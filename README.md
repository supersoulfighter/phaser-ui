# phaser-ui

A tiny UI component library (labels, buttons, inputs) built on Phaser
GameObjects, written for script-tag globals — no imports or modules —
so it works in plain web pages and the Phaser Desktop app.

Requires the global `Phaser` object (tested on Phaser 4).

## Usage

Vendor it into a Phaser project, typically as a git submodule:

```bash
git submodule add https://github.com/supersoulfighter/phaser-ui.git <path>
```

Then concatenate (or script-tag) the files before your game code.
Alphabetical order is already the correct load order:

| File            | Contents                                            |
|-----------------|-----------------------------------------------------|
| `UI.js`         | Shared `UI` namespace + `UIComponent` base class    |
| `UIButton.js`   | `UIButton` component                                |
| `UIInput.js`    | `UIInput` component                                 |
| `UILabel.js`    | `UILabel` component                                 |
| `UIRegister.js` | Registers `this.add.uiButton()` / `this.make.*()`   |

Order matters: `UI.js` defines the base class the components extend,
and `UIRegister.js` must run after all component classes exist.
