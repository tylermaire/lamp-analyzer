# LAMP Analyzer

A single-page web app for scoring **colorimetric phenol-red LAMP** assays from a
photo. Runs entirely in the browser (including iPhone Safari) — no server, no
upload; all image analysis happens on-device.

**Live app:** https://tylermaire.github.io/lamp-analyzer/

## How to use
1. Open the app (add it to your iPhone Home Screen via Share → "Add to Home Screen").
2. Take or choose a photo of your tube rack.
3. Tap the **Positive control**, then the **Negative control**, then each **test tube**.
4. Adjust the **Presumptive** and **Positive** cut-off sliders — calls update live.
5. **Save CSV** / **Save Image** to export results.

## Scoring
Each tube is placed on a percent scale anchored by the two controls, using the
CIELAB **hue angle**:

    % change = (hue_tube − hue_NEG) / (hue_POS − hue_NEG) × 100
    NEG control = 0 %        POS control = 100 %

Defaults: `< 15 %` NEGATIVE, `15–50 %` PRESUMPTIVE, `≥ 50 %` POSITIVE (tunable).
