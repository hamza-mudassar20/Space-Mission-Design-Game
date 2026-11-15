# Educational Science Model and Scoring

## Purpose
This prototype models **coupled mission engineering decisions** rather than full orbital dynamics. It intentionally illustrates the challenge statement's system interdependencies; it should never be interpreted as a physically validated mission planner.

## Design calculations
1. **Spacecraft dry mass (kg)** = spacecraft bus + solar arrays + communications + shield + chosen scientific instruments.
2. **Total spacecraft launch mass (kg)** = dry mass × (1 + destination propellant factor × orbit delivery factor).
3. **Available payload capacity (kg)** = fictional launch vehicle capacity adjusted for destination/orbit simplifications.
4. **Total mission cost (USD millions)** = fictional setup cost + fictional launch cost + subsystem development costs + instrument development costs + (fictional operations rate × days).
5. **Electrical generation (W)** = fictional solar array rating × destination sunlight factor × orbit illumination factor.
6. **Electrical demand (W)** = bus + communications + protection + science instrument operating loads.
7. **Downlink (GB/day)** = fictional radio link throughput × destination communications factor × orbit access factor.
8. **Science data generation (GB/day)** = sum of instrument data output.
9. **Science index** = (sum of instrument science scores × orbit science suitability × duration factor) / destination science target × 100.
10. **Illustrative confidence** = weighted hardware reliability indicators plus shield protections and mass stress.
11. **Viability indicator** = a weighted heuristic rewarding science, resource margins and confidence, with penalties for infeasibility.
12. **Postflight score** = weighted scientific return (36%), integrity (22%), budget reserve (12%), mass reserve (10%), power reserve (10%), effective downlink (10%), plus up to 5 team collaboration points and penalties for critical violations.

## Failures, event choices and learning
- Feasibility violations: incompatible launcher, missing scientific instrument, over-mass, over-budget, insufficient power; insufficient downlink produces a data backlog warning.
- Mission simulation: eight illustrative phases with two pause-and-choose events: a power/exposure event and a communications event.
- A conservative response can improve integrity at the cost of science; a risky response can enhance science/data return at a cost to integrity.
- The final report lists violated constraints and what the player might improve.

## Engineering assumptions
- Subsystem masses are approximate invented game values, *not* sourced spacecraft hardware specifications.
- Instrument data and electrical loads are approximations for intuitive trade-offs, not calibrated to any specific NASA instrument.
- Three mission altitudes are sourced from NASA; alternative orbit altitudes and all gameplay multipliers are illustrative.
- Time steps and anomalies are not physically simulated orbital propagation; `simulated` means an educational decision-tree exercise.
- The mission-score formula is a transparent classroom rubric, not a reliability assessment.
- Rover/lander design, transfer orbits, thermal control, detailed orbital mechanics, solar eclipses, RF link budgets, thermal cycling, propellant burns, and formal mission assurance are outside scope.

## What is original here?
An integrated *consequence chain*: each payload choice changes at least four engineering quantities; orbit choices trade science against sunlight and communications; launch capacity and cost trade off; a mission council approves the design; mid-flight decisions affect outcome; a quantitative debrief teaches what failed. The scenario structure invites replay and design iteration.

## Teamplay limitation
Role approvals are shared-device, hot-seat votes for up to four contributors, **not live network collaboration**. Real-time online multiplayer would require backend services and is not implemented.
