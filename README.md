# KnobV2.1 Vial QMK Firmware Profile

This is a custom firmware configuration for the [BaselineDesign Knob (V2.1)](https://github.com/BaselineDesign/BaselineDesign-Knob/) keypad, built on the [**Vial** fork of QMK](https://get.vial.today/). It enables extended configurability through the Vial application without requiring a custom JSON upload, and includes support for advanced QMK features like [tap-dance](https://docs.qmk.fm/features/tap_dance) and [key overrides](https://docs.qmk.fm/features/key_overrides).

---

## Getting Started

### Requirements

- [Vial firmware repository](https://github.com/vial-kb/vial-qmk)
- Your KnobV2.1 keyboard
- A working `qmk` or `vial` environment (see the Vial documentation for setup instructions)

### Installation

1. Clone the Vial QMK repo:
   ```bash
   git clone https://github.com/vial-kb/vial-qmk.git
   cd vial-qmk
   ```

2. Copy the `knobv2_1` directory into the `keyboards/` directory:

   ```bash
   cp -r /path/to/this/repo/knobv2_1 keyboards/
   ```

3. Build the firmware:

   ```bash
   make knobv2_1:vial
   ```

4. Flash the firmware to your KnobV2.1:

   ```bash
   make knobv2_1:vial:flash
   ```

   *(Follow flashing instructions from the original [Knob GitHub repo](https://github.com/BaselineDesign/BaselineDesign-Knob/))*

---

## Configuring with Vial

Once flashed, download the Vial app at: **[https://get.vial.today](https://get.vial.today)**, then:

* Open Vial
* Your KnobV2.1 should be automatically detected
* Begin configuring without any need for JSON uploads.

---

## Why Vial over VIA?

* **No JSON File Uploads**: Configuration is stored on the board.
* **Advanced QMK Features**: Supports features like Tap Dance, Key Overrides, etc.
* **More Flexibility**: Better suited for advanced keyboard users.

---

## Current Firmware Configuration

Due to memory constraints on the KnobV2.1 MCU, the firmware configuration in this repo has the following trade-offs:

* **Layers**: 4 total
* **Tap Dance Entries**: 4
* **Key Override Entries**: 1 (reduced to save space)
* **QMK Settings**: Disabled
* **Smooth Scrolling**: Removed (uses UP/DOWN keys instead)
* **Lighting Effects**: Disabled, but **Hue/Saturation control still works**

---

## Vial Profile Behavior

The included `tw-settings.vial` file contains:

* A multi-layer macro setup:

  * **Macro Layers M0 through M7** handle forward/backward layer switching via Tap Dance buttons (currently set to the left-button of each layer).
  * Uses **RGB Hue** (32 total steps) to represent state across layers. Each layer changes the hue by 8 steps so the layer colors are always the same.
* **Left Knob Key Tap Dance**:

  * Single Tap → Next Layer
  * Double Tap → Previous Layer
* All other keys are mapped with basic functions for simplicity.

---

## Precompiled Firmware

See the Releases for a ready-to-flash `.hex` file for the KnobV2.1.

---

## Questions?

Feel free to reach out or open an issue if you have questions or want to improve this profile further. Contributions welcome!

---
