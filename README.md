# STM32 Inertial Sensing PCB

### Custom 4-Layer Embedded Hardware Design | KiCad | STM32L476 | MPU-6050

**Project Status:** In Progress — PCB Design and Layout

## Project Overview

This project focuses on designing a custom four-layer printed circuit board (PCB) that integrates an STM32L476 microcontroller with an MPU-6050 six-axis inertial measurement unit (IMU).

My goal is to develop an embedded system capable of collecting acceleration and angular velocity data through I²C communication. I eventually want to use this board to explore applications involving motion tracking, robotics, and orientation sensing.

Rather than relying on a prebuilt development board, I wanted to take on the challenge of designing the hardware myself, from the circuit schematic to the PCB layout, and eventually bring the design to life through firmware development and physical testing.

## Why I Chose This Project

After working with STM32 microcontrollers in class, I wanted to learn more about the hardware itself instead of just programming it. Through earlier projects, I realized how much I enjoyed PCB design, so I wanted to take on a project where I could design a board of my own.

I've always been fascinated by the technology used in aerospace, especially how aircraft use sensors and electronics to track movement and orientation. That's part of what made me interested in using the MPU-6050.

I saw this project as a chance to combine my interest in aerospace technology with something I enjoy doing, while also improving my skills in PCB design and embedded systems. My goal is to eventually turn this design into a working board that I can program and test.

## Hardware Components

| Component | Purpose |
|---|---|
| STM32L476RGT6 | ARM Cortex-M4 microcontroller |
| MPU-6050 | Six-axis accelerometer and gyroscope |
| I²C Pull-Up Resistors | Support sensor communication |
| Decoupling Capacitors | Support stable power delivery |
| SWD Header | Microcontroller programming and debugging |
| UART Header | Serial communication interface |
| GPIO Expansion Header | Access to additional microcontroller pins |
| Reset Circuit | Manual microcontroller reset |

The board is designed to operate from an external regulated 3.3 V supply.

## PCB Architecture

The PCB uses a four-layer copper stackup:

| Layer | Function |
|---|---|
| Layer 1 — F.Cu | Component placement and signal routing |
| Layer 2 — In1.Cu | Ground plane |
| Layer 3 — In2.Cu | 3.3 V power plane |
| Layer 4 — B.Cu | Additional signal routing |

This configuration provides dedicated power and ground distribution while allowing signal connections to be routed across the outer layers.

## Engineering Design Considerations

### Sensor Communication

The STM32 is designed to communicate with the MPU-6050 through an I²C interface using SDA and SCL connections with external pull-up resistors.

### Power Distribution

The design incorporates dedicated power and ground planes, local decoupling capacitors, and vias to connect components to their respective supply networks.

### Programming and Debugging

An SWD interface provides access to the microcontroller for future firmware programming and debugging.

### Expandability

UART and GPIO headers provide connections for future external devices, testing, and embedded applications.

## Development Progress

- [x] Completed circuit schematic and passed KiCad ERC
- [x] Selected components and assigned footprints
- [x] Configured four-layer PCB with power and ground planes
- [ ] Complete PCB routing and pass DRC
- [ ] Manufacture and assemble the PCB
- [ ] Develop firmware and test sensor communication on the PCB

## Future Development

After completing and validating the PCB layout, my next goal is to manufacture and assemble the board. Since I already have experience programming STM32 microcontrollers in C, I plan to apply those skills to the PCB I designed by developing firmware that communicates with the MPU-6050 through I²C.

Once the board is working, I want to use the accelerometer and gyroscope measurements to create a simple motion-tracking or orientation-monitoring application.

Long term, I'd like to continue exploring how embedded hardware and inertial sensors are used in more advanced systems, particularly robotics and aerospace electronics.

## Tools and Technologies

- **PCB Design:** KiCad
- **Microcontroller:** STM32L476 (ARM Cortex-M4)
- **Sensor:** MPU-6050 IMU
- **Communication:** I²C, UART, SWD
- **Firmware Development:** Embedded C, STM32CubeIDE (planned for this board)

---

*This project is currently in the PCB design stage. The hardware has not yet been manufactured or physically tested.*
