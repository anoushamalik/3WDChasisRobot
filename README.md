
# 3WD Robotic Chassis Car using AVR_32 Microcontroller

## Project Overview

This project involves building and programming a 3-wheel-drive (3WD) robotic chassis car using the AVR_32 microcontroller. The car is designed to move in a straight line until an obstacle is detected, at which point it changes direction to avoid the obstacle. The project utilizes various sensors to detect obstacles and trigger the necessary actions.

## Features

- **Obstacle Detection**: The robotic car is equipped with sensors to detect obstacles in its path.
- **Automatic Direction Change**: Upon detecting an obstacle, the car automatically changes direction to avoid it.
- **LED Indicators**: LEDs are used to indicate the status of the car, such as moving forward, backward, or turning.
- **Buzzer Alert**: The buzzer is activated when the car encounters an obstacle.
- **Interrupt Handling**: The project uses interrupts to handle obstacle detection efficiently.

## Components Used

- **AVR_32 Microcontroller**: The brain of the robotic car, responsible for processing sensor inputs and controlling the motors.
- **3WD Robotic Chassis**: The structure of the robotic car, featuring three wheels driven by motors.
- **Sensors**: Used for detecting obstacles and triggering interrupts.
- **LEDs**: Indicate different states of the robotic car.
- **Buzzer**: Provides audible alerts when an obstacle is detected.
- **Motors**: Drive the wheels of the car, allowing it to move forward, backward, and turn.

## Code Explanation

The provided code is written in C and is designed to be loaded onto the AVR_32 microcontroller. Below is a brief explanation of the key parts of the code:

- **Initialization**: 
  - The pins for the LEDs, motors, and sensors are configured.
  - External interrupts are set up to handle obstacle detection.

- **Main Loop**:
  - The car moves forward as long as no obstacle is detected by `SENSOR3`.
  - When an obstacle is detected by `SENSOR3`, the car stops, moves backward, and turns to avoid the obstacle.

- **Interrupt Service Routine (ISR)**:
  - The ISR is triggered when an obstacle is detected by `SENSOR1`.
  - The car stops, toggles the LEDs, activates the buzzer, and moves the firing motor for a short duration before resuming its forward movement.

## Usage

1. **Setup**: Assemble the 3WD robotic chassis and connect the components as per the pin configurations defined in the code.
2. **Upload Code**: Compile and upload the provided code to the AVR_32 microcontroller.
3. **Power On**: Power on the robotic car, and it should start moving forward.
4. **Obstacle Detection**: The car will automatically change direction when an obstacle is detected.

## Future Improvements

- **Sensor Optimization**: Implement more sophisticated sensor algorithms to improve obstacle detection.
- **Advanced Movements**: Introduce more complex movements such as U-turns or circular paths.
- **Wireless Control**: Add wireless control to manually guide the car when needed.

## Conclusion

This project demonstrates the use of the AVR_32 microcontroller in building a basic autonomous robotic car. The project can be further enhanced by adding more sensors, optimizing the movement algorithms, and incorporating wireless control.

## Contributing

Feel free to contribute to this project by submitting issues or pull requests. Any improvements to code optimization, sensor handling, or additional features are welcome.

## License

This project is open-source and available under the MIT License. See the [LICENSE](./LICENSE) file for more details.
