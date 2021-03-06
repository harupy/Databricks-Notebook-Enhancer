# DBEditor

A Chrome extension to provide useful code editting features on Databricks.

<kbd>
  <img src="https://user-images.githubusercontent.com/17039389/60017754-7ad44980-96c4-11e9-8ff4-8a680ff393fd.gif">
</kbd>

## What this extension provides

- Shortcuts
- Code Snippets

## Installation

[DBEditor - Chrome Web Store](https://chrome.google.com/webstore/detail/dbeditor/nlnifkmijjmmoaindmhbcdfinkcmfafj)

## Getting Started

1. Open a Databricks notebook on the browser
1. Make sure the extension logo is enabled (the extension logo is enabled)
1. Select a cell and enter the edit mode
1. Type `dp` and press `Tab` (`dp` will be expanded to `display()`)
1. Type `df.gb` and press `Tab` (`gb` will be expanded to `groupBy()`)
1. Press `Ctrl-U` (The current line will be duplicated below)

## Build from the Source

1. Clone this repository
1. `npm install`
1. `npm build`
1. Open `chrome://extensions` on Chrome
1. Enable `Developer mode` if it's disabled
1. Click `Load unpacked`
1. Select `src` in the extension directory

## Shortcuts

**Note that some default shortcuts in Chrome are overridden.**

| Shortcut     | Action                                     |
| :----------- | :----------------------------------------- |
| Ctrl-K       | Delete the word the cursor is on           |
| Ctrl-O       | Open a blank line below                    |
| Ctrl-Shift-O | Open a blank line above                    |
| Ctrl-L       | Delete up to the end of the current line   |
| Ctrl-H       | Delete up to the start of the current line |
| Ctrl-U       | Duplicate the current line below           |
| Ctrl-Shift-U | Duplicate the current line above           |

## Snippets (Press `Tab` to expand)

[Snippets List](./docs/snippets.md)

## Add your own snippets

You can add your own snippets by inserting a new key/value pair to the variable `snippets` in `snippets.js`.

```js
const snippets = {
  ...
  // your own snippet
  'mf'   : 'myFunc(${args})',
}
```

## How this extension works

Each cell on the notebook has an object called `CodeMirror` which manages the cell content and state. This extension injects a JS script to override the properties related to key bindings and add new features not provided by default.

## Other Extensions

| Extension Name                             | Purpose                                   |
| :----------------------------------------- | :---------------------------------------- |
| [DBVim](https://github.com/harupy/vim)     | Enable Vim on Databricks                  |
| [DBDark](https://github.com/harupy/dbdark) | Provide a dark theme on Databricks        |
| [DBToc](https://github.com/harupy/dbtoc)   | Create a table of contents with one click |
| [DBHide](https://github.com/harupy/dbhide) | Hide unnecessary code and cells           |

## References

- [CodeMirror: User Manual](https://codemirror.net/doc/manual.html)

## Acknowledgements

A huge thanks to Databricks for making big data simple.

## License

MIT
