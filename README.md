# nRF24L01 Diagnosti Test for Arduino

A quick diagnostic sketch for Arduino to verify the SPI communication and register configurations of the nRF24L01 transceiver module.

## Overview
When working with nRF24L01 transceiver modules, loose wiring, incorrect pin connections, or insufficient 3.3V power supply can lead to communication failures. This diagnostic script initializes the radio and prints its internal configuration registers directly to the Serial Monitor so you can verify that your hardware is properly connected and functioning.

## Pinout Wiring (Arduino Uno / Nano)

| nRF24L01 Pin | Arduino Pin | Description |
| :--- | :--- | :--- |
| **GND** | GND | Ground |
| **VCC** | 3.3V | Power Supply *(Important: Do not connect to 5V)* |
| **CE** | D7 | Chip Enable |
| **CSN** | D8 | Chip Select Not |
| **SCK** | D13 | SPI Clock |
| **MOSI** | D11 | SPI Master Out Slave In |
| **MISO** | D12 | SPI Master In Slave Out |

## Required Libraries
Make sure you have the following library installed via the Arduino IDE Library Manager:
* **RF24** (by TMRh20)

## Expected Serial Output
Open your Arduino Serial Monitor at a baud rate of **9600**. If your module is wired correctly and communicating successfully over SPI, you should see the following register values:

```text
EN_AA          = 0x3f
EN_RXADDR      = 0x02
RF_CH          = 0x4c
RF_SETUP       = 0x03
CONFIG         = 0x0f
