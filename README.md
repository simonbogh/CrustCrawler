# CrustCrawler

A robotic arm control system for the CrustCrawler robot with gesture-based control using Myo armband.

## Overview

This project implements a complete control system for a CrustCrawler robotic manipulator, featuring:
- Real-time kinematics and dynamics calculations
- PID-based velocity control
- Gesture-based control via Myo armband EMG sensors
- Serial communication between PC and Arduino controller

## Architecture

The system consists of two main components:

### Arduino (Robot Controller)
- **Controller**: Main control loop coordinator
- **Kinematics**: Forward kinematics implementation
- **Dynamics**: Inverse dynamics for torque calculation
- **Control System**: PID controller for joint velocity tracking
- **Dynamixel Connection**: Interface with Dynamixel servo motors
- **Computer Connection**: Serial communication with PC

### Computer (User Interface)
- **MyoBand**: Interface with Myo armband for gesture recognition and EMG data
- **Filter**: Signal processing for EMG data
- **SerialLink**: Serial communication with Arduino

## Project Structure

```
CrustCrawler/
├── Arduino/              # Arduino controller code
│   ├── lib/              # Libraries (Dynamixel, BasicLinearAlgebra)
│   └── *.cpp/*.h         # Control system implementation
├── Computer/             # PC interface application
│   ├── lib/              # Myo SDK and serial library
│   └── main.cpp          # Main application entry
├── Inverse Dynamics/     # Mathematical models (Maple worksheet)
└── CrustCrawler.sln      # Visual Studio solution
```

## Requirements

### Hardware
- CrustCrawler robotic manipulator
- Arduino board (with DynamixelShield)
- Dynamixel servo motors
- Myo armband
- Windows PC

### Software
- Visual Studio (for Computer application)
- Arduino IDE (for Arduino firmware)
- Myo SDK (Windows)

## Operating Modes

The system supports two operating modes (configured in `DynamixelConnection.h`):
- **Velocity Mode**: Direct velocity control
- **PWM Mode**: Torque-based control using PWM signals

## Build

### Arduino
1. Open `Arduino/Arduino.ino` in Arduino IDE
2. Install required libraries from `Arduino/lib/`
3. Upload to Arduino board

### Computer
1. Open `CrustCrawler.sln` in Visual Studio
2. Build the solution
3. Configure COM port in `main.cpp` (default: COM4)
4. Run the application

## Usage

1. Upload Arduino firmware to the controller
2. Connect Myo armband to PC
3. Start the Computer application
4. Use gestures to control the robot
5. Press ESC to exit

## License

This project is provided as-is for educational and research purposes.
