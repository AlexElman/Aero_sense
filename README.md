# Aero_sense
Can-Sat 2026/27 project group 2 from HTL Rennweg

## Core

| Component | Manufacturer / Part Number | Description |
|-----------|---------------------------|-------------|
| **MCU** | STMicroelectronics **STM32F415ZGT6** | High-performance ARM Cortex-M4 microcontroller (168 MHz, 1 MB Flash, 192 KB RAM). Selected for processing power, multiple peripherals (SPI, I²C, UART), and suitability for real-time sensor fusion and telemetry. |

## Sensors

| Component | Manufacturer / Part Number | Description |
|-----------|---------------------------|-------------|
| **Barometer** | Bosch **BMP581** | High-accuracy, low-noise absolute pressure sensor. Excellent for precise altitude determination. Digital SPI/I²C interface. Preferred over BMP390 for better noise performance and resolution. |
| **IMU** | TDK InvenSense **ICM-42688-P** | High-performance 6-axis IMU (3-axis gyroscope + 3-axis accelerometer). Low noise, high stability, SPI interface. Chosen for accurate attitude and motion sensing during flight. |
| **GNSS** | u-blox **SAM-M10Q** | Compact concurrent multi-GNSS module (GPS, GLONASS, Galileo, BeiDou). Good sensitivity and update rate for position/velocity tracking. UART interface. |
| **Temperature & Humidity** | Sensirion **SHT45** | High-accuracy digital temperature and relative humidity sensor. Excellent long-term stability and low power consumption. I²C interface. |
| **VOC / Air Quality** | Sensirion **SGP41** | Digital VOC + NOx sensor providing VOC Index and NOx Index outputs. Significantly better long-term stability and lower power than BME688. I²C interface. |

## Communication

| Component | Manufacturer / Part Number | Description |
|-----------|---------------------------|-------------|
| **LoRa Telemetry** | MicoAir **LR868F** (with 2 dBi antenna) | 868 MHz LoRa telemetry radio (500 mW). Long-range, interference-resistant link for real-time data downlink. UART interface. Suitable for CanSat telemetry ranges. |

## Power

| Component | Manufacturer / Part Number | Description |
|-----------|---------------------------|-------------|
| **Battery** | Molicel **INR-21700-P50B** (P50B) | Single high-power 21700 Li-ion cell (nominal 3.6 V, 5000 mAh, up to 60 A continuous). Excellent energy and power density for the limited volume of a CanSat. |
| **Battery Charger / PMIC** | Texas Instruments **BQ25895** | Highly integrated battery charge management IC with system power path management. Supports fast charging of the P50B cell and provides regulated system power. |

## Board-to-Board Interconnect

| Component | Manufacturer / Part Number | Description |
|-----------|---------------------------|-------------|
| **Mezzanine Connectors** | Amphenol **BergStak 0.40 mm** (2×) | Two board-to-board stacking connectors (recommended 20-pin version with 4.0 mm stack height). Provides power, SPI, I²C, UART and multiple GND connections between the three circular PCBs while offering good mechanical rigidity and vibration resistance. |

## Mechanical / PCB Notes

- Three custom semi-circular PCBs ( ≈58 mm diameter)
- Sensors requiring fresh air (BMP581, SHT45, SGP41) placed on the bottom board with controlled side vents
- Charging and data-transfer via USB-C
