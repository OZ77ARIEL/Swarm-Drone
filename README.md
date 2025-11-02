Project Summary
The project involved developing a Python library designed to command a drone swarm to fly a path defined by an uploaded drawing or image. The code automatically processes the drawing, breaking the desired path into a series of discrete movement segments. It then scales these segments to the desired real-world size (in centimeters) and transmits the movement commands to the drones.

The core innovation is the system's ability to perform self-localization and real-time motion correction. It uses the drones' on-board cameras to identify a known reference object in the environment (such as a green square placed on a wall). This visual data allows the system to calculate the drones' absolute position in space and correct any deviations from the planned trajectory dynamically. The drones' real-time locations are updated in a database and visualized simultaneously in a Python simulation and an external monitoring application (smartphone).

✨ Key Features
Image-Based Path Planning: Takes a visual input (a drawing) and automatically converts it into a flight path, segmented into executable steps.

Visual-Based Navigation:

Utilizes the drone's camera to identify a green square as a spatial reference point.

Calculates the drone's self-position and orientation in the environment.

Corrective Motion Control (Self-Correction): Dynamically corrects for deviations from the planned path during the subsequent movement commands (as demonstrated at in the video).

Resolution Awareness: The system accounts for the technical constraint where the drones cannot accept a movement command smaller than 20 centimeters, setting the practical resolution limit of the path.

Dual Visualization: Drone movement is displayed in a graphical Python simulation and concurrently in an external monitoring application (like Raven) by reading data from the shared database.

🛠️ Architecture and Key Components
Python Control Library:

Input: Receives the path drawing image and the desired scale size (cm).

Processing: Segments the path and performs coordinate scaling.

Localization: Executes image processing algorithms to identify the green square and calculate the drone's position.

Database (Base Code): Continuously updates and stores the real-time location data of the drones.

Drone Array:

Drones that execute the flight commands.

On-board cameras provide the visual input for the localization algorithm.

Monitoring Application:

An external application (e.g., a smartphone app like Raven) reads the location data from the database and displays the swarm's position in real-time for monitoring purposes.

🎬 Preview
For a full explanation and demonstration of the project in action, watch the video:

Swarm of Drones Project - Explanation Video

👥 Authors
This project was developed by:

Oz Ariel (@OZ77ARIEL)

Arnold Cheskis

Supervised by Ofer Danino.
