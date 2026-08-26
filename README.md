Discord stacks up to six shortcut buttons above your channel list, each one a full-width
row with a label on it. This turns them into one row of icons at the top of the sidebar, so
your channels start higher up. The buttons split the width between them, so a server with one
button gets one wide button and a server with four gets four narrow ones. Whichever one you
have open turns purple and takes a small tick in its top corner. Hovering any of the others
fills it from the bottom up.

On servers that show Discord's "Get Started" card, that gets the same surface as the buttons
and keeps a row of its own. The DM sidebar is left alone.

Built against stock Discord dark.

## Install

Paste this into **QuickCSS**. No theme needed.

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

## How it works

**Telling the two sidebars apart.** The server channel list and the DM list use the same `ul`
class, so the `ul` is no help. The `nav` above it is: the DM one is `privateChannels_` and the
server one is not. Every layout rule here is scoped to `nav:not([class*="privateChannels_"])`,
which is what keeps the sheet out of the Friends / Nitro / Shop rows.

**Picking out a shortcut button.** The list items that hold a shortcut button, the Get Started
card and the server banner all carry no class at all, and the buttons are not even at a
consistent depth: Members sits one div deeper than Channels & Roles. Nothing on the row itself
separates them, so the row has to be asked what it contains. A shortcut button carries
`containerDefault` and `wrapper` on a single element, while a channel row splits those two
classes over two elements, so `:has([class*="containerDefault"][class*="wrapper"])` cannot
match a channel by accident.

That `:has()` is a structural test, not a state one. It is re-evaluated when the channel list
changes, not on every hover or scroll frame, which is where `:has()` gets expensive. There is
no `:has(:hover)` anywhere in the sheet.

**The gap above the row.** The Get Started card carries the space below itself rather than the
buttons carrying it above them, so nothing has to work out whether the card is present. The
card also sits 8px above its own list item on a negative margin, which is why its margin is
replaced rather than added to.

**The hover fill and the tick.** The fill is a pseudo-element scaled from `scaleY(0)` on the
bottom edge, so it composites and never touches layout. The link clips it to the tile's
corners. The tick hangs off the link rather than the wrapper because the wrapper's `::after`
is already drawing the divider rule, and the link inherits the tile's radius so the tick clips
to the rounded corner instead of poking past it. The button you are already on does not do the
climb.

### Changed in 4.4.0

`--sh-lift` is gone. It pulled the row *up* by its value, which is what put the buttons on
top of a server banner. `--sh-top` replaces it and pushes the row *down* instead.

`--sh-mark` is gone with the underline it drew. The open button now takes `--sh-tick`.

Two bugs went with them. The buttons used to be picked out by having no class on them,
which meant Discord's Get Started card got treated as a button and squeezed into the row,
and the whole DM sidebar got rearranged along with it. Both are matched properly now.
