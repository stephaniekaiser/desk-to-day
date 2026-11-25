# Theme packages

Each folder here is one theme package: a `theme.json` plus its art. The planner bundles every package
(`pack_themes.py` copies them into the page), and later a "Get more themes" catalog can download the same
packages.

## theme.json

| Field | What it is |
|---|---|
| `format` | Package format version (1) |
| `id`, `name`, `blurb` | Identity shown in Settings |
| `version`, `updated`, `notes` | Bumped when the theme grows (new friend, new season); notes can be shown to the user |
| `kind` / `storybook` | `storybook` themes get the scene, the big card and the Storybook section |
| `perks`, `card` | Card labels and the card picture |
| `binder` | Suggested cover + rings (the binder itself is the person's setting) |
| `tabPal`, `tabs`, `vars` | Tab colors and color tokens |
| `swatches`, `catSwatches` | The theme's look for each saved color key |
| `fHead`, `fBody`, `fontFace` | Fonts (`fontFace.file` is in this folder) |
| `paper`, `quote`, `quotes` | Paper color and rotating quotes |
| `img.dir`, `img.paper` | Art folder and paper texture |
| `scene.sets` | The place for a time of year: `months`, `perch`, `under` (strips), `extras` |
| `scene.casts` | Animal friends that rotate by day: `over` pieces. A piece with `holds: {x,y}` sits in the tree holding the season's item and drops it into the basket on a check-off; with no holder, the item drifts down from the branch. `flutter: true` gives a ground friend a tiny wing flutter as the item lands |
| `sets[].item` | The season's item that lands in the basket (`src`, `w`, `h`); `driftY` is where it lets go of the branch on quiet days |
| `sets[].pile` | The weekly basket: `anchor: underPerch` puts it under the branch tip (`dx` nudges it), `states` pick the art by how many things are done this week |
| `scene.quote`, `quoteClear`, `quoteY` | Where the quote sits |

Scene piece anchors: `spread` (top strip across both pages), `spreadBottom` (repeating ground strip),
`onStrip` (sits on the top strip at the set's `perch`), `tl` / `tr` / `bl` / `br` (page corners). Sizes are px at a
1180-wide screen. `page` is `L` (tasks page) or `R` (calendar page).
