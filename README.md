# Digital-Number-Display-Using-Arduino
![image](https://github.com/user-attachments/assets/99f16840-2b6c-4b61-a4c1-dfc16760a4ba)
Here is a README template for your GitHub repository based on the "Digital Number Display Using Arduino" project built using Proteus:

---

# Digital Number Display Using Arduino

This repository contains the implementation of a **Digital Number Display** using an Arduino Uno and a 7-segment display simulated in Proteus. The project demonstrates how to control a 7-segment display to display numbers using the Arduino microcontroller.

---

## Project Overview

The primary goal of this project is to display numbers on a 7-segment display by interfacing it with an Arduino Uno. The Proteus simulation software is used to visualize and test the circuit. This project is ideal for beginners looking to understand the basics of Arduino programming and 7-segment display interfacing.

---

## Features

- Displays numbers on a 7-segment display (0-9 or specific numbers).
- Demonstrates the use of current-limiting resistors for safety.
- Uses Proteus for circuit simulation and design.
- Arduino Uno serves as the microcontroller.

---

## Circuit Design

### Components Used:
- **Arduino Uno**: Microcontroller for controlling the display.
- **7-Segment Display**: Common anode/cathode type (as per your design).
- **Resistors**: 330 ohms (or as required) to limit current to each segment.
- **Connecting Wires**: For connections between components.
- **Proteus Software**: For simulation and circuit design.

### Circuit Diagram:
The circuit diagram (as shown in the simulation) includes the following:
- The Arduino Uno connected to the 7-segment display via resistors.
- Each segment of the display is controlled by a digital output pin of the Arduino.
- Current-limiting resistors are placed between Arduino pins and the 7-segment display.

---

## Software Implementation

### Arduino Code:
The code uploaded to the Arduino Uno contains logic for lighting up specific segments of the display to form numbers. 

```cpp
// Example Code
const int segmentPins[] = {2, 3, 4, 5, 6, 7, 8}; // Arduino pins connected to segments
const byte digits[10][7] = {
  {1, 1, 1, 1, 1, 1, 0}, // 0
  {0, 1, 1, 0, 0, 0, 0}, // 1
  {1, 1, 0, 1, 1, 0, 1}, // 2
  // Add other numbers
};

void setup() {
  for (int i = 0; i < 7; i++) {
    pinMode(segmentPins[i], OUTPUT);
  }
}

void displayDigit(int digit) {
  for (int i = 0; i < 7; i++) {
    digitalWrite(segmentPins[i], digits[digit][i]);
  }
}

void loop() {
  for (int i = 0; i < 10; i++) {
    displayDigit(i);
    delay(1000);
  }
}
```

---

## How to Use

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/Digital-Number-Display-Using-Arduino.git
   ```

2. Open the Proteus design file (`.pdsprj`) in Proteus software.

3. Upload the provided Arduino code to the virtual Arduino Uno in Proteus.

4. Run the simulation to observe numbers being displayed on the 7-segment display.

---

## Applications

- Digital clocks
- Counters
- Simple display systems
- Educational projects

---

## Future Enhancements

- Display alphabets or custom characters on the 7-segment display.
- Add push buttons to control the displayed number.
- Integrate multiple displays for larger numbers.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

