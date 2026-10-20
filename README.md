# solstice-bar.github.io

Static pages for Solstice, served by GitHub Pages.

- **`p/`** — the shared place links (`https://solstice-bar.github.io/p/?id=…&ll=…&n=…`).
  `.well-known/apple-app-site-association` and `.well-known/assetlinks.json` let iOS and Android
  hand those links straight to the app; `.nojekyll` keeps GitHub Pages from dropping the dot folder.
  `p/index.html` is what someone without the app sees: the place's name, a way into the app, the
  App Store. The app side is `src/lib/places/place-link.ts` in the app's repository.
- **`street-photos/v1/`** — the Panoramax photos the place sheet shows (`index.json` and `photos/`,
  Licence Ouverte 2.0 or CC BY-SA 4.0, author and licence per photo). The index stays
  `reviewed: false` until the team has checked every photo (verification desk, mission 3); until
  then only test builds show them. The index holds only photos the team judged OK and nobody
  refused (`tools/apply_photo_verdicts.py` in solstice-ground-truth, 2026-10-20: 216 of 415, 52
  refused for a face, a plate or the wrong place, and their files deleted). Never add a photo by
  hand: rebuild the index and run that tool again.
- **`terrace-lab/v1/`** — *superseded.* The Labo's terrace footprints now live in the places
  channels (`solstice-places-beta/v1/lab/`, built and promoted with the places since 2026-10-20);
  no app version reads this copy any more, and it can go once production's channel serves the Labo.

The data processes behind all of this are described in the app repository: `docs/data-pipeline.md`.
