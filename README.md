# ExpressLRS 4.0 for E28-2G4M27SX (2.4GHz 500mW)

Custom ELRS RX firmware for E28-2G4M27SX module (SX1281, 27dBm/500mW).

## Hardware
- **MCU:** ESP32-C3
- **Radio:** E28-2G4M27SX (SX1281)
- **Power:** 27dBm (500mW) with built-in PA/LNA

## Frequency
- Band: ISM 2.4GHz (2400-2500MHz)

## Download
See [Releases](https://github.com/ddlabus/ExpressLRS-E28-2G4/releases) for compiled firmware.

## Files
| File | Description |
|------|-------------|
| `ELRS_4.0_RX_ESP32C3_E28_2400.bin` | Receiver firmware |
| `E28-2G4M27SX_RX.json` | RX hardware layout |

## Pinout (ESP32-C3 to E28-2G4M27SX)
| ESP32-C3 | E28-2G4M27SX |
|----------|--------------|
| GPIO1    | DIO1         |
| GPIO2    | RESET        |
| GPIO3    | BUSY         |
| GPIO4    | MOSI         |
| GPIO5    | MISO         |
| GPIO6    | SCK          |
| GPIO7    | NSS          |
| GPIO0    | TXEN         |
| GPIO10   | RXEN         |
| GPIO8    | LED          |
| GPIO20   | Serial RX    |
| GPIO21   | Serial TX    |

## Flashing
Use [esptool](https://github.com/espressif/esptool) or ELRS Configurator.
