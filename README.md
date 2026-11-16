# Skin Atlas

Interactive 3D skin and procedure explainer for aesthetic clinics. One self-contained `index.html` built on Three.js, no build step.

## Scenes

- **Treatments** – laser epilation, hyaluronic biorevitalization and RF lifting on a scrubbable timeline
- **Skin age** – age slider (20–65) with lifestyle toggles
- **Face map** – seven zones with causes and treatment options

English and Georgian are both included. Deep links: `#ka`, `#en`, `#ka-age`, `#ka-face`, `#en-age`, `#en-face`.

## Face photo

In the Face map scene a visitor can upload a photo or use the camera. The face is detected in the browser with MediaPipe Face Landmarker, shown as a 3D mask in place of the mannequin, and a before/after slider previews an approximate effect per zone.

- The photo never leaves the device. Library, WebAssembly and model are served from `vendor/`, so nothing is sent to a third party.
- The result is a visual simulation, not a clinical prediction. The page labels it as such.
- The camera needs HTTPS (or localhost).

## Run

Open `index.html` in a browser, or deploy the repository as a static site (Vercel framework preset: Other).

## Notes

The model is illustrative. Figures, temperatures and timings are simplified and are not clinical guidance.
