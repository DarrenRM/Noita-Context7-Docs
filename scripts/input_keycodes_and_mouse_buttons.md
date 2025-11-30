---
title: Input Keycodes and Mouse Buttons
category: scripts
---

# Input Keycodes and Mouse Buttons

This document outlines the numerical identifiers for mouse buttons and keyboard keys used within Noita's scripting API, specifically for functions like `InputIsMouseButtonDown(...)` and `InputIsButtonDown(...)`. Understanding these codes is crucial for implementing custom input handling in your mods.

## Mouse Buttons

These constants represent the different mouse buttons.

| Constant Name       | Value | Description        |
| :------------------ | :---- | :----------------- |
| `Mouse_left`        | 1     | Left mouse button  |
| `Mouse_right`       | 2     | Right mouse button |
| `Mouse_middle`      | 3     | Middle mouse button|
| `Mouse_wheel_up`    | 4     | Mouse wheel up     |
| `Mouse_wheel_down`  | 5     | Mouse wheel down   |
| `Mouse_x1`          | 6     | Mouse button X1    |
| `Mouse_x2`          | 7     | Mouse button X2    |

## Keyboard Keycodes

These constants represent various keyboard keys. They are used with the `InputIsButtonDown(...)` function.

### Alphabetical Keys

| Constant Name | Value | Description |
| :------------ | :---- | :---------- |
| `Key_a`       | 4     | 'A' key     |
| `Key_b`       | 5     | 'B' key     |
| ...           | ...   | ...         |
| `Key_z`       | 29    | 'Z' key     |

### Number Keys

| Constant Name | Value | Description |
| :------------ | :---- | :---------- |
| `Key_1`       | 30    | '1' key     |
| `Key_2`       | 31    | '2' key     |
| ...           | ...   | ...         |
| `Key_0`       | 39    | '0' key     |

### Special Keys

| Constant Name      | Value | Description         |
| :----------------- | :---- | :------------------ |
| `Key_RETURN`       | 40    | Enter key           |
| `Key_ESCAPE`       | 41    | Escape key          |
| `Key_BACKSPACE`    | 42    | Backspace key       |
| `Key_TAB`          | 43    | Tab key             |
| `Key_SPACE`        | 44    | Spacebar            |
| `Key_MINUS`        | 45    | Minus key           |
| `Key_EQUALS`       | 46    | Equals key          |
| `Key_LEFTBRACKET`  | 47    | Left bracket key    |
| `Key_RIGHTBRACKET` | 48    | Right bracket key   |
| `Key_BACKSLASH`    | 49    | Backslash key       |
| `Key_SEMICOLON`    | 51    | Semicolon key       |
| `Key_APOSTROPHE`   | 52    | Apostrophe key      |
| `Key_GRAVE`        | 53    | Grave accent key    |
| `Key_COMMA`        | 54    | Comma key           |
| `Key_PERIOD`       | 55    | Period key          |
| `Key_SLASH`        | 56    | Slash key           |
| `Key_CAPSLOCK`     | 57    | Caps Lock key       |

### Function Keys (F1-F24)

| Constant Name | Value | Description |
| :------------ | :---- | :---------- |
| `Key_F1`      | 58    | F1 key      |
| `Key_F2`      | 59    | F2 key      |
| ...           | ...   | ...         |
| `Key_F24`     | 115   | F24 key     |

### Navigation and Editing Keys

| Constant Name | Value | Description      |
| :------------ | :---- | :--------------- |
| `Key_INSERT`  | 73    | Insert key       |
| `Key_HOME`    | 74    | Home key         |
| `Key_PAGEUP`  | 75    | Page Up key      |
| `Key_DELETE`  | 76    | Delete key       |
| `Key_END`     | 77    | End key          |
| `Key_PAGEDOWN`| 78    | Page Down key    |
| `Key_RIGHT`   | 79    | Right arrow key  |
| `Key_LEFT`    | 80    | Left arrow key   |
| `Key_DOWN`    | 81    | Down arrow key   |
| `Key_UP`      | 82    | Up arrow key     |

### Numpad Keys

| Constant Name   | Value | Description       |
| :-------------- | :---- | :---------------- |
| `Key_NUMLOCKCLEAR`| 83    | Num Lock key      |
| `Key_KP_DIVIDE` | 84    | Numpad Divide     |
| `Key_KP_MULTIPLY`| 85    | Numpad Multiply   |
| `Key_KP_MINUS`  | 86    | Numpad Minus      |
| `Key_KP_PLUS`   | 87    | Numpad Plus       |
| `Key_KP_ENTER`  | 88    | Numpad Enter      |
| `Key_KP_1`      | 89    | Numpad 1          |
| ...             | ...   | ...               |
| `Key_KP_0`      | 98    | Numpad 0          |
| `Key_KP_PERIOD` | 99    | Numpad Decimal    |

