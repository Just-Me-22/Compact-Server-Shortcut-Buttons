# Server Header

Discord stacks up to six shortcut buttons above your channel list, each one a full-width
row with a label on it. This turns them into a single bar of icon tiles across the top of
the sidebar, so your channels start higher up. Whichever one you have open stays lit.

The boost goal bar gets a sheen that sweeps across it cuz why not. It only runs while you
hover the bar.

Built against stock Discord dark.

## Install

Paste this into **QuickCSS**. No theme needed.

```css
@import url("https://raw.githubusercontent.com/Just-Me-22/server-header/main/server-header.css");
```

## Knobs

All of them sit at the top of the file. Change any value.

| | |
|---|---|
| `--sh-boost-ground` | the bar's dark end |
| `--sh-boost-light` | its bright end |
| `--sh-boost-sheen` | the light that travels across it |
| `--sh-boost-ink` | the label and the boost count |
| `--sh-boost-edge` | the rule under the bar |
| `--sh-drift` | one pass of the sheen |
| `--sh-tile` | how tall the bar is |
| `--sh-icon` | the glyph size |
| `--sh-lift` | how far the bar sits up toward the boost goal |
| `--sh-tile-bg` | the band behind the glyphs |
| `--sh-tile-lit` | a tile on hover |
| `--sh-tile-sel` | the one you have open |
| `--sh-tile-ink` | glyph colour on hover |
| `--sh-fade` | how fast a tile lights up |

## Notes

No `:has()` anywhere. The `<li>` wrappers Discord puts around every row have no class, so
getting the tiles onto one line uses `display: contents` on the `li` and lets the rows
themselves become the flex items.

That has a cost worth knowing about: `display: contents` takes those `li` elements out of
the accessibility tree, so a screen reader no longer reads the channel list as a list with
N items. If that matters more to you than the vertical space, skip this one.

## License

[CC0 1.0 Universal](LICENSE). Public domain, no attribution needed.
