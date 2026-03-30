# Push2Resolume

Control Resolume Arena with your Ableton Push 2. Push2Resolume bridges the Push 2's pads, encoders, and display to Resolume's layers, clips, and effects.

## Requirements

- Windows 10/11 (64-bit)
- Ableton Push 2 (connected via USB)
- Resolume Arena or Avenue with the REST API enabled (default port 8080)
- NDI Runtime (for Push 2 display output)

## Installation

1. Download the latest installer from the [releases](releases/) folder
2. Run the installer — it will install to Program Files and add a startup shortcut
3. Set up NDI and ArtNet in Resolume (see below)
4. Connect your Push 2 and launch Push2Resolume

## Resolume NDI Setup

Push2Resolume receives a live video feed from Resolume via NDI to show clip previews on the Push 2 display.

### Option A: Import the preset

1. Copy `presets/PushDisplay.xml` to your Resolume presets folder
2. In Resolume, go to **Arena > Advanced Output**
3. Load the `PushDisplay` preset

### Option B: Manual setup

1. In Resolume, go to **Arena > Advanced Output**
2. Add a new **Screen** and name it `PushDisplay`
3. Set the output to **NDI** with resolution **960 x 160**
4. Create **8 slices**, each 120 x 160 pixels, arranged left to right
5. Map each slice to a layer (Layer 1 through Layer 8)
6. Rotate each slice **90 degrees**
7. Enable the screen

The NDI source name must match: `{YourComputerName} (Arena - PushDisplay)`

Push2Resolume will automatically detect and connect to this NDI source.

## Resolume ArtNet Setup

Push2Resolume uses ArtNet to light up the Push 2 pads with colors matching your Resolume clips. Resolume sends an 8x8 RGB pixel grid via ArtNet, and Push2Resolume maps each pixel to a pad color.

### Setup

1. Copy `presets/led8x8.xml` to your Resolume fixtures folder (usually `Documents/Resolume Arena/Fixtures/`)
2. In Resolume, go to **Arena > Advanced Output**
3. Add a **DMX/ArtNet** output using the `LED8x8` fixture
4. Set the ArtNet **universe** and **start address** (defaults: universe 0, address 1)
5. Map the fixture to your composition

### Configuration

In Push2Resolume's settings (accessible via the tray icon), make sure the ArtNet universe and start address match what you configured in Resolume:

- **ArtNet Universe**: 0 (default)
- **ArtNet Start Address**: 1 (default)

## Usage

Push2Resolume automatically connects to Resolume and your Push 2 on startup.

- **Pads** — Trigger clips in Resolume, colors reflect clip state via ArtNet
- **Encoders** — Control layer opacity and effect parameters
- **Display** — Shows live clip previews and layer state on the Push 2 screen

## Uninstall

Use Windows Add/Remove Programs or run the uninstaller from the Start menu.
