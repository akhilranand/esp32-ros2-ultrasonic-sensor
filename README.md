# Ultrasonic Sensor Integration with ROS 2 and ESP32

## Overview

This project demonstrates the integration of an **HC-SR04 Ultrasonic Distance Sensor with ROS 2 using an ESP32 microcontroller**.

The ESP32 reads distance measurements from the ultrasonic sensor and sends the data to a computer through serial communication. A ROS 2 Python node receives the sensor data and publishes the distance measurements to a ROS 2 topic.

This project demonstrates the integration of embedded hardware and ROS 2 for real-time distance monitoring in robotics applications.

## Features

- HC-SR04 ultrasonic distance measurement.
- ESP32-based sensor interfacing.
- Serial communication between ESP32 and Ubuntu.
- ROS 2 Python publisher node.
- Real-time distance data publishing.
- ROS 2 topic monitoring.

## Hardware Requirements

- ESP32 Development Board
- HC-SR04 Ultrasonic Sensor
- Jumper Wires
- USB Cable
- Computer running Ubuntu

## Software Requirements

- Ubuntu 22.04
- ROS 2 Humble
- Python 3
- Arduino IDE
- PySerial

## Project Structure

```text
Ultrasonic-Sensor-with-ROS2/
│
├── esp32_ultrasonic_test1/
│   └── ESP32 ultrasonic sensor code
│
├── src/
│   └── esp32_distance/
│       └── ROS 2 Python package
│
└── .gitignore
```

## Working Principle

1. The HC-SR04 sensor sends ultrasonic waves through its Trigger pin.
2. The Echo pin receives the reflected signal.
3. The ESP32 calculates the distance based on the time taken by the ultrasonic wave.
4. The measured distance is transmitted to the computer through USB serial communication.
5. The ROS 2 Python node reads the incoming serial data.
6. The node publishes the distance measurement to a ROS 2 topic.

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/akhilranand/Ultrasonic-Sensor-with-ROS2.git
```

### 2. Navigate to the Workspace

```bash
cd Ultrasonic-Sensor-with-ROS2
```

### 3. Install Required Dependencies

```bash
sudo apt update
sudo apt install python3-serial
```

### 4. Upload ESP32 Code

- Open Arduino IDE.
- Open the ESP32 ultrasonic sensor code.
- Select the appropriate ESP32 board and port.
- Upload the program to the ESP32.

### 5. Connect ESP32

Connect the ESP32 to your Ubuntu computer using a USB cable.

Check the serial device:

```bash
ls /dev/ttyACM*
```

### 6. Build the ROS 2 Package

Source ROS 2 Humble:

```bash
source /opt/ros/humble/setup.bash
```

Build the workspace:

```bash
colcon build
```

Source the workspace:

```bash
source install/setup.bash
```

### 7. Run the ROS 2 Node

```bash
ros2 run esp32_distance distance_node
```

*Note: The executable name and workspace directory should match the actual package configuration.*

## Monitoring Sensor Data

Check available ROS 2 topics:

```bash
ros2 topic list
```

Monitor the distance measurements:

```bash
ros2 topic echo /distance
```

Check the publishing rate:

```bash
ros2 topic hz /distance
```

## Applications

- Obstacle detection in mobile robots.
- Distance monitoring systems.
- Robotics sensor integration.
- Embedded systems and ROS 2 communication.
- Autonomous robot development.

## Learning Outcomes

- Interfacing ultrasonic sensors with ESP32.
- Understanding serial communication.
- Developing ROS 2 Python publisher nodes.
- Publishing real-time sensor measurements.
- Integrating embedded hardware with ROS 2.

## Technologies Used

`ROS 2 Humble` `Python` `ESP32` `HC-SR04` `Arduino IDE` `Ubuntu 22.04`

## Author

**Akhil R Anand**

Robotics and Automation Engineer

[GitHub Profile](https://github.com/akhilranand)