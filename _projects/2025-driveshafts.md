---
layout: project
title: Cornell Baja Racing Driveshafts and Plunging Cups
description: Advanced Design Project
technologies: [Solidworks, ANSYS FEA, Trak Lathe]
image: /assets/images/driveshafts.png
---

My project for Cornell Baja Racing 2024–2025 was to design the driveshafts and plunging cups for TG21, Cornell Baja's 2025 competition car. The driveshafts transfer torque from the driveline to the wheels while accommodating suspension travel through CV joints. The plunging cups are the inboard CV housings that integrate directly with the front and rear gearboxes. Both parts went through a full redesign with a primary goal of significant weight reduction — the final result was a **58% weight reduction** on the driveshafts over the previous car.

![Pretty Shafts]({{ "/assets/images/Rebuilding Driveshafts.JPG" | relative_url }}){: .inline-image-r style="width: 360px"}

## Design Requirements

**Constraints:**
- Must transfer maximum driveline torque without yielding
- Must survive the landing drop test load case
- Must not fail due to fatigue over the competition cycle
- Must fit within tight packaging constraints set by the CV joints.

**Objectives:**
- Reduce weight by 50% over the previous car's solid stainless steel shafts
- Keep costs and manufacturing complexity reasonable
- Maintain in-house manufacturability where possible

## Background — Why Redesign?

TGXX ran solid 17-4 H900 stainless steel driveshafts at 2.93 lbs each across three competitions without failure. However, strain gauge data collected during testing measured a peak torsional load of 677 ft-lbs — a load case under which hand calculations predicted the shafts should have yielded (FOS 0.89). The shafts survived, but this left open questions about true safety margin and made the case for a redesign that could also dramatically cut weight.

The team had previously attempted carbon fiber bonded driveshafts which failed during testing, leaving us on the heavy stainless shafts. This history made the case for a thorough material and manufacturing trade study before committing to a new design.

## Manufacturing Trade Study

I evaluated four broad manufacturing approaches before selecting a final design direction:

**Billet Machined (Gun Drilled)** — Building on the TGXX design, billet machined driveshafts offer the tightest packaging since the outer diameter is set only by CV joint clearances. Gun drilling the center removes significant material with minimal impact on torsional stiffness. Most operations can be done in-house; only the gun drilling requires outsourcing. This was the strongest candidate from the start.

**Welded** — Returning to a welded design was initially attractive since it worked historically. However, getting OEM splines now requires machining our own inserts with 4th-axis continuous operations we don't currently have the capability for. Weld strength is limited by penetration depth and weld length, and increasing either means adding wall thickness and weight. Maintaining concentricity across a welded shaft is also difficult and time-intensive for our welders.

**Press Fit Multi-Part Assembly** — Inspired by crankshaft design, this approach would press splined inserts onto a central tube to transfer torque. The upside is material mixing between sections; the downside is an unfamiliar and potentially dangerous manufacturing process with difficult-to-analyze failure modes.

**Splined Multi-Part Assembly** — Similar to the press fit idea but using a splined connection. Allows material mixing and easier manufacturing than a press fit, but internal spline machining and retention add complexity, and packaging becomes harder with a larger diameter tube.

**The winning solution: Gun-Drilled Billet.** It offered the best combination of weight savings, in-house manufacturability, packaging, and known failure behavior.

## Material Trade Study

I evaluated three primary materials: 17-4 H900 stainless steel (baseline), Titanium 6Al-4V STA, and 300M steel. Key considerations were torsional strength, fatigue life, weight, and machinability. While titanium has worse fatigue properties than both 17-4 and 300M, the cycle count at max load during a competition is low enough that it remains viable for the lower-loaded front shafts.

