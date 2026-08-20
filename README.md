Discord stacks up to six shortcut buttons above your channel list, each one a full-width
row with a label on it. This turns them into one small row of icons at the top of
the sidebar, so your channels start higher up. Whichever one you have open turns purple and
gets an underline.

Built against stock Discord dark.

## Install

Paste this into **QuickCSS**. No theme needed.

```css
@import url("https://raw.githubusercontent.com/Just-Me-22/Compact-Server-Shortcut-Buttons/main/compact-server-shortcuts.css");
```

## License

[CC0 1.0 Universal](LICENSE). Public domain, no attribution needed.

## Values you may want to change

`--sh-gap` is the space between the icons and `--sh-tile-w` is how wide each one is.
`--sh-lift` pulls the row up towards the divider above it, and `--sh-ink` is the purple.

The row centres itself, so it stays in the middle whether a server gives you one button or
six. You should not need to nudge it.
