
### 3WD Chassis Control System

This project is an embedded C program designed to control a 3-wheel drive (3WD) chassis using an AVR microcontroller. The system moves the chassis forward and automatically turns it right or left when it detects an obstacle. The program uses sensors to detect obstacles and controls motors, LEDs, and a buzzer to perform necessary actions.

### Features

- **Forward Motion:** The chassis moves forward by default.
- **Obstacle Detection:** When an obstacle is detected by the sensors, the system stops, alerts with a buzzer, and then performs a 90-degree right or left turn.
- **LED Indicators:** LEDs indicate the current state of the chassis (e.g., moving forward, turning).
- **Interrupt Handling:** External interrupts are used to detect obstacles and trigger appropriate responses.

### Hardware Requirements

- AVR Microcontroller (e.g., ATmega16/32)
- 3WD Chassis with motors
- IR Sensors or Ultrasonic Sensors for obstacle detection
- Buzzer for audible alerts
- LEDs for visual indicators
- Power Supply for the microcontroller and motors

## Pin Configuration

- **PD1**: Motor Control Pin
- **PD0**: Buzzer Control Pin
- **PD2**: Sensor 1 (Obstacle Detection)
- **PC4**: Sensor 3 (Obstacle Detection)
- **PC0 - PC3**: LED Indicators

## Code Overview

### Main Loop

The main loop of the program continuously checks the state of the obstacle sensors:

- If no obstacle is detected, the chassis moves forward, and LEDs 1 and 2 are turned on.
- If an obstacle is detected, the chassis stops, turns on LEDs 3 and 4, sounds the buzzer, and then performs a 90-degree turn.

### Interrupt Service Routine (ISR)

- The ISR for `INT0` is triggered when an obstacle is detected by Sensor 1.
- It stops the chassis, toggles the LEDs, and activates the firing motor.

### Libraries Used

- `<avr/io.h>`: Provides access to I/O registers for the AVR microcontroller.
- `<util/delay.h>`: Allows for delay functions in milliseconds.
- `<avr/interrupt.h>`: Manages interrupt handling.

## Usage

1. **Compile the Code:** Use AVR-GCC or another compatible compiler.
2. **Upload to Microcontroller:** Use an AVR programmer to upload the compiled code to your microcontroller.
3. **Power Up the System:** Connect the power supply to the microcontroller and motors.
4. **Observe the Behavior:** The chassis should move forward and turn when obstacles are detected.

## Customization

- **Adjusting Turn Timing:** Modify the `_delay_ms()` values to adjust the duration of the turn.
- **Sensor Sensitivity:** You can change the sensor configuration to adjust the sensitivity for obstacle detection.
- **LED Behavior:** Customize the LED indicators by changing the PORTC assignments.

## Contributing

Feel free to contribute to this project by submitting issues or pull requests. Any improvements to code optimization, sensor handling, or additional features are welcome.

## License

This project is open-source and available under the MIT License. See the LICENSE file for more details.

---

This `README.md` provides an overview of your project, guiding users on how to understand, use, and contribute to the code.
