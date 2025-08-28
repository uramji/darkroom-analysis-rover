# darkroom-analysis-rover
autonomous rover designed to navigate in complete darkness, map its environment, detect and count objects, and measure key environmental data. The robot uses a Raspberry Pi as its brain and is built on the Robot Operating System (ROS) framework.
# Dark Room Analysis Rover

An autonomous rover designed to navigate in complete darkness, map its environment, detect and count objects, and measure key environmental data. The robot uses a Raspberry Pi as its brain and is built on the Robot Operating System (ROS) framework.

![Dark Room Analysis Rover](https://i.imgur.com/your-project-image-link-here.jpg)
*Replace this image link with a picture or render of your finished robot.*

## 🤖 Features
- **Autonomous Navigation & SLAM:** Creates a 2D occupancy grid map of a room using LiDAR, all in zero-light conditions.
- **Object Detection:** Identifies and counts the number of distinct objects in the mapped area.
- **Environmental Sensing:** Measures and reports real-time data on temperature, pressure, and gas levels.
- **Light Intensity Detection:** Confirms the darkness of the environment with a sensitive light sensor.
- **Wireless Dashboard:** Streams all data and the generated map to a user-friendly web interface accessible via Wi-Fi.

## 🛠️ Hardware Components
This table lists the core components required to build the rover.

| Component             | Model                  | Purpose                               |
| --------------------- | ---------------------- | ------------------------------------- |
| **SBC** | Raspberry Pi 4 Model B | Main computer, runs all software      |
| **Mapping Sensor** | RPLIDAR A1M8           | 360° LiDAR for SLAM and mapping       |
| **Environment Sensor**| BME280                 | Measures temperature, pressure, humidity|
| **Gas Sensor** | MQ-2                   | Detects smoke, LPG, and carbon monoxide|
| **Light Sensor** | BH1750                 | Measures ambient light intensity (Lux)|
| **Motor Driver** | L298N                  | Controls the speed and direction of motors|
| **Chassis & Motors** | 4WD Robot Kit          | Provides the physical body and mobility|
| **Power Source** | 2S LiPo Battery (7.4V) | Powers all robot components           |

## 💻 Software & Dependencies
The software stack is built on ROS (Robot Operating System). All code is written in Python.

### Prerequisites
- **Operating System:** Raspberry Pi OS (64-bit)
- **Framework:** ROS Noetic

### Setup & Installation
1.  **Clone the repository to your Raspberry Pi:**
    ```bash
    git clone [https://github.com/YOUR_USERNAME/darkroom-analysis-rover.git](https://github.com/YOUR_USERNAME/darkroom-analysis-rover.git)
    ```
2.  **Install ROS and Python dependencies:**
    *(Navigate to the `scripts` folder and run the installation script. This script will handle `apt` and `pip` dependencies.)*
    ```bash
    cd darkroom-analysis-rover
    bash scripts/install_deps.sh
    ```
3.  **Build the ROS workspace:**
    ```bash
    cd ros_ws
    catkin_make
    ```

## ▶️ Usage
1.  **Launch the robot:**
    Ensure all hardware is connected and powered on. Open a terminal on the Raspberry Pi and run the main launch file.
    ```bash
    # Source the workspace environment
    source ~/darkroom-analysis-rover/ros_ws/devel/setup.bash

    # Launch the main robot node
    roslaunch rover_bringup rover.launch
    ```
2.  **Access the web dashboard:**
    From a computer or smartphone on the same Wi-Fi network, open a web browser and navigate to the robot's IP address on port `5000`.
    ```
    http://<robot_ip_address>:5000
    ```
    You will see a live view of the map, object count, and real-time sensor data.
