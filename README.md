# Skin Atlas

Interactive 3D skin and procedure explainer for aesthetic clinics. One self-contained `index.html` built on Three.js, no build step.

## Design

The interface follows the Verve brand book: Cream Silk page, Smoked Moss rail, Charcoal Noir stage, Dark Walnut and Tanned Leather for calls to action. Headings use Zodiak Bold (Latin) and Noto Serif Georgian Bold; text uses Noto Sans Georgian. The wordmarks in `assets/logo-en.svg` and `assets/logo-ka.svg` and the symbol in `assets/symbol.svg` are the vector outlines from the brand book, unmodified. The lattice in the rail is the brand pattern.

The model sits in an arch whose outline is the progress track: it fills as a treatment plays and carries the decade marks in the Skin age scene.

Zodiak is served from `assets/fonts/` and comes from Fontshare; check its licence terms before commercial launch.

## Scenes

- **Treatments** – laser epilation, hyaluronic biorevitalization and RF lifting on a scrubbable timeline
- **Skin age** – age slider (20–65) with lifestyle toggles
- **Face map** – seven zones with causes and treatment options

English and Georgian are both included. Deep links: `#ka`, `#en`, `#ka-age`, `#ka-face`, `#en-age`, `#en-face`.

## Face photo

The Face map opens on a default portrait (`assets/model.jpg`). It is AI-generated, not a real person, and the page says so. Its landmarks are precomputed in `assets/model.json`, so the default face needs no model download. To change it, replace the image and regenerate the JSON by uploading the image in the page and running `JSON.stringify(SkinAtlas.landmarks())` in the console.

In the Face map scene a visitor can upload a photo or use the camera. The face is detected in the browser with MediaPipe Face Landmarker, shown as a portrait with the face in relief, and the zone pins move onto the real features. A suggestions panel lets the visitor mark which areas bother them and enter an age, and returns a short list of topics to raise at a consultation.

- The photo never leaves the device. Library, WebAssembly and model are served from `vendor/`, so nothing is sent to a third party.
- Nothing is measured from the photo. An automatic line score was tried and removed after it misread a test portrait. The suggestion rules (`recommend()` in `index.html`) are a draft for the clinic's doctor to review.
- There is no before/after simulation: it was removed because the result was not reliable enough to show clients.
- The camera needs HTTPS (or localhost).

## Run

Open `index.html` in a browser, or deploy the repository as a static site (Vercel framework preset: Other).

## Notes

The model is illustrative. Figures, temperatures and timings are simplified and are not clinical guidance.
