##Qatar Sciense & Technology school for boys - Ghaleb shaje - saeed almari - supervisor:Eng.Ahmad Tubaishat
# IES Code System

## Introduction
The **Intelligent Evacuation System (IES)** is designed to enhance the efficiency and effectiveness of evacuation processes in buildings during emergencies, such as fires, gas leaks, and earthquakes. The system integrates advanced technologies, including artificial intelligence (AI), sensors, and communication modules, to provide real-time monitoring, detection, and notification capabilities.

## Components
The system utilizes a Raspberry Pi 3 shield, which serves as the central hub for connecting various components. The key components include:
1. Flame Sensor: Detects the presence of fire or flames.
2. CO2 Sensor: Monitors and detects the concentration of carbon dioxide.
3. MQ2 and MQ9 Sensors: Gas sensors for detecting various gases, including toxic ones.
4. LEDs: Provide visual indicators for system status, with different colors representing different states.
5. USB Camera: Used for video analysis using the YoloV3 algorithm to count the number of people in the building.
6. LCD Screen: Displays relevant information about the system's status.
7. Telegram Bot: Linked to the Python program, sending notifications to the Security and Safety Committee.
8. Audio Output: Utilizes sound alarms for immediate attention.

## Operation
The system continuously monitors environmental conditions, and in the event of an emergency, it activates the evacuation process. The YoloV3 algorithm analyzes video footage to count the number of people in the building, providing crucial information for evacuation management. The integration with Telegram allows for instant notifications to the Security and Safety Committee.

## Implementation
The system is designed to be portable and can be deployed in various buildings or laboratories. It aims to bridge the gap in traditional evacuation systems, providing a cost-effective and intelligent solution for a quicker and safer evacuation process.

## Acknowledgments and Dedication
This project is dedicated to those who have lost their lives in building emergencies and to the brave firefighters who risk their lives for the safety of others. It also acknowledges the significance of addressing delays in evacuation operations and aims to contribute to saving lives through innovative technologies.

## How to Use
1. Connect all components to the Raspberry Pi 3 shield.
2. Ensure proper setup of sensors and GPIO pins.
3. Run the Python program to initiate the IES.
4. Monitor the LCD screen and LED indicators for system status.
5. In case of an emergency, receive instant notifications via the Telegram Bot.

For additional details and inquiries, please refer to the project's documentation or contact the project team.

**Note:** This readme provides a brief overview; for detailed instructions and technical specifications, consult the documentation included with the project.