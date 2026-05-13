---
layout: project
title: MAE 3780 Robotics Competition
description: Mechatronics  
technologies: [Arduino (AVR C), Fusion 360, Laser Cutting, Circuit Design]
image: /assets/images/Mechatronics.jpg
---

<video width="1080" height="1920" controls>
  <source src="{{ site.baseurl }}/assets/videos/robot_wall_deploy.mp4" type="video/mp4">

  Your browser does not support the video tag.
</video>

In MAE 3780 Mechatronics, my team designed and built a competitive robot for Cornell's Cube Craze tournament. Rather than optimizing a collector like most teams, we took an unconventional defensive approach: a deployable lattice wall that, once released, extended 20 inches on each side to block the opposing robot from collecting cubes entirely.

I designed the lattice wall mechanism in Fusion 360, which had to fit within an 8"×8" starting constraint while expanding dramatically upon release. I also wrote the majority of the robot's control code in AVR C using direct register manipulation, foregoing Arduino library functions entirely for lower-level hardware control.

I noticed that the Arduino's bootloader introduced a 1.5-second startup delay when the robot starts, which is critical when wall deployment timing determined the outcome of a match. By flashing the microcontroller without a bootloader using a second Arduino as a programmer, I reduced that delay to 0.1 seconds, a 15x improvement. The robot drew significant attention at competition, including interest from ASML engineers who asked to compete against us after the event concluded

<iframe src="{{ site.baseurl }}/assets/pdf/MAE3780_robotics_report.pdf" width="100%" height="800px"></iframe>
