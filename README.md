# brew

Turns a filter coffee recipe into a printable sheet — sized for a 100 x 150 mm label by default, with standard paper sizes (a6, a5, a4, us letter) also on offer.

**Running:** [ankitsachdeva.com/brew](https://ankitsachdeva.com/brew/) — no build step, no dependencies.

Edit the recipe on the right, watch the sheet on the left, then print or export:

- **print** sets `@page { size: …; margin: 0 }` from the chosen page size, so the sheet prints vector at exact size.
- **save png** rasterises the same SVG at 300 dpi and thresholds it to pure black and white, for printer software that wants an image.

The sheet is one SVG drawn in millimetre coordinates. The timeline grows its type to fill the sheet, then spreads the steps; with a long recipe it shrinks instead, and says so when a recipe still will not fit.

Switch steps carry a lever marker with the knob down (shut) or up (open), so a Hario Switch recipe reads at a glance.

Recipes persist in the browser, one at a time.

## Design

Canonical lane of [colophon](https://github.com/ankitsxchdeva/design). `tokens.css` is a verbatim copy of the spec's tokens. The printed sheet declares three exemptions, listed in [`AGENTS.md`](AGENTS.md): it is ink on thermal stock, not UI.

## License

MIT (c) Ankit Sachdeva