| Configuration | Weight (lbs) | FOS (500 ft-lbs) |
|---|---|---|
| Ti 6-4 0.875" OD (stock) | 2.05 | 1.005 |
| Ti 6-4 20mm OD | 1.74 | 1.005 |
| Ti 6-4 0.708" OD | 1.52 | 1.005 |
| Ti 6-4 0.708" OD (drill 3/8") | 1.07 | 0.926 |
| 300M 20mm OD (solid) | 2.96 | — |
| 300M 20mm OD (drill 7/16") | 1.99 | 1.317 |
| 300M 0.708" OD (drill 7/16") | 1.57 | 1.317 |
| 300M 0.675" OD (drill 7/16") | 1.54 | 1.100 |
| 17-4 20mm OD (TGXX, with neck) | 2.94 | Proven in comp |
| 17-4 0.708" OD (solid) | 2.53 | 1.139 |
| 17-4 0.708" OD (drill 3/8") | 1.83 | 1.050 |

The final design uses necked down **gun-drilled 300M steel**. The rear shafts save 1.7 lbs each (58% reduction) with the front shafts slightly less, for a total combined saving of approximately **5.92 lbs**.

## Ansys FEA

![Front Left Diff Troque]({{ "/assets/images/Front Left Diff Troque.png" | relative_url }}){: style="width: 600px; display: block; margin: 0 auto;"}

The primary load case analyzed in Ansys is shock torque loading from a drop test. The car being dropped onto a high traction surface with the driveline spun up, producing a sudden shock torque. I set up the Ansys model to apply this torsional load and verify that stresses stayed within material limits. Stress concentrations from the fillets at diameter transitions were also investigated; the fillet radii were large enough relative to the shaft diameter that standard table-based stress concentration factors weren't applicable, making the Ansys validation particularly important.

For the plunging cups I ran an axial load case on the front left diff cup and a sprag torque load case. The axial load case confirmed that the bearing surface stress was low, though reducing the bearing surface area without care could have made it significant. The sprag load case was updated to apply a 2 thou deformation (sourced from measured sprag deflection data) rather than a direct force, which better represents how the sprag physically loads the cup.

![Plunging Cup Shock Torque Ansys]({{ "/assets/images/Rear Shock Ansys Setup1.png" | relative_url }}){: style="width: 600px; display: block; margin: 0 auto;"}

## Plunging Cups

The plunging cups are the inboard CV housings that allow the driveshafts to plunge axially as the suspension travels. I designed custom plunging cups for both the front and rear gearboxes.

### Front Differential Plunging Cups

![Front Diff Plunging Cup CAD]({{ "/assets/images/FDR-diff-plunging.png" | relative_url }}){: style="width: 500px; display: block; margin: 0 auto;"}

The front plunging cups integrate with the front differential and had the most packaging challenges. A shimming oversight early in the design caused clearance issues between the cup and the diff/gearbox. Fixing this required moving the bearing abutment face and carefully re-verifying that enough material remained for axial load transfer. On the other side, the diff bolt circle was too close to the cup OD, requiring the outer diameter to be tapered down to avoid interference. I also standardized the bolt pattern to match TG19's retaining plate holes, allowing the front and rear cups to share the same retaining plates.

### Rear Plunging Cups

![Rear Plunging Cup]({{ "/assets/images/Rear Plunging Cup.png" | relative_url }}){: style="width: 500px; display: block; margin: 0 auto;"}

For the rear plunging cups I added a key slot to the brake rotor mount interface. When tightening the rotor mount onto the cup, the mount seats into the groove, preventing any axial movement of the rotor mount during competition loading. This improved rotor retention reliability and reduced break drag across competitions.

## Competition Results

TG21 competed successfully with no issues on either the driveshafts or plunging cups. A plunging CV internal cage failed during competition, but this was an off-the-shelf component that had been run for years. New OEM parts where purchased and there was no other issues. The diff plunging cups ran for all three competition without issues. TG21 came in first place at all competitions that it competed in.


[View Full Technical Report]({{ "/assets/pdf/skd82_TG21_Driveshaft_Plunging_Cups_Full.pdf" | relative_url }})
