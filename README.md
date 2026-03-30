# Fortunate Son — Competition Edition (Hardware)

Official hardware documentation, CAD repository, and Engineering Portfolio for **Fortunate Son**, a high-performance FIRST Tech Challenge robot by **Team THUNDERSTRIKE 33535**. [cite_start]This release focuses on the physical build and mechanical assembly, optimized for rigidity, precision localization, and high-speed scoring[cite: 6, 7, 8].

---

## License
This hardware and documentation are licensed under the **Creative Commons Attribution-ShareAlike 4.0 International License**. 

**Under this license, you are free to:**
* **Share:** Copy and redistribute the material in any medium or format.
* **Adapt:** Remix, transform, and build upon the material for any purpose.

**Under the following terms:**
* [cite_start]**Attribution**: You must give appropriate credit to **Team THUNDERSTRIKE 33535 (Lisbon, Portugal)**, provide a link to the license, and indicate if changes were made[cite: 5, 31].
* **ShareAlike**: If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.

---

## Overview and Physical Capabilities
[cite_start]Fortunate Son is built on a robust mecanum drivetrain, utilizing a specialized sensor suite for precision localization and vision processing[cite: 168, 243, 244].

* [cite_start]**Holonomic Movement**: Full 360-degree maneuverability to enable "Point & Shoot" mobility[cite: 168, 169].
* [cite_start]**Triple-Redundant Localization**: Integrated mounting for the **goBILDA Pinpoint Computer** and the **SparkFun OTOS** for zero-drift positioning[cite: 227, 232, 244].
* [cite_start]**Vision-Guided Targeting**: Optimized FOV mounts for the **Limelight 3a** to facilitate real-time artifact detection[cite: 224, 250].
* [cite_start]**High-Inertia Shooter**: Dual-motor flywheel system designed for consistent exit velocity and rapid recovery times[cite: 208, 210, 248].

---

## Engineering Portfolio
[cite_start]The Engineering Portfolio documents the iterative design process and strategic decision-making that led to the current competition assembly[cite: 8, 124].

* [cite_start]**CAD-First Methodology**: A strict rule where zero physical manufacturing occurs before digital verification to eliminate material waste[cite: 135, 136].
* [cite_start]**Iterative Evolution**: Documentation of the pivot from a 6-wheel differential drive to a 15:1 mecanum system to eliminate wheel slip and increase agility[cite: 167, 168, 171].
* [cite_start]**Vibration Management**: Use of aluminum shooter panels over acrylic to increase rigidity and shot consistency[cite: 186].

---

## Strategic Analysis: Optimal Cycle Play
[cite_start]Based on the team's documented **TeleOp Cycle Philosophy**, Fortunate Son is optimized for a **Minimum Travel Strategy**[cite: 495].

* [cite_start]**Intake-to-Shoot Sequence**: Designed for rapid transitions without manual orientation delays[cite: 495, 222].
* [cite_start]**Zone Optimization**: Optimal performance is achieved by utilizing dedicated "Shooting Zones" synchronized with 15:1 drivetrain speeds[cite: 497, 498].
* [cite_start]**High-Throughput Bursts**: The dual-motor flywheel enables a 3-round burst in under 1 second, maximizing scoring density[cite: 213, 248].
* [cite_start]**Passive Funneling**: The custom front bumper angle creates a funnel that centers artifacts into the intake's acquisition zone[cite: 178].
* [cite_start]**Interlocking Protection**: Independent skirt panels shield drive motors and prevent robot snagging during defense[cite: 175, 182, 183].

---

## CAD Structure
The CAD assembly is organized into a modular hierarchy within Fusion 360 to allow for parallel development.

### Main Assembly Tree (Main:1)
The **Main:1** component serves as the top-level assembly for all active hardware subsystems:
* [cite_start]**Odo Pod Y Axis / X Axis**: Dedicated sub-assemblies for the spring-loaded dead-wheel odometry pods[cite: 233].
* [cite_start]**Intake**: Contains the deployment mechanism, 20:1 drive system, and dual-sensor housing[cite: 187, 239].
* [cite_start]**Shooter**: The primary scoring mechanism, including the dual-motor flywheel and handover logic[cite: 203, 208].
* [cite_start]**Chassis Base**: The structural skeleton of the robot, including drive motor mounts and the protective skirt[cite: 166, 174].
* **Chain Covers**: Protective shielding for the drive system.
* [cite_start]**Signage**: Custom 3D-printed branding plates (33535 Arial Narrow signs)[cite: 21].

---

## Untested Experimental Configurations
Inside the CAD browser, you will find several hidden sub-components representing alternative hardware configurations:
* **Shooter Structure (Aluminum vs. Acrylic)**: Toggle between Acrylic and Aluminum side panels. [cite_start]Aluminum is preferred for vibration damping[cite: 186].
* **Flywheel Mass (Standard vs. Plus)**: Includes a Standard Flywheel and a "Plus" Flywheel for higher rotational inertia.
* **Limelight Mounts (Static vs. Gimbal)**: The standard static pivot is active by default. An untested active Limelight gimbal powered by a servo is included for experiments with dynamic tracking.

---

## Bill of Materials (BOM)

### Drivetrain and Navigation
| Item | Quantity | Notes |
| :--- | :--- | :--- |
| REV HD Hex Motor | 4 | [cite_start]Paired with UltraPlanetary Gearboxes [cite: 170] |
| UltraPlanetary Kit | 4 | [cite_start]Configured at 15:1 Gear Ratio [cite: 171] |
| goBILDA Pinpoint Computer | 1 | [cite_start]Operating in I²C mode [cite: 234] |
| goBILDA Odometry Wheels | 2 | [cite_start]48mm specialized wheels [cite: 233] |
| SparkFun OTOS | 1 | [cite_start]Optical Tracking Odometry Sensor [cite: 227] |
| Limelight 3a | 1 | [cite_start]AI Vision Sensor (USB mode) [cite: 250] |

### Intake Subsystem
| Item | Quantity | Notes |
| :--- | :--- | :--- |
| REV HD Hex Motor | 1 | 20:1 UltraPlanetary Gearbox |
| REV Color Sensor V3 | 2 | [cite_start]Dual-sensor setup for intake logic/detection [cite: 239] |

### Shooter Subsystem
| Item | Quantity | Notes |
| :--- | :--- | :--- |
| REV HD Hex Motor (Flywheel) | 2 | [cite_start]1:1 Ratio (Direct Drive) [cite: 210] |
| REV HD Hex Motor (Handover) | 1 | [cite_start]20:1 Ratio with Gecko Wheels [cite: 205] |
| REV Color Sensor V3 | 1 | Internal state checking |
| REV Blinkin LED | 1 | [cite_start]Driver feedback and visual cues [cite: 284] |

**Hardware Note**: In the shooter assembly, the Port Motor must be oriented/wired for Anti-Clockwise rotation, while the Starboard Motor is oriented/wired for Clockwise rotation.

### Control System
| Item | Quantity | Notes |
| :--- | :--- | :--- |
| REV Control Hub | 1 | Primary Controller |
| REV Expansion Hub | 1 | Connected via RS485 |
