# Digispark ATtiny85 Key Codes and Modifiers

This table can be useful if you are writing code that simulates keystrokes or actions via the **Digispark ATtiny85** (like a "USB keyboard").

Here, we provide a table with the main **key codes** and **modifiers** that can be used in the **Digispark ATtiny85** with the **HID-Project** or **HID-Keyboard** library to emulate keyboard inputs.

## Key Codes and Modifiers for Digispark ATtiny85 (Keyboard Emulation)

### Key Codes

| **Action**                | **Key Code**                |
|---------------------------|-----------------------------|
| **Key A**                 | `KEY_A`                     |
| **Key B**                 | `KEY_B`                     |
| **Key C**                 | `KEY_C`                     |
| **Key D**                 | `KEY_D`                     |
| **Key E**                 | `KEY_E`                     |
| **Key F**                 | `KEY_F`                     |
| **Key G**                 | `KEY_G`                     |
| **Key H**                 | `KEY_H`                     |
| **Key I**                 | `KEY_I`                     |
| **Key J**                 | `KEY_J`                     |
| **Key K**                 | `KEY_K`                     |
| **Key L**                 | `KEY_L`                     |
| **Key M**                 | `KEY_M`                     |
| **Key N**                 | `KEY_N`                     |
| **Key O**                 | `KEY_O`                     |
| **Key P**                 | `KEY_P`                     |
| **Key Q**                 | `KEY_Q`                     |
| **Key R**                 | `KEY_R`                     |
| **Key S**                 | `KEY_S`                     |
| **Key T**                 | `KEY_T`                     |
| **Key U**                 | `KEY_U`                     |
| **Key V**                 | `KEY_V`                     |
| **Key W**                 | `KEY_W`                     |
| **Key X**                 | `KEY_X`                     |
| **Key Y**                 | `KEY_Y`                     |
| **Key Z**                 | `KEY_Z`                     |
| **Key 0**                 | `KEY_0`                     |
| **Key 1**                 | `KEY_1`                     |
| **Key 2**                 | `KEY_2`                     |
| **Key 3**                 | `KEY_3`                     |
| **Key 4**                 | `KEY_4`                     |
| **Key 5**                 | `KEY_5`                     |
| **Key 6**                 | `KEY_6`                     |
| **Key 7**                 | `KEY_7`                     |
| **Key 8**                 | `KEY_8`                     |
| **Key 9**                 | `KEY_9`                     |
| **Enter**                 | `KEY_RETURN`                |
| **Space**                 | `KEY_SPACE`                 |
| **Backspace**             | `KEY_BACKSPACE`             |
| **Tab**                   | `KEY_TAB`                   |
| **Escape**                | `KEY_ESC`                   |
| **Shift**                 | `MOD_SHIFT`                 |
| **Control**               | `MOD_CONTROL`               |
| **Alt**                   | `MOD_ALT`                   |
| **GUI (Windows)**         | `MOD_GUI_LEFT`              |
| **GUI (Mac)**             | `MOD_GUI_RIGHT`             |
| **Caps Lock**             | `KEY_CAPS_LOCK`             |
| **F1**                    | `KEY_F1`                    |
| **F2**                    | `KEY_F2`                    |
| **F3**                    | `KEY_F3`                    |
| **F4**                    | `KEY_F4`                    |
| **F5**                    | `KEY_F5`                    |
| **F6**                    | `KEY_F6`                    |
| **F7**                    | `KEY_F7`                    |
| **F8**                    | `KEY_F8`                    |
| **F9**                    | `KEY_F9`                    |
| **F10**                   | `KEY_F10`                   |
| **F11**                   | `KEY_F11`                   |
| **F12**                   | `KEY_F12`                   |

### Combined Modifiers

- **Shift + A**:  
  ```cpp
  Keyboard.press(MOD_SHIFT);
  Keyboard.press(KEY_A);
  Keyboard.releaseAll();
  ```
- **Ctrl + C**:  
  ```cpp
  Keyboard.press(MOD_CONTROL);
  Keyboard.press(KEY_C);
  Keyboard.releaseAll();
  ```
- **Alt + Tab**:  
  ```cpp
  Keyboard.press(MOD_ALT);
  Keyboard.press(KEY_TAB);
  Keyboard.releaseAll();
  ```
- **Shift + Enter**:  
  ```cpp
  Keyboard.press(MOD_SHIFT);
  Keyboard.press(KEY_RETURN);
  Keyboard.releaseAll();
  ```

### Notes:
- **MOD_SHIFT**, **MOD_CONTROL**, **MOD_ALT**, **MOD_GUI_LEFT**, **MOD_GUI_RIGHT** are **modifiers** that change the behavior of keys.
- The **HID-Project** or **HID-Keyboard** library must be installed in the IDE to use these keys.
- This table is primarily used to simulate keyboard input in Digispark, making it useful for projects like keystroke automation.
```
