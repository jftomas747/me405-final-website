# ME405 Final Project - MECH13

This website contains Team MECH13’s final ME405 project documentation, source code, and mechanical/electrical maps for our Romi robot obstacle-course project.

## Team Members
- Kaden Guevarra
- John Tomas

## Project Information
- **Course:** ME405
- **Due Date:** March 20, 2026
- **Project Type:** Final Project

## Project Overview
This project combines the work completed throughout the ME405 labs into one final Romi robot system capable of navigating an obstacle course. Our final robot integrates motors and encoders, line sensors, IMU-based state estimation, and bump sensors. We also included LED lights, although they were not used in a meaningful way for the final performance.

## Objectives
The objective of this final project was to combine all major systems developed during the quarter into one complete Romi robot capable of finishing the obstacle course. To do this, we integrated motor control, encoder feedback, line following, IMU-based turning logic, and bump sensing into a single working system.

## Mechanical and Electrical Design
We began with the standard ME405 Romi kit, which included the Romi chassis, motors, encoders, wheels, casters, BNO055 IMU breakout board, modified Shoe of Brian, and Nucleo L476RG. We assembled these components according to the lab instructions and then added our own sensors.

We installed a QTRX-MD-07A reflectance sensor array at the front underside of the robot using stand-offs so that it would sit just above the ground for reliable line detection. We also installed right and left bumper switch assemblies at the front of the robot to detect wall contact while protecting the line sensor from impact.

For wiring, we used a common ground system. Board power was connected through VIN and GND. The right motor was wired to PA1 and PA0, and the left motor was wired to PA8 and PA9. The right encoder was connected to PB6, PA7, and PA6, while the left encoder was connected to PB4, PB5, and PB3. The line sensor was connected to PC3, PC2, PC0, PC1, PB0, PA4, PC4, GND, and 3V3. The IMU was connected through PB9 (SCL), PB8 (SDA), GND, and 3V3. The right bump sensor used PB15, PB14, and PB13, while the left bump sensor used PC8, PC6, and PC5.

## Photo of the Romi
![Romi Robot](https://github.com/user-attachments/assets/59b8538a-9f08-433e-8024-1bff118f0d29)

## Wiring Map
[Wiring Map Excel File](https://cpslo-my.sharepoint.com/:x:/r/personal/ktguevar_calpoly_edu/Documents/FINAL_ROMI_WIRINGMAP.xlsx?d=wce03223d2b894929a85aa045309b94bb&csf=1&web=1&e=eps5Vk)

## Results
During our demonstration, the robot completed the course successfully 1 out of 3 attempts. Before the official demonstration, it completed the course 3 times in a row. However, due to external issues, we had to make last-minute calibration adjustments that reduced consistency.

Our system relied mainly on the line sensor and encoder ticks, while state estimation was primarily used during turning sections when no line was available to follow. Our fastest overall completion time was just under 2 minutes, and our fastest official run was approximately 2 minutes, as shown in the video below.

Some of the biggest challenges we faced were heading control, state-estimation calibration, and making repeatable turns. Since we could not fully stabilize the robot’s heading, it was difficult to maintain a perfectly straight path, especially because the right motor consistently ran slightly faster than the left. We compensated by strengthening the line-following behavior, but this made sections without a visible line more difficult to execute consistently. Despite these issues, we are proud of how our robot performed and of the progress we made in integrating multiple subsystems into one final design.

## Video Demonstration
[Watch the Romi Demo](https://youtu.be/V55OzWEsSkU)

## Code Documentation
The following source files are included in this project:

- bump_sensor.py
- cotask.py
- encoder.py
- estimator.py
- imu_driver.py
- linesensor_driver.py
- main.py
- motor_driver.py
- multichar_input.py
- task_bump.py
- task_estimator.py
- task_motor.py
- task_navigator.py
- task_share.py
- task_start_button.py
- task_user.py

## File Structure / Reproduction
These files can be flashed to a Romi built to match our hardware setup in order to recreate our project. After uploading the classes and tasks, the user can either run `main.py` and follow the user interface to enter values manually, or use the built-in calibration values already stored in our code. Using the user button allows the robot to run with our premeasured calibration values.
