# IES Code System

This repository contains the code for the Intelligent Evacuation System (IES). The system uses a Raspberry Pi 3 shield with various sensors to detect hazardous conditions and initiate an evacuation procedure.

## Dependencies

The code uses the following Python libraries:
- PCF8591
- RPi.GPIO
- time
- LCD1602
- playsound
- telepot
- pydub

## Setup

1. Clone this repository to your Raspberry Pi.
2. Install the required Python libraries.
3. Run the script.

## How it Works

The script continuously monitors the readings from the gas and flame sensors. If the readings exceed a certain threshold, the system activates the evacuation procedure. This includes sending a message to a Telegram bot, activating an alarm, and displaying a message on an LCD screen.

## Contact

If you have any questions or issues, feel free to reach out.
///////////////////////////////////////////////////////////////////////
# People Counter System

This repository contains the code for a people counter system. The system uses the YOLO model for object detection and tracking to count the number of people entering and exiting a room.

## Dependencies

The code uses the following Python libraries:
- cv2
- pandas
- ultralytics
- tracker
- cvzone

## Setup

1. Clone this repository to your machine.
2. Install the required Python libraries.
3. Run the script.

## How it Works

The script continuously captures frames from a video file and uses the YOLO model to detect people in each frame. It then tracks each person and counts the number of people entering and exiting the room based on their movement.

## Contact

If you have any questions or issues, feel free to reach out.

//////////////////////////////////////////////////////////////////////////////////////////
IES
Project Summary: Intelligent Evacuation System (IES)

The Intelligent Evacuation System (IES) is an innovative project designed to revolutionize traditional evacuation systems in buildings, with a primary focus on enhancing safety during emergencies. Acknowledging the critical role of swift and accurate evacuations, the project aims to reduce the approved evacuation time, employing cutting-edge technologies and artificial intelligence (AI).

	Key Components and Technologies:
•	Sensors: The system incorporates advanced sensors for detecting toxic gases, fires, and electrical contacts, providing real-time information during emergencies.
•	AI Algorithm (YOLO V3): Utilizing the YOLO V3 algorithm, the IES conducts 24/7 video analysis to count the number of individuals within a building, facilitating efficient crowd management during evacuations.
•	Portable Device: A key innovation is the design of a portable device housing both the CCTV system and evacuation components. This device offers a consolidated solution applicable to diverse settings such as schools, hospitals, malls, and more.

	Objectives:
•	Reduced Evacuation Time: The project aims to decrease the approved evacuation time from two minutes to a minute and a half, ensuring swift responses to emergencies.
•	Real-time Notifications: Integrating a Telegram program supported by Python, the IES provides real-time notifications to the Security and Safety Committee in the event of fires or toxic gas emissions.
•	Comprehensive Video Analysis: The YOLO V3 algorithm enables continuous video analysis, offering detailed insights into the number of occupants and potential hazards.

	Research Problem and Significance:
The project addresses the critical issue of traditional evacuation systems contributing to tragic outcomes in emergencies. By introducing the IES, the team seeks to minimize delays in detecting individuals within large buildings, ultimately saving lives.

	Innovation and Integration:
The IES combines AI, sensors, and a portable device to create an intelligent evacuation system. The integration of front-end information acquisition and intelligent fire alarming enhances the system's capabilities beyond traditional approaches.

	Engineering Design and Implementation:
The prototype design illustrates the system's configuration, and the implementation phase involves testing and refining the components. Challenges include precision in component connection and the time-consuming nature of design.

	Results and Future Implications:
Initial testing demonstrates a significant reduction in evacuation time, from two minutes to one minute. The video analysis capability and real-time notifications contribute to efficient emergency management. The future implications include further refinement of the system, scalability considerations, and potential applications in various settings.

	Conclusion:
The Intelligent Evacuation System presents a promising solution to the challenges of traditional evacuation systems. By leveraging AI and advanced technologies, the IES endeavors to create a safer environment in buildings during emergencies, ultimately saving lives and minimizing the impact of unforeseen events.

	Project Team: Saeed Al-Marri & Ghaleb Shajea – Supervisor :Eng.Ahmad Tubaishat – Qatar Science & Technology School for Boys
