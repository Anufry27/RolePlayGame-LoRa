# RolePlayGame-LoRa

Autonomous LoRa system for role-playing games with stable communication protocol.

**System Architecture:**
- **УУ** (Control Unit) - Game master control panel
- **УИ** (Game Object) - Physical game points with buttons and LEDs
- **УК** (Role Point Controller) - Score and resource management

## Project Stages

### Stage 1: Connection & Command Protocol (CURRENT)
- ✅ Stable LoRa protocol with CRC and ACK
- ✅ UU ↔ UI communication
- ✅ UI ↔ UK communication
- ✅ Serial monitoring for debugging

### Stage 2: Network Expansion
- Multiple UI devices (UI-01, UI-02, UI-03, UI-04)
- Multiple UK controllers (UK-GREEN, UK-BLUE)
- Addressing and broadcast

### Stage 3: Algorithms & Full Game
- Game algorithms (Capture, Reconnaissance, Hold)
- Role Points system
- Complete game scenario

## Hardware

Each device requires:
- Arduino Nano (ATmega328P)
- LoRa RA-01 / SX1278 (433 MHz)
- Power supply (2×18650 with DC-DC converter)

### UI Specific:
- WS2812B RGB LED
- 2× Push buttons (GREEN, BLUE)

### UU Specific:
- LCD 1602 (I2C)
- 4× Push buttons (UP, DOWN, OK, BACK)

### UK Specific:
- LCD 1602 (I2C)
- 1× Push button
- Color identification (GREEN or BLUE)

## File Structure

```
RolePlayGame-LoRa/
├── README.md
├── docs/
│   ├── PROTOCOL.md
│   └── HARDWARE.md
├── libraries/
│   └── LoRaProtocol/
│       ├── LoRaProtocol.h
│       └── LoRaProtocol.cpp
└── sketches/
    ├── UU_Controller/
    │   └── UU_Controller.ino
    ├── UI_GamePoint/
    │   └── UI_GamePoint.ino
    └── UK_RolePointCounter/
        └── UK_RolePointCounter.ino
```

## Quick Start

1. Install Arduino IDE
2. Install required libraries:
   - `LoRa` by Sandeep Mistry
   - `LiquidCrystal_I2C` by Frank de Brabander
   - `Adafruit_NeoPixel`
3. Copy `libraries/LoRaProtocol/` to Arduino libraries folder
4. Upload sketches to devices
5. Open Serial Monitor (9600 baud) to see debug logs

## Protocol Overview

See `docs/PROTOCOL.md` for detailed message structure.

**Basic message types:**
- `COMMAND` - UU sends command to UI
- `ACK` - UI acknowledges receipt
- `EVENT` - UI reports event completion to UK
- `STATUS` - Optional status updates

## Status

**Stage 1: IN PROGRESS**
- Protocol design: ✅
- Library: IN PROGRESS
- UU sketch: IN PROGRESS
- UI sketch: IN PROGRESS
- UK sketch: IN PROGRESS
