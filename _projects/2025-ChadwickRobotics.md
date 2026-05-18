---
layout: project
title: VEX Robotics
description: Three-Year Competition Program
technologies: [Autodesk Inventor, Onshape, Ansys Discovery, PID Control]
image: /assets/images/VEX-SpinUp.jpg
order: 6
---

Over three years of high school VEX Robotics competition I led my team to qualify for the VEX World Championship twice, win the Build Award at the California State Championship, and ultimately design one of the most technically ambitious robots of my high school career: a turret bot with a custom PID auto-aim system built entirely within competition-legal parts.

---

## Change Up (2020) — Building Through a Pandemic

![Change Up Robot]({{ "/assets/images/VEX-ChangeUp.JPG" | relative_url }}){: style="width: 360px; display: block; margin: 0 auto;"}

The 2020 season hit during the COVID-19 school shutdowns. With no access to a school shop, our small team of 3–5 designed and built our robot almost entirely from home. Despite those constraints, we successfully qualified for the **VEX World Championship**, a result that required placing at a qualifying tournament and meeting the design documentation standards required by VEX judges at every level

---

## Tipping Point (2021) — Worlds and the Build Award

![Tipping Point at Worlds]({{ "/assets/images/VEX-TippingPoint.jpg" | relative_url }}){: style="width: 50%; display: block; margin: 0 auto;"}

The following year we qualified for Worlds a second time and won the **Build Award at the California State Championship**. The Build Award is judged on the quality of the engineering design process as documented in the team's engineering notebook. This documentation covers research, design iterations, testing, and reflection. Winning it at states earned us a second invitation to compete at the World Championship against teams from across the globe.

---

## Spin Up (2022) — Turret Bot with Auto-Aim

![Spin Up Turret Robot]({{ "/assets/images/VEX-SpinUp.jpg" | relative_url }}){: style="width: 550px; display: block; margin: 0 auto;"}

As a senior I set out to build the most technically sophisticated robot I could within the constraints of the VEX system. The game involved launching flying discs at elevated goals, and I designed a **full 360° turret** that could track and aim at targets autonomously.

![Vex Turret]({{ "/assets/images/VexTurret.jpg" | relative_url }}){: style="width: 550px; display: block; margin: 0 auto;"}

### Custom Hardware

Executing a turret inside VEX's competition-legal part restrictions required designing and manufacturing custom components from scratch:

- **Custom turret base gear** — designed to interface with VEX motors while providing the gear ratio needed for smooth, fast turret rotation
- **Custom ring gears** — machined to fit within the legal parts envelope while enabling the turret's full rotational range

![Custom gear close-up]({{ "/assets/images/VexCustomGear.jpg" | relative_url }}){: style="width: 500px; display: block; margin: 0 auto;"}

### PID Auto-Aim Control System

Getting the turret to aim accurately required building a custom control system from scratch. I implemented an **electrodynamic inverse motor model** paired with a **PID controller** to drive the turret to a target heading and hold it precisely under load. This meant modeling the motor's back-EMF behavior to get accurate velocity feedback, then tuning the PID gains for fast settling time without overshoot, all on VEX's constrained embedded platform.

![Robot Turret Looking At Target]({{ "/assets/images/VexSpinUpPointAtGoal.jpg" | relative_url }}){: style="width: 550px; display: block; margin: 0 auto;"}

### Engineering Notebook

Significant effort went into the engineering notebook this season, building on lessons learned from the Build Award win the prior year. The notebook documents the full design process: game analysis, design trade studies, CAD iterations, manufacturing decisions, and control system development.


[View the Engineering Notebook (PDF)](https://www.seankaidempsey.com/2150A_Spin_Up_Notebooks-10_5_22_Edition.pdf)

---
