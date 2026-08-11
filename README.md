# ANKL — 3-DOF Pediatric Prosthetic Ankle

A three-degree-of-freedom prosthetic ankle designed to emulate natural gait motion for a pediatric patient, developed across five 3D-printed design iterations with linear actuators, custom joints, and a purpose-built PCB.

**Stack:** SolidWorks (parts, assemblies, drawings) · FEA · 3D printing (PLA) · linear actuators · custom PCB · electrical schematics · kinematic modeling
**Context:** Biomedical Engineering Project, Texas A&M University — January 2026 – present
**Role:** Mechanical design, electrical schematic design, PCB layout, iteration testing

---

## The problem

Commercial prosthetic ankles are overwhelmingly designed for adult anatomy and adult gait. Pediatric patients get scaled-down adult hardware, which means the wrong mass distribution on a body that has less strength to carry it, and joint kinematics that don't match a growing gait pattern. Weight is the binding constraint: every gram at the distal end of the limb costs disproportionate metabolic energy during swing phase.

## What was built

A 3-DOF ankle assembly — dorsiflexion/plantarflexion, inversion/eversion, and internal/external rotation — driven by linear actuators through custom-designed joints, with a kinematic model used to size actuator stroke and mounting geometry against target range of motion before anything was printed.

### Headline result

**Device weight reduced 1.6×** by designing the electrical schematics and a custom PCB from scratch, replacing discrete wiring and off-the-shelf boards, then repackaging the mechanical envelope around the smaller board footprint. The electrical redesign didn't just save board mass — it collapsed the wiring harness volume, which let the housing shrink.

## Design process

Five full iterations, each following the same loop:

1. **Model** — full parts and assemblies in SolidWorks, driven by the kinematic model for joint placement and actuator stroke
2. **Print** — 3D-printed prototype build
3. **Validate** — fit and range-of-motion checks on the physical build
4. **Feed back** — dimensional changes carried into the CAD model before the next print cycle

That last step is the one that matters. Each print exposed tolerance stack-up and interference that the model didn't predict, and the CAD was corrected rather than the print being shimmed.

| Iteration | Focus |
| --- | --- |
| 1 | Baseline 3-DOF joint architecture, actuator mounting feasibility |
| 2 | Joint geometry refinement against measured range of motion |
| 3 | Tolerance and clearance correction from physical fit testing |
| 4 | Electrical integration — schematic design and custom PCB |
| 5 | Mechanical envelope repackaged around the new board; weight reduction realized |

## Electrical design

Schematics and custom PCB components were designed from scratch rather than assembled from breakout boards. The goals, in order: cut mass, cut wiring complexity, and shrink the volume the electronics demand from the mechanical housing.

## Repository contents

```
cad/
  parts/            SolidWorks part files (.SLDPRT)
  assemblies/       Full ankle assemblies (.SLDASM)
  drawings/         Technical drawings (.SLDDRW, PDF exports)
  step/             Neutral-format STEP exports
electrical/
  schematics/       Electrical schematics
  pcb/              PCB layout files and Gerbers
  bom.csv           Bill of materials
analysis/
  kinematics/       Kinematic model and range-of-motion calculations
  fea/              FEA setup and results
docs/
  iteration-log.md  Per-iteration changes, measurements, and rationale
  images/           Renders and build photos
```

## Next steps

- Gait-cycle load testing beyond static fit and range-of-motion validation
- Actuator control tuning against measured pediatric gait profiles
- Material study — evaluating printed PLA against carbon-filled alternatives for the load-bearing members

## A note on files

CAD binaries are versioned here for completeness, but Git handles them as opaque blobs — diffs aren't meaningful. STEP exports are included so the geometry is reviewable without a SolidWorks license.

## License

MIT — see [LICENSE](LICENSE).
