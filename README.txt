SPRINT TIMING TESTING LABORATORY — V1

Purpose
This is a local, deterministic visual test laboratory. It is not the final
mobile video-analysis app. It simulates runner geometry, a running corridor,
chest-point correction, start/finish crossing, and known ground truth.

Run
Open index.html in a modern browser. No model, network connection, camera,
video upload, cloud storage, or account is needed.

Controls
- Drag Start A, Start B, Finish A, or Finish B directly in the scene.
- Use Play/Pause/Restart and one-frame stepping to inspect a crossing.
- Use Run test to run the deterministic simulation through its finish crossing.
- Choose a preset or adjust speed, apparent scale, lean, starting position,
  direction, simulation speed, and frame rate.
- Toggle overlays to isolate the geometry and calculated points.
- Export report downloads a local JSON diagnostic report.

Coordinate concepts
- Corridor progress is normalized: start cross-section = 0%, finish = 100%.
- Start A to Finish A and Start B to Finish B are the corridor boundaries.
- The current corridor cross-section is interpolated from those boundaries.
- The runner's ground/contact point is the primary reference.
- Blue is the simulated skeletal chest point.
- Orange is the algorithm's estimated front-chest point.
- Purple is the known simulated ground-truth front-chest point.

Crossing method
The laboratory tests crossing of each corridor cross-section by both the
estimated and ground-truth front-chest points. It linearly interpolates within
the current frame interval and retains a small past-frame diagnostic window.
This creates measurable timing error even though all runner inputs are known.

Deliberate V1 limits
- No video, MediaPipe, camera movement, noise, distractors, calibration, or
  advanced biomechanics.
- The body and chest correction are intentionally transparent simplified models.
- This is a geometry/timing validation surface for later connection to real
  video frames, MediaPipe landmarks, and tracking output.
