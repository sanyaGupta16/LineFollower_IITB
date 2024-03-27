# Documentation for the line follower bot with Qtr Sensor

## Hardware

### Componets Required 

1. QTR sensor
2. Arduino Uno
3. Motor Driver
4. Li-ion Battery
5. Motors
6. Jumper wires
7. Chassis and wheels

### Circuit Overview
- The arduino uno board is to be connected to the motor driver and qtr sensor.
- Motor Driver is connected to the motors to control the path taken by the bot based on the controlling speeds sent to the motors by arduino uno using readings from Qtr Sensor.

## Software

### Libraries Used
- QTRSensors.h

### Setting up libraries 
1. Open the Arduino IDE.
2. In the Arduino IDE, open the <strong>Sketch</strong> menu, select <strong>Include Library</strong>, then <strong>Manage Libraries...</strong>.
3. Search for <strong>QTRSensors</strong> in the search bar1.
4. Click the <strong>QTRSensors</strong> entry in the list1.
5. Click the <strong>Install</strong> button to install the library

### PID Controller Algorithm 
- The QTR sensor array can provide values ranging from 0 to 7000, with 3500 representing the line being directly under the center of the robot. The sensor provides information on how far the robot has strayed from the line.
- The PID controller algorithm uses this information to calculate an error value as the difference between the robot’s current position and its desired position on the line. The controller then applies a correction to the robot’s movement based on this error value, using the proportional, integral, and derivative terms.
- The proportional term is based on the current error value and determines how much the robot should turn to correct its position.
- The integral term takes into account past errors and helps to reduce steady-state error. 
- The derivative term predicts future errors based on the rate of change of the error value and helps to reduce overshooting.
- By adjusting the gains of these three terms, the PID controller is tuned to provide smooth and accurate movement of the line follower robot along the line
