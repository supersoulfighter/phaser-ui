# phaser-ui

A tiny UI component library (labels, buttons, inputs) built on Phaser
GameObjects

## For Phaser Desktop
Phaser's online coding environment, "Desktop", puts all JavaScript
into a single global scope, no imports or modules. This library
is written with that in mind. It assumes that the global `Phaser`
object already exists (tested on Phaser 4).

You need to control load
order yourself, typically by loading the js scripts in the correct
order in the HTML file, or by naming src files and folders so that they 
get concatenated in the correct order by a concatenation tool like
vite-plugin-concat.

Personally, I use a git submodule, effectively embedding the library
into the project that is consuming the library as source code:

```bash
git submodule add https://github.com/supersoulfighter/phaser-ui.git <path>
```

## Contents

| File            | Contents                                            |
|-----------------|-----------------------------------------------------|
| `UI.js`         | Shared `UI` namespace + `UIComponent` base class    |
| `UIButton.js`   | `UIButton` component                                |
| `UIInput.js`    | `UIInput` component                                 |
| `UILabel.js`    | `UILabel` component                                 |
| `UIRegister.js` | Registers `this.add.uiButton()` / `this.make.*()`   |

Given the global scope of Phaser Desktop, load order matters.
`UI.js` defines the base class the components extend,
and `UIRegister.js` must run after all component classes exist.
