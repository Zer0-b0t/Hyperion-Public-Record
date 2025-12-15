# VRC Autonomous Path Planning Engine

### An Educational Tool for VEX Robotics Competition Teams

![VEX](https://img.shields.io/badge/VEX-V5-red) ![MadeBy](https://img.shields.io/badge/madeby-SBK-blue) ![Version](https://img.shields.io/badge/version-4.0.0-brightgreen) ![License](https://img.shields.io/badge/license-CC%20BY--NC--ND%204.0-lightgrey) 

> **A comprehensive All-in-one code generation platform designed to accelerate learning and competition readiness for VRC teams of all (but aimed specially for teams with low experience) experience levels.**

[**Launch Application**](https-gonna-put-a-link-here-DONT-FORGET) | [**Report Issues**](mailto:fekasbhy@gmail.com)

---

## Motivation

The VRC Autonomous Engine was developed by Team 46262X to address common challenges faced by robotics teams during autonomous programming:

- **Autonomation** - While VRC code is easy for me, it was still time consuming to calculate everything by hand when anything changed.
- **Steep Learning Curve** – As a conclusion of my pre development surveys, new teams often struggle on autonomous programmings because of steep steps of VRC code learning
- **Time Constraints** – Because the programmers mostly had access to the final robot for maybe only a few days before competetion, we had to make sure we had enough preperation for these few days to make a working Auton program.
- **Visualize** – Even if our code was great, we needed a way to visualize what our robot will do so we won't have to run our program each time we change something to see if it exceeds or conflicts with field or it's elements
- **Small Community** - Compared to FRC, VRC community especially in Turkey is quite small with most teams don't help to not give their possible opponents

### Solution Architecture

This platform provides:

- **Automated Code Generation** – Production-ready VEXcode V5 output without manual coding
- **Transparent Calculations** – All mathematical conversions are documented and editable
- **Progressive Learning** – Educational framework that teaches concepts through practical application
- **Competition Focus** – Allows teams to prioritize strategy development over syntax debugging
- **Fast and True** - Calculates copy-and-upload codes that require zero to minimal editing.

---

## Getting Started

### Prerequisites
- VEXcode V5 installed on your computer
- VEX V5 Brain and controller
- MicroUSB cable with data-upload to upload the code
- A VRC Robot
- A will

### Basic Workflow

**1. Robot Configuration**
   - Input robot dimensions, motors and robot-specific elements
   - Specify ports
   - Define wheel diameter and gear ratios

**2. Path Planning**
   - Set starting position on field
   - Add waypoints by entering their coordinates
   - Adjust speeds 

**3. Code Generation & Deployment**
   - Review generated code
   - Copy to VEXcode V5 project
   - Upload to robot and test

---

## Code Structure

### Command-Based Architecture

**Drive Function**
```cpp
void drive(double cm, int vel = 85) {
    double targetDeg = (cm * 1.0) * 11.46;
    lg.spinFor(fwd, targetDeg, degrees, false);
    rg.spinFor(fwd, targetDeg, degrees, true);
}
```
Transforms field coordinates into **command-based motor control**:
- **Input**: Distance in centimeters
- **Conversion**: Applies wheel circumference and gear ratio calculations
- **Output**: Centimeters -> Required motor rotation
- **Result**: Precise linear movement

**Rotate Function**
```cpp
void rotate(double deg) {
    double motorDegrees = (deg * 1.0) * 8.73;
    rg.spinFor(fwd, motorDegrees * -1, degrees, false);
    lg.spinFor(fwd, motorDegrees, degrees, true);
}
```
Converts turn angle to differential motor rotation based on robot width using the **command-based pattern**.

**Autonomous Routine**
```cpp
void autonomous() {
    drive(120.5, 85);     // Command: Move forward
    wait(75, msec);       // Command: Pause
    rotate(45.0);         // Command: Turn
}
```
High-level **command-based sequencing** (which is preferred method in large applications) generated from visual waypoint planning—no low-level motor math required.

---

## Educational Value

**Core Concepts Covered:**
- Motor control and motor group configuration
- Kinematic calculations (distance, rotation, velocity)
- Autonomous routine sequencing
- Code modularity and best practices
- Turning standart VRC codes into Command Based codes which users can inspire upon
  
---

## Features

**Code Generation**
- Visual path planning interface
- Real-time error validation
- Universal robot configuration support
- Documented calculation formulas

**Educational Tools**
- Annotated code output
- Command Based output architecture
- Progressive complexity options
- Advanced control algorithms (PID, Bezier curves)

---

## Path Generation Types

Multiple algorithm options available:
- **Pure Pursuit** – Simple path following
- **PID Control** – Precision movement control
- **Bezier Curves** – Smooth curved trajectories *(in development)*
- **Another cool curve formula** - *will add soon*

---

## Troubleshooting

| Issue | Cause | Solution |
|-------|-------|----------|
| **Inaccurate distance** | Wheel slippage, friction variance | Adjust friction multiplier in configuration |
| **Wrong rotation direction** | Reversed motor polarity | Enable "Reverse" option for affected motors |
| **Inaccurate turns** | Incorrect robot width measurement | Remeasure wheelbase and update configuration |
| **It still isn't working** | Insufficient Info | I couldn't try this site throguhly on other teams robots, which you will have to mail me your robot details so I can fix both your code and my site |

---

## Competition Guidelines

**Pre-Competition:**
- Validate on practice field surface
- Maintain consistent battery charge (80-90%)
- Verify robot dimensions with installed mechanisms
- Prioritize reliable routines over complex strategies
- Take the friction into account because it is impossible to calculate without knowing the robot.

**Setup Procedures:**
- Precise starting position alignment
- Verify robot orientation
- Confirm autonomous mode selection
- Make some testing drives and edit the Friction Coefficient

**Calibration Parameters:**
```cpp
frictionCoefficient = 1.0; // Change only if you know what you are doing
```

---

## Roadmap

**Current Release (v4.0.0):**
- Multiple path generation algorithms
- Complete controller mapping
- Collision detection system
- Velocity profile visualization

**Planned Features:**
- Interactive waypoint editing
- Undo/redo functionality
- Mobile platform support
- Enhanced UI/UX improvements
- Velocity Graphs more realistic

---

## Feedback & Support

**Contact:**
- Email: fekasbhy@gmail.com
- Instagram: @serdar_burak_karagoz

We welcome feedback, bug reports, and success stories from teams using this platform.

---

## Credits

**Developer:** SBK - Team 46262X

**Acknowledgments:**
- VEX Robotics Competition platform
- ChatGPT for fixing variable names to something more commercially acceptable
- My teammates for Beta testing
- Open-source community
- ChatGPT again for CSS animations
- ChatGPT one last time for fixing all function names which were quite unprofessional

---

## License

### Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International

Copyright © 2025 SBK

This work is licensed under [CC BY-NC-ND 4.0](http://creativecommons.org/licenses/by-nc-nd/4.0/).

**Terms:**
- ✅ Share and redistribute with attribution
- ✅ Educational and non-commercial use
- ❌ No modifications or derivative works
- ❌ No commercial applications

For permissions beyond this license, contact: fekasbhy@gmail.com

[![CC BY-NC-ND 4.0](https://licensebuttons.net/l/by-nc-nd/4.0/88x31.png)](http://creativecommons.org/licenses/by-nc-nd/4.0/)

**Note:** Access may be temporarily restricted during major competitions to ensure equitable participation.
