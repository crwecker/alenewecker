# alenewecker.com

Author website for Alene Wecker. Plain static HTML/CSS, no build step.

- `index.html`: the whole site
- `styles.css`: styles
- `images/`: book covers, author photo, social share image (`og.jpg`)

## Preview locally

    python3 -m http.server 8000
    # open http://localhost:8000

## Adding a new book

Copy an `<article class="book">` block in `index.html`, drop the cover in `images/`,
and update the title, blurb, and buy links. Add `book-flip` to alternate the cover side.

See [DEPLOY.md](DEPLOY.md) for hosting and pointing the Squarespace domain.
