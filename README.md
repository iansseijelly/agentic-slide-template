# Slide template

## Setup

Requires Node.js 22.12 or later.

```sh
npm ci
npm run dev
```

Open the local URL printed by Slidev. Edit the Markdown files in `src/slides/`
for content. `src/slides.md` sets deck options and assembles those files in order
using `src:` entries. Edit `src/style.css` for styling, and `src/deck.config.ts`
for settings shared across the deck. Put images in `src/assets/figures/` and reference them from the slide files
with `<img src="../assets/figures/example.svg" alt="Description" />`.

## Generate

Build the HTML presentation into `dist/`:

```sh
npm run build
```

Install Chromium and its system libraries once for PDF export on Linux
(the system-library step may ask for sudo):

```sh
npx playwright install --with-deps chromium
```

On macOS or Windows, use `npx playwright install chromium`.

Generate light and dark PDFs in `exports/`:

```sh
npm run export:latte
npm run export:mocha
```

Choose a filename (add `--dark` for Mocha):

```sh
npm run export -- --output exports/my-talk.pdf
npm run export -- --dark --output exports/my-talk-dark.pdf
```

Set `exportFilename` in `src/slides.md` to change the default for `npm run export`.
The `export:latte` and `export:mocha` shortcuts keep their fixed filenames.
