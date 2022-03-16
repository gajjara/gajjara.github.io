# MODE Radar System

![Alt text](img/Capstone%20Final%20Presentation0.png)

## Design Problem

Many popular unmanned vehicles rely heavily or solely on optical sensors for room navigation and mapping in disaster search & rescue scenarios\. The effectiveness of the optical sensors on these vehicles can be inhibited by smoke and dust\.

![Alt tex](img/Capstone%20Final%20Presentation1.png)

![Alt text](img/Capstone%20Final%20Presentation2.png)

__https://www\.enr\.com/articles/42484\-what\-local\-officials\-want\-to\-do\-about\-wood\-frame\-building\-fires\-in\-massachusetts__

__https://www\.cbsnews\.com/news/surfside\-condo\-collapse\-search\-ends/__

## Solution? The MODE Radar System

<span style="color:#000000">60 GHZ</span>

<span style="color:#000000">FMCW</span>

<span style="color:#000000">CFAR</span>

![Alt text](img/Capstone%20Final%20Presentation3.png)

![Alt text](img/Capstone%20Final%20Presentation4.png)

ANDROS Wolverine

<span style="color:#000000">Murphy R\.R\. </span>  <span style="color:#000000"> _Disaster Robotics\._ </span>  <span style="color:#000000"> MIT Press; Cambridge\, MA\, USA: 2014</span>

## Frequency Modulated Continuous Wave Radar

* Modulated in frequency
* Difference in frequencies\, Δf → time delay\, td
  * td = Δf \* T / B
  * T is period; B is bandwidth
* d = c \* td / 2
  * c = 3E8 m/s is the speed of light in vacuum

![Alt text](img/Capstone%20Final%20Presentation5.png)

![Alt text](img/Capstone%20Final%20Presentation6.png)

## Signal Processing

![Alt text](img/Capstone%20Final%20Presentation7.png)

![Alt text](img/Capstone%20Final%20Presentation8.png)

## Hardware Block Diagram

![Alt text](img/Capstone%20Final%20Presentation9.png)

Features:

Power Supply support servo

External Computer combines all data

Gyroscope for accurate positioning

SOC pre\-flashed

## Radar Overview

![Alt text](img/Capstone%20Final%20Presentation10.jpg)

![Alt text](img/Capstone%20Final%20Presentation11.jpg)

![Alt text](img/Capstone%20Final%20Presentation12.png)

## Gimbal

* Features:
* 2 Servos
  * horizontal one on the base
  * vertical one holding the frame for radar chip
* Gyroscope
  * receiving three angles in degrees for three directions\- x\, y\, and z; only using x and z direction
  * accurate current position in floating point
* Multiple antenna
  * increase the field of view for both azimuth \(90°\) and elevation \(30°\)

![Alt text](img/Capstone%20Final%20Presentation13.png)

## Kinematics

![Alt text](img/Capstone%20Final%20Presentation14.png)

## Software - Overview

| Requirement | Approach | Result |
| :-: | :-: | :-: |
| Radar Control<br />Must have real-time configuration and control | UART for communication | Can configure and control radar SOC in real time |
| Data Receiving/Processing<br />Must be relatively fast | UART for communication<br />Communication and data processing in separate process<br /> | ~500 microseconds to receive and process data* |
| Gimbal Control | UART for communication<br />Communication in separate process | Non-blocking |
| Visualization<br />Cannot be resource intensive | OpenGL<br />Relatively fast runtime | Non-blocking and can run at data rate of 30FPS |
| Integration<br />Must have non-blocking threads and processes | Multiprocessing<br />Low CPU use and easier to poll for data | Low CPU use (2-3%) for data processing and gimbal control*<br /><br />*on Intel MacOS |

## Software - Data Receiving/Processing

From radar SOC: list of detected objects

![Alt text](img/Capstone%20Final%20Presentation15.png)

## Software - Gimbal Control

![Alt text](img/Capstone%20Final%20Presentation16.png)

Gimbal Control

Inputs the angles to the servos

Transfer data from gyroscope to the PC

![Alt text](img/Capstone%20Final%20Presentation17.png)

Gimbal Control

Controls the servos

Transfer data from gyroscope to the PC

## Software - Visualization

OpenGL Visualization:

![Alt text](img/Capstone%20Final%20Presentation18.png)

3D Plot Keyboard inputs:

Left and Right arrow keys \- rotates the voxels horizontally with an Ry rotation

Up and Down arrow keys \- rotates the voxels vertically with an Rx rotation

Decimal \- resets the current frame to the origin frame

Shift and Forward Slash \- translate the voxels on the z\-axis to give the points the appearance of “zooming in” and “zooming out” 2 dimensionally

Semicolon and Apostrophe \- translates the voxels on the y\-axis so the user can get an “overhead view” of the plot\.

Antenna Center Point

## Software - Main Program 2D

![Alt text](img/Capstone%20Final%20Presentation19.png)

![Alt text](img/Capstone%20Final%20Presentation20.png)

![Alt text](img/Capstone%20Final%20Presentation21.png)

![Alt text](img/Capstone%20Final%20Presentation22.gif)

![Alt text](img/Capstone%20Final%20Presentation23.gif)

![Alt text](img/Capstone%20Final%20Presentation24.png)

![Alt text](img/Capstone%20Final%20Presentation25.jpg)

![Alt text](img/Capstone%20Final%20Presentation26.png)

Antenna Center Point

## Software - Visualization

Enter servo angles

Reset to initial position

Have a complete scan

![Alt text](img/Capstone%20Final%20Presentation27.png)

## Budget

| Item | Cost | Quantity | Total |
| :-: | :-: | :-: | :-: |
| Arduino (Redboard) | $20.00 | 1.00 | $20.00 |
| 3D Printed Servo Assembly | $20.00 | 1.00 | $20.00 |
| Servo 2 Pack | $38.84 | 1.00 | $38.84 |
| Heat Inserts for 4 mm screws (20 Pack) | $11.54 | 1.00 | $11.54 |
| Heat Inserts for 2.5 mm screws (20 pack) | $7.94 | 1.00 | $7.94 |
| Screw 2.5mm (100) | $2.54 | 1.00 | $2.54 |
| Radar Board | $142.00 | 1.00 | $142.00 |
| USB to microUSB cable and Battery Pack | $7.35 | 1.00 | $7.35 |
|  |  | Total Cost: | $250.21 |
| R&D Cost: $411.97 |  | Estimated Bulk Cost: | $150.12 |

## MODE Radar Rev 2

* Increase Range
* Increase accuracy
* Decreased data complexity
* User friendly application
* Use of compiled software instead of interpreted software
  * And optimized resource use

![Alt text](img/Capstone%20Final%20Presentation28.jpg)

![Alt text](img/Capstone%20Final%20Presentation29.png)

![Alt text](img/Capstone%20Final%20Presentation30.jpg)

## Acknowledgements

Thank you to Professor Dimarzio for all his help throughout the design process
