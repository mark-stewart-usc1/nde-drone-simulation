# NDE Drone Simulation

Custom PX4/Gazebo simulation platform developed for autonomous nondestructive evaluation (NDE) drone research at the University of South Carolina.

## Project Status

### Simulation Validation
- Stable Hover ✓
- Position Hold ✓
- Mission Mode ✓
- Return-To-Launch (RTL) ✓
- Custom NDE Airframe ✓
- Custom Gazebo Model ✓

## Repository Structure

### Gazebo Models

models/nde_drone
models/nde_drone_base

### PX4 Airframe

airframes/4022_gz_nde_drone

## Software Stack

- PX4 Autopilot
- Gazebo Harmonic
- QGroundControl
- Fusion 360
- ROS2 (planned)

## Key Engineering Findings

- Developed a custom PX4/Gazebo simulation model for the NDE drone.
- Validated the model against the PX4 X500 reference architecture.
- Identified mass/inertia consistency as a major factor affecting flight stability.
- Successfully achieved stable hover, mission execution, and RTL behavior.

## Future Work

- ROS2 Offboard Control
- Autonomous waypoint navigation
- Target tracking
- NDE inspection behaviors
- Orange Pi integration

## Author

Mark Stewart  
University of South Carolina
