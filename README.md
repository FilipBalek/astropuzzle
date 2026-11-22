# astropuzzle

A daily star puzzle. Six guesses for one real star's apparent magnitude and
distance, then the sky shows where it actually is. 274 named stars, seeded by
the date.

- **274 named stars** from the Yale Bright Star Catalogue, one a day.
- **Dealt like a deck, not drawn at random**: every star appears once before any
  appears twice, so there is no repeat for 274 days.
- **The sky is real.** Every dot is a catalogued star at its real position with
  its own colour from its own temperature; the reward opens the field around the
  answer at true magnification, north up, east left.
- **No server, no account, no tracking.** Progress lives in `localStorage` on the
  device and nowhere else.

## How it plays

The screen shows one star among its neighbours, as you would see it. Guess two
numbers: how bright it looks, and how far away it is.

Magnitude can be judged by eye, comparing it with the stars around it. Distance
has to be known, or reasoned out from what you know about the star. Each half
locks on its own, and both answers use the same feedback: ice for right, violet
for close, rose for far off.

## Run it

It is a static page, but it fetches its catalogue, so serve it over http rather
than opening the file from disk:

```
python -m http.server 8000
```

then open <http://localhost:8000/>.

It is published with GitHub Pages straight from this branch: `index.html` and
`star-data/stars.json` are the whole application.

## Data

Stars: the **Yale Bright Star Catalogue**, 5th Revised Edition (Hoffleit &
Warren, 1991), public domain, via the JSON mirror at
[brettonw/YaleBrightStarCatalog](https://github.com/brettonw/YaleBrightStarCatalog).

`star-data/stars.json` is a derived subset, ten fields per star. No value was
altered: fields were dropped and distances were converted from the catalogue's
parallax (arcseconds) to light-years.

## Licence

Code, design and copy: MIT, see [LICENSE](LICENSE).

Third-party material: see [NOTICE](NOTICE).
