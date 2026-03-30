# Fortunate Son — Competition Edition (Hardware)

Official hardware documentation, CAD repository, and Engineering Portfolio for **Fortunate Son**, a high-performance FIRST Tech Challenge robot by **Team THUNDERSTRIKE 33535**. This release focuses on the physical build and mechanical assembly, optimized for rigidity, precision localization, and high-speed scoring.

---

## License
This hardware and documentation are licensed under the **GNU General Public License v3.0**. 

**Under this license, you are free to:**
* **Share:** Copy and redistribute the material in any medium or format.
* **Adapt:** Remix, transform, and build upon the material for any purpose.

**Under the following terms:**
* **Attribution**: You must give appropriate credit to **Team THUNDERSTRIKE 33535 (Lisbon, Portugal)**, provide a link to the license, and indicate if changes were made.
* **ShareAlike**: If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.

---

## Overview and Physical Capabilities
Fortunate Son is built on a robust mecanum drivetrain, utilizing a specialized sensor suite for precision localization and vision processing.

* **Holonomic Movement**: Full 360-degree maneuverability to enable "Point & Shoot" mobility.
* **Triple-Redundant Localization**: Integrated mounting for the **goBILDA Pinpoint Computer** and the **SparkFun OTOS** for zero-drift positioning.
* **Vision-Guided Targeting**: Optimized FOV mounts for the **Limelight 3a** to facilitate real-time artifact detection.
* **High-Inertia Shooter**: Dual-motor flywheel system designed for consistent exit velocity and rapid recovery times.

---

## Engineering Portfolio
The Engineering Portfolio documents the iterative design process and strategic decision-making that led to the current competition assembly.

* **CAD-First Methodology**: A strict rule where zero physical manufacturing occurs before digital verification to eliminate material waste.
* **Iterative Evolution**: Documentation of the pivot from a 6-wheel differential drive to a 15:1 mecanum system to eliminate wheel slip and increase agility.
* **Vibration Management**: Use of aluminum shooter panels over acrylic to increase rigidity and shot consistency.

---

## Strategic Analysis: Optimal Cycle Play
Based on the team's documented **TeleOp Cycle Philosophy**, Fortunate Son is optimized for a **Minimum Travel Strategy**.

* **Intake-to-Shoot Sequence**: Designed for rapid transitions without manual orientation delays.
* **Zone Optimization**: Optimal performance is achieved by utilizing dedicated "Shooting Zones" synchronized with 15:1 drivetrain speeds.
* **High-Throughput Bursts**: The dual-motor flywheel enables a 3-round burst in under 1 second, maximizing scoring density.
* **Passive Funneling**: The custom front bumper angle creates a funnel that centers artifacts into the intake's acquisition zone.
* **Interlocking Protection**: Independent skirt panels shield drive motors and prevent robot snagging during defense.

---

## CAD Structure
The CAD assembly is organized into a modular hierarchy within Fusion 360 to allow for parallel development.

### Main Assembly Tree (Main:1)
The **Main:1** component serves as the top-level assembly for all active hardware subsystems:
* **Odo Pod Y Axis / X Axis**: Dedicated sub-assemblies for the spring-loaded dead-wheel odometry pods.
* **Intake**: Contains the deployment mechanism, 20:1 drive system, and dual-sensor housing.
* **Shooter**: The primary scoring mechanism, including the dual-motor flywheel and handover logic.
* **Chassis Base**: The structural skeleton of the robot, including drive motor mounts and the protective skirt.
* **Chain Covers**: Protective shielding for the drive system.
* **Signage**: Custom 3D-printed branding plates (33535 Arial Narrow signs).

---

## Untested Experimental Configurations
Inside the CAD browser, you will find several hidden sub-components representing alternative hardware configurations:
* **Shooter Structure (Aluminum vs. Acrylic)**: Toggle between Acrylic and Aluminum side panels. Aluminum is preferred for vibration damping.
* **Flywheel Mass (Standard vs. Plus)**: Includes a Standard Flywheel and a "Plus" Flywheel for higher rotational inertia.
* **Limelight Mounts (Static vs. Gimbal)**: The standard static pivot is active by default. An untested active Limelight gimbal powered by a servo is included for experiments with dynamic tracking.

---

## Bill of Materials (BOM)

### Drivetrain and Navigation
| Item | Quantity | Notes |
| :--- | :--- | :--- |
| REV HD Hex Motor | 4 | Paired with UltraPlanetary Gearboxes |
| UltraPlanetary Kit | 4 | Configured at 15:1 Gear Ratio |
| goBILDA Pinpoint Computer | 1 | Operating in I²C mode |
| goBILDA Odometry Wheels | 2 | 48mm specialized wheels |
| SparkFun OTOS | 1 | Optical Tracking Odometry Sensor |
| Limelight 3a | 1 | AI Vision Sensor (USB mode) |

### Intake Subsystem
| Item | Quantity | Notes |
| :--- | :--- | :--- |
| REV HD Hex Motor | 1 | 20:1 UltraPlanetary Gearbox |
| REV Color Sensor V3 | 2 | Dual-sensor setup for intake logic/detection |

### Shooter Subsystem
| Item | Quantity | Notes |
| :--- | :--- | :--- |
| REV HD Hex Motor (Flywheel) | 2 | 1:1 Ratio (Direct Drive) |
| REV HD Hex Motor (Handover) | 1 | 20:1 Ratio with Gecko Wheels |
| REV Color Sensor V3 | 1 | Internal state checking |
| REV Blinkin LED | 1 | Driver feedback and visual cues |

**Hardware Note**: In the shooter assembly, the Port Motor must be oriented/wired for Anti-Clockwise rotation, while the Starboard Motor is oriented/wired for Clockwise rotation.

### Control System
| Item | Quantity | Notes |
| :--- | :--- | :--- |
| REV Control Hub | 1 | Primary Controller |
| REV Expansion Hub | 1 | Connected via RS485 |
