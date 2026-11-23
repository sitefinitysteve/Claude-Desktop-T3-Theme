# Claude Desktop T3

A [T3 Code](https://github.com/pingdotgg/t3code) theme that matches the Claude desktop app, in dark and light.

## Install

### Option 1: Search in T3 Code

1. Open **Settings → Appearance → Add a theme**.
2. Search for **Claude Desktop T3**.
3. Click **Install**.

This installs the colors only. T3 Code doesn't load custom CSS from Open VSX themes.

### Option 2: Import the full theme (recommended)

This version includes the custom CSS: the Claude-style composer, send buttons colored by model (Claude orange, Gemini blue), and restyled menus, dialogs, settings, switches and tooltips.

1. Download [`claude-desktop.json`](./claude-desktop.json).
2. In T3 Code, open **Settings → Appearance → Add a theme → Import a file**.
3. Choose the downloaded file.

## VS Code

The Open VSX package is also a regular VS Code color theme. Install **Claude Desktop T3** from Open VSX (VSCodium, Cursor and others) and pick *Claude Desktop T3 Dark* or *Claude Desktop T3 Light*.

## Files

| Path | What it is |
| --- | --- |
| `claude-desktop.json` | The full T3 Code theme: colors, light variant and custom CSS |
| `themes/claude-desktop-dark.json` | VS Code color theme (dark), used by the Open VSX package |
| `themes/claude-desktop-light.json` | VS Code color theme (light), used by the Open VSX package |
| `package.json` | Extension manifest for Open VSX |

## Building

```sh
npx @vscode/vsce package
npx ovsx publish claude-desktop-t3-<version>.vsix -p <token>
```

## Credits

Made by [sitefinitysteve](https://www.sitefinitysteve.com). Not affiliated with Anthropic.

## License

[MIT](./LICENSE)
