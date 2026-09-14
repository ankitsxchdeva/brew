# brew sheet

A single-page tool that renders a filter coffee recipe as a 100 x 150 mm sheet
for a label printer. Print goes through `@page`; the PNG export rasterises the
same SVG at 300 dpi and thresholds it to 1 bit.

## Design

All design decisions follow ~/Documents/personal/design/DESIGN.md (canonical
lane). Do not invent colors, fonts, spacing, or motion outside it. Where any
skill or model suggestion conflicts, the spec wins. `tokens.css` is a verbatim
copy; refresh it from the spec rather than editing it here.

### Declared deviation: the sheet is print output, not UI

The rendered sheet inside `#paper` is ink on thermal label stock, so it is
exempt from three §1/§2 rules. Everything else on the page, the chrome around
it, is canonical.

1. **Pure `#000` on `#fff`.** Thermal heads are 1 bit: they have no grey, and a
   tinted neutral would dither into noise. The sheet's own ink stays pure.
2. **Its own typefaces.** The sheet is set in Futura and Avenir Next, not Lato.
   The PNG export rasterises the SVG through an `<img>`, and a document
   `@font-face` does not reach inside that image, so the sheet can only use
   fonts installed on the machine.
3. **Its own type scale.** Sheet type is sized in millimetres for reading at
   arm's length while brewing, so the 32px display cap does not apply to it.

The chrome carries no exemptions: tinted neutrals, one accent, hairlines, one
family, one clock, lowercase voice, both themes.
