# QA Report — ALBAZ Yallop Crescent Visibility Maps v9.6.3

Test date: 2026-08-02

## Scientific identity

- Verified the presence of `calcYallopAt`.
- Verified the implemented Yallop polynomial:
  `11.8371 - 6.3226W + 0.7319W² - 0.1018W³`.
- Verified the q definition:
  `q = (ARCV - yallopLimit) / 10`.
- Verified the six thresholds:
  - A: `q > +0.216`
  - B: `q > -0.014`
  - C: `q > -0.160`
  - D: `q > -0.232`
  - E: `q > -0.293`
  - F: all lower values

## Web package checks

- JavaScript syntax: PASS using Node.js `--check` for all inline scripts.
- Embedded font payloads: none.
- Native mobile bridges and Android-only labels: none.
- Static HTTP delivery: PASS (`200`) for `index.html`, `guide.html`, `manifest.webmanifest`, `icon.svg`, and `404.html`.
- ZIP integrity: PASS.

## Browser runtime checks

Headless Chromium tests were completed for desktop and mobile viewport sizes.

- Page load: PASS.
- Splash screen closes: PASS.
- JavaScript page errors: none.
- Console errors: none.
- Horizontal page overflow: `0 px` on desktop and mobile.
- Scientific guide loads and contains the q equation: PASS.
- Desktop map calculation at 10° grid resolution: PASS.
- Progress reached `100%`: PASS.
- Canvas output contained rendered pixels: PASS.

## Reference calculation used in the runtime test

Case: Baghdad, Iraq — 2026-08-14.

- Resulting class: A
- q: approximately `0.877606`
- ARCV: approximately `12.354716°`
- W: approximately `1.516164 arcmin`
- Moon lag: approximately `56.5637 minutes`

This reference calculation confirms that the calculation path executes successfully; it is not presented as an external ephemeris validation.

## Deployment conclusion

The package is structurally ready for deployment from the root of a dedicated GitHub repository using GitHub Pages.
