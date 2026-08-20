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

## The one value you may want to change

`--sh-indent` slides the row sideways. It is a fixed offset, not real centring, because
centring the row would need a wrapper element around just those buttons and Discord does not
render one. 88px lines up a four button server. Fewer buttons will sit left of centre, more
will sit right, so nudge it until it looks right on the servers you actually use.
