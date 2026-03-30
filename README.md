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
3. Set up NDI in Resolume (see below)
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

## Usage

Push2Resolume automatically connects to Resolume and your Push 2 on startup.

### Pads (8x8 grid)

The pad grid is rotated 90 degrees — each column maps to a Resolume layer, each row to a clip slot. Press a pad to trigger the corresponding clip.

### Encoders

The 8 encoders above the display control layer opacity (Layer 1-8). Turn to adjust, the value is sent to Resolume in real-time.

### Display

The Push 2 screen shows 8 layer outputs via NDI, with opacity sliders and the active clip name per layer.

### Above-screen buttons

Select a layer in Resolume (Layer 1-8). The selected layer gets a green border on the display.

### Below-screen buttons

Function depends on the active mode:

| Mode | Button action |
|------|---------------|
| **Stop Clip** (default) | Clear layer 1-8 |
| **Mute** | Toggle layer bypass 1-8 |
| **Solo** | Toggle layer solo 1-8 |

### Mode buttons

| Button | Function |
|--------|----------|
| **Stop Clip** | Activate Stop Clip mode (default) |
| **Mute** | Activate Mute mode |
| **Solo** | Activate Solo mode |

The active mode button lights up green.

### Arrow keys

Navigate the clip preview selection on the Resolume grid. Wraps around at the edges.

## Uninstall

Use Windows Add/Remove Programs or run the uninstaller from the Start menu.

