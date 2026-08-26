
Discord stacks up to six shortcut buttons above your channel list, each one a full-width
row with a label on it. This turns them into one row of icons at the top of the sidebar, so
your channels start higher up. The buttons split the width between them, so a server with one
button gets one wide button and a server with four gets four narrow ones. Whichever one you
have open turns purple and takes a small tick in its top corner. Hovering any of the others
fills it from the bottom up.

## Install

Paste this into **QuickCSS**.

```css
@import url("https://raw.githubusercontent.com/Just-Me-22/Compact-Server-Shortcut-Buttons/main/compact-server-shortcuts.css");
```

## License

[CC0 1.0 Universal](LICENSE). Public domain, no attribution needed.

## Values you may want to change

| knob | does |
|---|---|
| `--sh-gap` | space between the buttons |
| `--sh-tile-w` | narrowest a button gets before the row wraps |
| `--sh-top` | clearance above the row when a Get Started card sits over it |
| `--sh-top-solo` | clearance when there is no card and the row meets the banner |
| `--sh-fill` | the background on each button |
| `--sh-ink` | the purple |
| `--sh-tick` | size of the corner tick on the open button |
| `--sh-rise` | colour that climbs the button on hover |
| `--sh-rise-ease` | how long that takes, and on what curve |

Set `--sh-rise-ease` to `0s` if you would rather it just appear.


