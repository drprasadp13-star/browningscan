# BrowningScan

BrowningScan grades enzymatic browning of fresh-cut potato cubes from a single smartphone photograph. It runs entirely in the phone's browser: no server, no account, and no image leaves the device. After the first visit it also works offline.

**Open the app:** https://drprasadp13-star.github.io/browningscan/

## How to use

1. Put four potato cubes (about 1 cm) in a clear dish on plain white paper. The paper is the colour reference.
2. Hold the phone flat, about 30 cm above the dish, and avoid lamp reflections and the phone's shadow on the cubes. No grey card is needed, and ordinary room light, daylight or an LED lamp can be used. Avoid over-exposed (washed-out) photos.
3. Tap **Take photo** (or **Choose from gallery**).
4. Read the result:
   - **Level 0** (green): fresh or acceptable, ΔE00 below about 4
   - **Level 1** (amber): slight to moderate browning, ΔE00 about 4 to 8
   - **Level 2** (red): severe browning, ΔE00 above about 8
5. Tap **Save to log** to keep a time-stamped record, and **Copy log as CSV** to export it.

## Install on a phone

- **Android (Chrome):** open the link, then tap **Install app** on the page, or use the menu (three dots) and **Add to Home screen**.
- **iPhone (Safari):** open the link, tap **Share**, then **Add to Home Screen**.

## How it works

The app balances the photo against the white paper, finds the four cubes (threshold sweep on local yellowness contrast, then colour-model refinement), corrects colour against the white paper next to each cube, computes eight CIELAB colour indices, and applies a linear discriminant model (43 parameters). On phones that were not used for training, it graded 89 % of cubes and 90 % of photos correctly (balanced accuracy). In simulated lighting tests (warmer, cooler, dimmer or unevenly lit photos, with or without the grey card) cube accuracy stayed between 85 % and 91 %.

## Files

| File | Purpose |
|---|---|
| `index.html` | the complete app (analysis engine, model and three sample photos included) |
| `manifest.webmanifest` | makes the app installable |
| `sw.js` | caches the app for offline use |
| `icons/` | app icons |

## Citation

Prasad P., Pavithra K., Savitha M. B. Smartphone-based grading of enzymatic browning in fresh-cut potato (manuscript in preparation). Dataset: https://doi.org/10.5281/zenodo.17087416

Contact: Prasad P., Jawaharlal College of Engineering and Technology, Palakkad, Kerala, India (drprasadp13@gmail.com).

BrowningScan is a research prototype. Its results support, and do not replace, laboratory colorimetry.