### Modifier Keys

| Constant Name | Value | Description     |
| :------------ | :---- | :-------------- |
| `Key_LCTRL`   | 224   | Left Control    |
| `Key_LSHIFT`  | 225   | Left Shift      |
| `Key_LALT`    | 226   | Left Alt        |
| `Key_LGUI`    | 227   | Left GUI (Win/Cmd)|
| `Key_RCTRL`   | 228   | Right Control   |
| `Key_RSHIFT`  | 229   | Right Shift     |
| `Key_RALT`    | 230   | Right Alt       |
| `Key_RGUI`    | 231   | Right GUI (Win/Cmd)|

### Multimedia and Application Keys

| Constant Name     | Value | Description        |
| :---------------- | :---- | :----------------- |
| `Key_POWER`       | 102   | Power button       |
| `Key_VOLUMEUP`    | 128   | Volume Up          |
| `Key_VOLUMEDOWN`  | 129   | Volume Down        |
| `Key_MUTE`        | 127   | Mute button        |
| `Key_MAIL`        | 265   | Mail button        |
| `Key_CALCULATOR`  | 266   | Calculator button  |
| `Key_COMPUTER`    | 267   | Computer button    |
| `Key_WWW`         | 264   | Web/Home button    |

## Joystick (Gamepad) Input

These constants are used for detecting input from a gamepad.

### Analog Stick Movement

| Constant Name             | Value | Description                               |
| :------------------------ | :---- | :---------------------------------------- |
| `JOY_BUTTON_ANALOG_00_MOVED`| 1     | Analog stick 0 movement detected          |
| `JOY_BUTTON_ANALOG_01_MOVED`| 2     | Analog stick 1 movement detected          |
| ...                       | ...   | ...                                       |
| `JOY_BUTTON_ANALOG_09_MOVED`| 10    | Analog stick 9 movement detected          |
| `JOY_BUTTON_LEFT_STICK_MOVED`| 21    | Left analog stick movement detected       |
| `JOY_BUTTON_RIGHT_STICK_MOVED`| 22    | Right analog stick movement detected      |

### D-Pad and Button Inputs

| Constant Name        | Value | Description        |
| :------------------- | :---- | :----------------- |
| `JOY_BUTTON_DPAD_UP` | 11    | D-Pad Up           |
| `JOY_BUTTON_DPAD_DOWN`| 12    | D-Pad Down         |
| `JOY_BUTTON_DPAD_LEFT`| 13    | D-Pad Left         |
| `JOY_BUTTON_DPAD_RIGHT`| 14    | D-Pad Right        |
| `JOY_BUTTON_START`   | 15    | Start button       |
| `JOY_BUTTON_BACK`    | 16    | Back button        |
| `JOY_BUTTON_LEFT_THUMB`| 17    | Left Thumb button  |
| `JOY_BUTTON_RIGHT_THUMB`| 18    | Right Thumb button |
| `JOY_BUTTON_LEFT_SHOULDER`| 19    | Left Shoulder button|
| `JOY_BUTTON_RIGHT_SHOULDER`| 20    | Right Shoulder button|

### Face Buttons (Common Layout)

| Constant Name | Value | Description |
| :------------ | :---- | :---------- |
| `JOY_BUTTON_A`| 23    | 'A' button  |
| `JOY_BUTTON_B`| 24    | 'B' button  |
| `JOY_BUTTON_X`| 25    | 'X' button  |
| `JOY_BUTTON_Y`| 26    | 'Y' button  |

### Other Gamepad Buttons

| Constant Name | Value | Description |
| :------------ | :---- | :---------- |
| `JOY_BUTTON_0`| 23    | Button 0    |
| `JOY_BUTTON_1`| 24    | Button 1    |
| ...           | ...   | ...         |
| `JOY_BUTTON_15`| 38    | Button 15   |

### Analog Stick Directional Inputs

These represent specific directions for the analog sticks.

| Constant Name              | Value | Description             |
| :------------------------- | :---- | :---------------------- |
| `JOY_BUTTON_LEFT_STICK_LEFT` | 39    | Left stick left         |
| `JOY_BUTTON_LEFT_STICK_RIGHT`| 40    | Left stick right        |
| `JOY_BUTTON_LEFT_STICK_UP`   | 41    | Left stick up           |
| `JOY_BUTTON_LEFT_STICK_DOWN` | 42    | Left stick down         |
| `JOY_BUTTON_RIGHT_STICK_LEFT`| 43    | Right stick left        |
| `JOY_BUTTON_RIGHT_STICK_RIGHT`| 44    | Right stick right       |
| `JOY_BUTTON_RIGHT_STICK_UP`  | 45    | Right stick up          |
| `JOY_BUTTON_RIGHT_STICK_DOWN`| 46    | Right stick down        |