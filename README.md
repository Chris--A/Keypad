# Keypad library for Arduino

![image](https://user-images.githubusercontent.com/36513474/68024736-bd3e1080-fccc-11e9-85c3-f29f43ae4f8c.png)

## Description

The Keypad is a library for using matrix style keypads with the Arduino. As of version 3.0, it now supports multiple keypresses.

This library is based upon the [Keypad Tutorial](https://playground.arduino.cc/Main/KeypadTutorial/).

It was created to promote [Hardware Abstraction](https://playground.arduino.cc/Code/HardwareAbstraction/). Keypad library is part of the Hardware Abstraction libraries.

Version 3.0 has just been posted (19 July 2012) and was rewritten to support multi-keypresses by default.

This repository is a copy of the code found here [[Arduino Playground]](http://playground.arduino.cc/Code/Keypad).

The source and file structure has been modified to conform to the newer `1.5r2` library specification and is not compatible with legacy IDE's.
For these IDE's, visit the link above to grab the pre `1.0` compatible version, or download it directly here:  [[pre `1.0` version]](http://playground.arduino.cc/uploads/Code/keypad.zip).

## Installation

### First Method

1. In the Arduino IDE, navigate to Sketch > Include Library > Manage Libraries
1. Then the Library Manager will open and you will find a list of libraries that are already installed or ready for installation.
1. Then search for Keypad using the search bar.
1. Click on the text area and then select the specific version and install it.

### Second Method

1. Navigate to the [Releases page](https://github.com/Chris--A/Keypad/releases).
1. Download the latest release.
1. Extract the zip file
1. In the Arduino IDE, navigate to Sketch > Include Library > Add .ZIP Library

## Features

- ### Hardware abstraction

    It improves the readability of the code by hiding the pinMode and digitalRead calls for the user.

- ### Compatibility

    For those who still need the original single-keypress functionality, the library is fully backward compatible.

- ### No external dependency

    You won't need external resistors or diodes because the library uses the internal pullup resistors and additionally ensures that all unused column pins are high-impedance.

- ### Hardware support

    Support was added to allow other hardware to be used along with a keypad. Joe Young's keypad library added support for several I2C expander chips. You can find it [here](https://github.com/joeyoung/arduino_keypads)

- ### Give back

    OneWire is free for everyone. The licensed document can be copied, redistributed and used in the projects, assignments or anywhere.

## Functions

- begin()
- getKey()
- getKeys()
- scanKeys()
- updateList()
- nextKeyState()
- isPressed()
- findInList()
- waitForKey()
- getState()
- keyStateChanged()
- numKeys()
- setDebounceTime()
- setHoldTime()
- addEventListener()
- transitionTo()
- key_update()

For further functions description visit [Playground-Keypad](https://playground.arduino.cc/Code/Keypad/)

## Example

There are many examples implemented where this library is used. You can find other examples from [Github-Keypad](https://github.com/Chris--A/Keypad/tree/master/examples) and [Arduino Playground](https://playground.arduino.cc/Code/Keypad/)

- ### HelloKeypad

    Demonstrates the simplest use of the matrix Keypad library.

```Cpp
#include <Keypad.h>

const byte ROWS = 4;
const byte COLS = 3;
char keys[ROWS][COLS] = {
  {'1','2','3'},
  {'4','5','6'},
  {'7','8','9'},
  {'*','0','#'}
};
byte rowPins[ROWS] = {5, 4, 3, 2};
byte colPins[COLS] = {8, 7, 6};

Keypad keypad = Keypad( makeKeymap(keys), rowPins, colPins, ROWS, COLS );

void setup(){
  Serial.begin(9600);
}

void loop(){
  char key = keypad.getKey();

  if (key){
    Serial.println(key);
  }
}
```

## Contributing

If you want to contribute to this project:

- Report bugs and errors
- Ask for enhancements
- Create issues and pull requests
- Tell others about this library
- Contribute new protocols

Please read [CONTRIBUTING.md](https://github.com/Chris--A/Keypad/blob/master/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Credits

The authors of this library are M. Stanley and A. Brevig. This library is maintained by [Community](https://github.com/Chris--A/Keypad)

Based on previous work by:

- C. Andrews
- P. Stoffregen

## Current stable version

**version:**  v3.1.1

## License

This library is licensed under [GNU General Public License v3.0](https://github.com/Chris--A/Keypad/blob/master/LICENSE).
