# Digispark ATtiny85 - Mouse Functionality Guide

This guide provides instructions on how to use the **Digispark ATtiny85** for emulating mouse functionality via the **HID-Project** library. You'll learn how to simulate various mouse actions like moving the cursor, clicking, scrolling, dragging, and more. Whether you're building automation scripts, creating custom input devices, or just experimenting with HID devices, this guide will help you get started.

<br/>

## Prerequisites

To use the **HID-Project** library for mouse emulation with the **Digispark ATtiny85**, you'll need to install the library in your Arduino IDE:

1. Open the **Arduino IDE**.
2. Go to **Sketch > Include Library > Manage Libraries...**.
3. Search for "**HID-Project**" and click **Install**.

Once the library is installed, you're ready to start using the Digispark ATtiny85 for mouse emulation!

<br/>

## Basic Mouse Operations

The **HID-Project** library provides several functions to emulate mouse actions. Below are the core functionalities you can use with your **Digispark ATtiny85**.

### 1. Moving the Mouse

You can move the mouse cursor on the screen by using the `Mouse.move()` function.

#### Syntax:
```cpp
Mouse.move(x, y, wheel);
```

- `x`: Horizontal movement (positive for right, negative for left).
- `y`: Vertical movement (positive for down, negative for up).
- `wheel`: Scroll wheel movement (positive for up, negative for down).

#### Example: Move the Mouse 10 Pixels to the Right and 10 Pixels Down
```cpp
Mouse.move(10, 10, 0);  // Moves the mouse diagonally
```

<br/>

### 2. Simulating Mouse Clicks

You can simulate mouse clicks with the functions `Mouse.click()`, `Mouse.press()`, and `Mouse.release()`.

#### Syntax:
```cpp
Mouse.click(button);
Mouse.press(button);
Mouse.release(button);
```

- `button`: The button you want to click. Possible values:
  - `MOUSE_LEFT`
  - `MOUSE_RIGHT`
  - `MOUSE_MIDDLE`

#### Example: Simulate Left Mouse Click
```cpp
Mouse.click(MOUSE_LEFT);
```

#### Example: Press and Hold Left Mouse Button
```cpp
Mouse.press(MOUSE_LEFT);
delay(1000);  // Hold the button for 1 second
Mouse.release(MOUSE_LEFT);
```

<br/>

### 3. Scrolling with the Mouse

Simulate mouse wheel scrolling with the `Mouse.scroll()` function.

#### Syntax:
```cpp
Mouse.scroll(wheel);
```

- `wheel`: The number of scroll units (positive for scrolling up, negative for scrolling down).

#### Example: Scroll Down
```cpp
Mouse.scroll(-1);  // Scrolls down once
```

#### Example: Scroll Up
```cpp
Mouse.scroll(1);   // Scrolls up once
```

<br/>

### 4. Quick Mouse Movement

You can move the mouse quickly by using larger values for `x` and `y`. The mouse will move smoothly based on the given input.

#### Example: Move the Mouse 100 Pixels to the Right and 50 Pixels Down
```cpp
Mouse.move(100, 50, 0);  // Quick movement to the bottom right
```

<br/>

### 5. Mouse Dragging

To drag an item, you press and hold a mouse button, move the mouse, and then release the button.

#### Example: Drag an Item from Top-Left to Bottom-Right
```cpp
Mouse.press(MOUSE_LEFT);     // Press the left mouse button
Mouse.move(50, 50, 0);       // Move diagonally
delay(500);                  // Wait for 0.5 seconds
Mouse.move(100, 100, 0);     // Move further diagonally
Mouse.release(MOUSE_LEFT);   // Release the left mouse button
```

<br/>

### 6. Simulating Diagonal Movement

Simulate diagonal movements by adjusting both the `x` and `y` coordinates.

#### Example: Move the Mouse Diagonally (Right & Down)
```cpp
Mouse.move(10, 10, 0);  // Move 10 pixels to the right and down
```

<br/>

### 7. Continuous Mouse Movement

Create continuous or repetitive mouse movements with a loop.

#### Example: Continuously Move the Mouse to the Right
```cpp
void loop() {
  Mouse.move(5, 0, 0);   // Move 5 pixels to the right
  delay(100);             // Wait for 100ms before moving again
}
```

<br/>

### 8. Control System UI with Mouse

Use the mouse to automate UI actions like clicking icons or navigating menus.

#### Example: Click on a Specific Screen Location
```cpp
Mouse.move(500, 300, 0);  // Move to (500, 300) on the screen
Mouse.click(MOUSE_LEFT);   // Click the mouse at that position
```

<br/>

## Example Code - Combining Mouse and Keyboard

This example shows how to use both mouse and keyboard emulation together, ideal for creating automated workflows.

```cpp
#include <HID-Project.h>

void setup() {
  Mouse.begin();     // Start mouse emulation
  Keyboard.begin();  // Start keyboard emulation
  
  // Simulate Mouse Scroll
  Mouse.scroll(1);   // Scroll up
  
  delay(500);         // Wait for half a second
  
  // Move the Mouse to the Right
  Mouse.move(50, 0, 0);
  
  delay(500);         // Wait for half a second
  
  // Simulate Left Mouse Click
  Mouse.click(MOUSE_LEFT);
  
  delay(500);         // Wait for half a second
  
  // Type a message
  Keyboard.print("Hello, Digispark!");
  Keyboard.press(KEY_RETURN);
  Keyboard.releaseAll();
  
  Mouse.end();        // End mouse emulation
  Keyboard.end();     // End keyboard emulation
}

void loop() {
  // Empty loop, all actions are in setup()
}
```

<br/>

## Notes and Tips

- **Smooth Movement**: Mouse movement is generally smooth and based on the pixel values you provide. If you want very fast or large movements, adjust the `x`, `y`, and `wheel` parameters accordingly.
  
- **Using Delays**: It's a good idea to use `delay()` in between actions, especially when you're simulating multiple inputs, to ensure actions are properly registered.
  
- **Combining Inputs**: You can combine keyboard and mouse actions to create powerful automation scripts or custom input devices. For example, you could simulate a drag-and-drop action, or a keyboard shortcut followed by a mouse click.

<br/>

## Conclusion

With the **Digispark ATtiny85** and the **HID-Project** library, you can emulate a wide range of mouse actions for your projects. Whether you're automating desktop tasks, creating custom control devices, or experimenting with mouse input, these functions give you full control over the mouse.

Explore and modify the examples above to suit your needs, and let your creativity run wild with the Digispark ATtiny85's mouse emulation capabilities!

Happy hacking! 🎮
