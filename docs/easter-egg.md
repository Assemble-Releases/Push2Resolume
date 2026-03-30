# ArtNet Easter Egg

Push2Resolume can receive ArtNet data to control the Push 2 pad colors directly from Resolume. This is an easter egg mode — not required for normal operation.

## Setup

1. Copy `presets/led8x8.xml` to your Resolume fixtures folder (usually `Documents/Resolume Arena/Fixtures/`)
2. In Resolume, go to **Arena > Advanced Output**
3. Add a **DMX/ArtNet** output using the `LED8x8` fixture
4. Map the 8x8 grid to your composition — each pixel maps to a pad on the Push 2

## Configuration

In Push2Resolume's settings, set the ArtNet universe and start address to match Resolume:

- **ArtNet Universe**: 0 (default)
- **ArtNet Start Address**: 1 (default)
