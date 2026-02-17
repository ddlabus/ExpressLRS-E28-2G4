# ExpressLRS RX for E28-2G4M27SX (2.4GHz 500mW)

Custom ELRS RX firmware for E28-2G4M27SX module (SX1281, 27dBm/500mW).

![E28-2G4M27SX Module](https://raw.githubusercontent.com/ddlabus/ExpressLRS-E28-2G4/main/images/E28-2G4M27SX.jpg)

## Hardware

### Receiver (RX only)
- **MCU:** ESP32-C3 SuperMini
- **Radio:** E28-2G4M27SX (SX1281, 27dBm/500mW)

![ESP32-C3 SuperMini](https://raw.githubusercontent.com/ddlabus/ExpressLRS-E28-2G4/main/images/ESP32-C3.avif)

## Frequency
- Band: ISM 2.4GHz (2400-2500MHz)

---

## Wiring Diagram

### RX: ESP32-C3 SuperMini + E28-2G4M27SX

```
ESP32-C3 SuperMini         E28-2G4M27SX
┌─────────────────┐        ┌─────────────────┐
│                 │        │                 │
│ GPIO20 (RX) ────┼────────┼─ (to FC)        │
│ GPIO21 (TX) ────┼────────┼─ (from FC)      │
│                 │        │                 │
│ GPIO1  ─────────┼────────┼─ DIO1           │
│ GPIO2  ─────────┼────────┼─ RST            │
│ GPIO3  ─────────┼────────┼─ BUSY           │
│ GPIO4  ─────────┼────────┼─ MOSI           │
│ GPIO5  ─────────┼────────┼─ MISO           │
│ GPIO6  ─────────┼────────┼─ SCK            │
│ GPIO7  ─────────┼────────┼─ NSS            │
│                 │        │                 │
│ GPIO0  ─────────┼────────┼─ TXEN           │
│ GPIO10 ─────────┼────────┼─ RXEN           │
│                 │        │                 │
│ GPIO8  ─────────┼────────┼─ LED            │
│                 │        │                 │
│ 3V3    ─────────┼────────┼─ VCC (3.3V)     │
│ GND    ─────────┼────────┼─ GND            │
└─────────────────┘        └─────────────────┘
```

| ESP32-C3 Pin | E28-2G4M27SX Pin | Function |
|--------------|------------------|----------|
| GPIO20 | - | Serial RX (to FC) |
| GPIO21 | - | Serial TX (from FC) |
| GPIO1 | DIO1 | Radio interrupt |
| GPIO2 | RST | Radio reset |
| GPIO3 | BUSY | Radio busy |
| GPIO4 | MOSI | SPI data out |
| GPIO5 | MISO | SPI data in |
| GPIO6 | SCK | SPI clock |
| GPIO7 | NSS | SPI chip select |
| GPIO0 | TXEN | PA TX enable |
| GPIO10 | RXEN | PA RX enable |
| GPIO8 | - | LED |
| 3V3 | VCC | Power 3.3V |
| GND | GND | Ground |

---

## Flashing Firmware

### RX (ESP32-C3 SuperMini)

**Via USB-C (built-in bootloader):**
1. Hold BOOT button
2. Connect USB-C cable
3. Release BOOT button

```bash
esptool.py --port /dev/ttyACM0 --baud 460800 \
    --chip esp32c3 write_flash 0x0 ELRS_*_RX_ESP32C3_E28-2G4M27SX.bin
```

### After Flashing
1. Power cycle the module
2. Connect to WiFi: `ExpressLRS RX`
3. Configure at `10.0.0.1`

---

## Download
See [Releases](https://github.com/ddlabus/ExpressLRS-E28-2G4/releases)

## Files
| File | Description |
|------|-------------|
| `ELRS_*_RX_ESP32C3_E28-2G4M27SX.bin` | Receiver firmware (ESP32-C3) |
| `ESP32C3_SuperMini_RX.json` | RX hardware layout |

## Links
- [E28-2G4M27SX Datasheet](https://www.cdebyte.com/products/E28-2G4M27SX)
- [ESP32-C3 SuperMini](https://www.aliexpress.com/item/1005005967641936.html)
- [ExpressLRS Documentation](https://www.expresslrs.org/)
