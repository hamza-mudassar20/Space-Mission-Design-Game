# QA / Acceptance Test Plan

This is a functional engineering prototype. Execute this browser checklist before public competition submission.

## Manual smoke tests
1. Open index.html: all three mission cards and the telemetry panel appear.
2. Switch Earth → Moon → Mars: mission name, cost budget, relevant instrument catalog, reference altitude and planet color update.
3. Change orbit: visual altitude label and advisor information change.
4. Choose/deselect science instruments: count changes; multiple resource values update.
5. Try selecting a fourth instrument: UI prevents the selection.
6. Choose too-small launcher for Mars: a **critical** warning appears and mission viability decreases.
7. Add the biggest payload with weak power: warning appears for demand exceeding generation.
8. Select inadequate communications: a data-backlog warning appears.
9. Click launch on a valid design: animated mission phase dialog appears; first dilemma appears after four phases.
10. Select each first choice, then the communications choice: a result card appears with score and debrief.
11. Download report and blueprint: valid text and JSON files are created.
12. Switch on 4-role team council: launch without approvals shows a warning. With three approvals, launch starts.
13. Click reset: scenario defaults restored.
14. Save comparison snapshot, modify orbit: score delta appears in snapshot button.
15. Reload the page: configuration is preserved when localStorage is available.
16. Test with keyboard Tab/Enter/Space and narrow mobile widths.
17. Run with network disconnected: no external dependencies are required to play.

## Static/code checks performed during generation
- `node --check game.js`: syntax check.
- Node isolated model evaluations for all three scenario default configurations: no major feasibility violations at baseline.
- In this environment, automated Chromium browsing was **blocked by administrator policy**, so live end-to-end click testing and screenshot inspection could not be completed. The team must run the manual acceptance steps in a normal browser before submission.

## Known limits
- One file-saved localStorage value per device; clearing browser data removes saved config.
- No real multiplayer sync; teamwork is hot-seat only.
- Score parameters are fictional teaching values.
- Mission flight stages are scripted with branch decisions rather than a real orbital propagator.
- Report export describes the latest completed mission but live configuration changes after report generation should be avoided until you download the report.

## Release gate
Do not claim tested in full browser until the player walkthrough and edge cases are completed on your actual device. Screenshot assets for the slide deck are artistic representations, not captured running-product screenshots.
