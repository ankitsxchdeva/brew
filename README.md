# brew-sheet

Turns a filter coffee recipe into a 100 x 150 mm sheet for a label printer.

**Running:** [ankitsachdeva.com/brew-sheet](https://ankitsachdeva.com/brew-sheet/) — no build step, no dependencies.

Edit the recipe on the right, watch the sheet on the left, then print or export:

- **print** uses `@page { size: 100mm 150mm; margin: 0 }`, so the sheet prints vector at exact size.
- **save png** rasterises the same SVG at 300 dpi (1181 x 1772) and thresholds it to pure black and white, for printer software that wants an image.

The sheet is one SVG drawn in millimetre coordinates. The timeline grows its type to fill the sheet, then spreads the steps; with a long recipe it shrinks instead, and says so when a recipe still will not fit.

Switch steps carry a lever marker with the knob down (shut) or up (open), so a Hario Switch recipe reads at a glance.

Recipes persist in the browser, one at a time.

## Design

Canonical lane of [colophon](https://github.com/ankitsxchdeva/design). `tokens.css` is a verbatim copy of the spec's tokens. The printed sheet declares three exemptions, listed in [`AGENTS.md`](AGENTS.md): it is ink on thermal stock, not UI.

## License

MIT (c) Ankit Sachdeva
