SAFANI MACROPAD 9-KEY - SOURCE CONFIG ZMK
==========================================

Target:
- Nice!Nano V2 (nRF52840)
- 9 switch matrix 3x3 + encoder push switch as matrix position 10
- EC11 rotary encoder
- SSD1306 I2C OLED 128x32, address 0x3C
- Bluetooth LE
- Diode direction ROW2COL

PIN MAPPING
-----------
Rows:
  Row 0              P0.11
  Row 1              P1.04
  Row 2              P1.06
  Row 3 / Encoder SW P1.13

Columns:
  Column 0           P0.09
  Column 1           P0.10
  Column 2           P1.11

Encoder:
  A                  P0.29
  B                  P0.02
  SW                 Row 3 - Column 0 through its matrix diode

OLED:
  SDA                P0.17 (Nice!Nano D2)
  SCL                P0.20 (Nice!Nano D3)
  VCC                3.3V
  GND                GND

DIODE DIRECTION
---------------
ROW2COL means current flows from ROW to COLUMN:
- Diode anode -> ROW
- Diode cathode (striped end) -> COLUMN

IMPORTANT NFC PINS
------------------
P0.09 and P0.10 are NFC-capable pins on nRF52840. The overlay enables
them as GPIO through the UICR property nfct-pins-as-gpios. This is
persistent UICR configuration; do not remove it while using those pins.

KEYMAP DEFAULT
--------------
K1-K9 send F13-F21.
Encoder clockwise: Volume Up.
Encoder counter-clockwise: Volume Down.
Encoder push: Mute.

BUILD
-----
1. Upload the contents of this ZIP to a GitHub repository.
2. Keep build.yaml at repository root.
3. Keep the config directory at repository root.
4. Use the ZMK GitHub Actions build workflow/template.
5. The build target is nice_nano//zmk with shield safani9.
6. Download the firmware artifact after GitHub Actions succeeds.

This ZIP contains source configuration, NOT a compiled UF2.
The project has not yet been run through a ZMK build. The first GitHub
Actions build is required to validate the selected ZMK revision and
the actual PCB wiring.

If your repository is already using a different ZMK release or workflow,
match the board target syntax to that release.
