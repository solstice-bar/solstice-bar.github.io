# solstice-bar.github.io

The site behind Solstice's shared place links (`https://solstice-bar.github.io/p/?id=…&ll=…&n=…`).

- `.well-known/apple-app-site-association` and `.well-known/assetlinks.json` let iOS and Android
  hand those links straight to the app. `.nojekyll` keeps GitHub Pages from dropping the dot folder.
- `p/index.html` is what someone without the app sees: the place's name, a way into the app,
  the App Store.

The app side is `src/lib/places/place-link.ts` in the app's repository.
