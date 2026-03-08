# FSM-based Autonomous Lane Change System

## Overview

This project implements an autonomous lane change system for a mini electric vehicle.

The system detects lanes and obstacles using camera-based perception and performs safe lane changes using a Finite State Machine (FSM) decision algorithm.

Key features:
- Lane detection
- Obstacle detection using YOLO
- FSM-based lane change decision
- Autonomous lane recovery

---

## Hardware Platform

The autonomous driving system is implemented on a mini electric ride-on vehicle platform.

### Vehicle Platform
- Ride-on electric vehicle body
- Drive motor
- Steering motor
- Wheels
- Battery

### Control Unit
- Arduino microcontroller
- Potentiometer (steering control)

### Sensors
- Camera: YOLO-based lane and vehicle detection. The image Y-coordinate is used to estimate the distance to the detected vehicle.
- LiDAR: Used for accurate distance measurement to the obstacle vehicle.

---

## System Architecture
```
Sensor
(Camera)
    ↓
Perception
(Lane Detection, YOLO Detection)
    ↓
Decision Making
(FSM)
    ↓
Control
    ↓
Actuation
(UART Motor Control)
```
## Algorithm

The lane change decision is implemented using a Finite State Machine (FSM).

States:

The FSM consists of the following states:

1. **Normal Driving**  
   The vehicle follows the current lane during normal autonomous driving.

2. **Preparing to Change Lane**  
   When an obstacle is detected ahead, the system evaluates the adjacent lane and prepares for a lane change.

3. **Changing Lane**  
   The vehicle performs a lane change maneuver to avoid the obstacle.

4. **Overtaking**  
   The vehicle continues driving in the adjacent lane while passing the obstacle.

5. **Returning Lane**  
   After passing the obstacle, the vehicle safely returns to the original lane.

The vehicle changes lanes when an obstacle is detected and returns to the original lane after passing the obstacle.

---

## Experimental Scenarios

To evaluate the autonomous lane change system, three driving scenarios were designed.

1. **Normal Driving**  
The vehicle follows the lane without obstacles.

2. **Obstacle Avoidance**  
When an obstacle is detected in the current lane, the system performs a lane change maneuver.

3. **Lane Recovery**  
After overtaking the obstacle, the vehicle safely returns to the original lane.

---

## Results

The autonomous driving system successfully demonstrated the following capabilities:

- Stable lane following
- Obstacle detection using LiDAR and camera
- Safe lane change using FSM-based decision logic
- Autonomous return to the original lane

## Repository Structure
```
fsm-lane-change-system
├── src
│ └── autonomous_lane_change
│ ├── perception
│ ├── decision
│ └── control
├── launch
├── config
└── README.md
```
