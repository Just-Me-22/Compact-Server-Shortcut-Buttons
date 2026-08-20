Discord stacks up to six shortcut buttons above your channel list, each one a full-width
row with a label on it. This turns them into one row of icons at the top of the sidebar, so
your channels start higher up. The buttons split the width between them, so a server with one
button gets one wide button and a server with four gets four narrow ones. Whichever one you
have open turns purple and gets an underline.

Built against stock Discord dark.

## Install

Paste this into **QuickCSS**. No theme needed.

```css
@import url("https://raw.githubusercontent.com/Just-Me-22/Compact-Server-Shortcut-Buttons/main/compact-server-shortcuts.css");
```

## License

[CC0 1.0 Universal](LICENSE). Public domain, no attribution needed.

## Values you may want to change

`--sh-gap` is the space between the buttons and `--sh-tile-w` is the narrowest a button will
get before the row wraps. `--sh-lift` pulls the row up towards the divider above it,
`--sh-fill` is the background on each button, and `--sh-ink` is the purple.
