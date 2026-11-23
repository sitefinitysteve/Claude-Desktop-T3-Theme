<p align="center"><img src="images/icon.png" width="128" alt="Claude Desktop T3 icon"></p>

# Claude Desktop T3

A [T3 Code](https://github.com/pingdotgg/t3code) theme that matches the dark mode of the Claude desktop app.

## Install

1. Download **[claude-desktop.json](https://raw.githubusercontent.com/sitefinitysteve/Claude-Desktop-T3-Theme/main/claude-desktop.json)** (right-click → *Save Link As…*).
2. In T3 Code, open **Settings → Appearance → Add a theme**.
3. Under **Or import a file**, choose `claude-desktop.json`.

That's the whole theme: the colors **and** the custom CSS that gives it the Claude desktop look.

## What's in it

- Claude desktop dark palette for the sidebar, chat, code blocks and terminal
- Claude-style composer and message bubbles
- Send button colored by model (below)
- Restyled menus, popovers, dialogs, tooltips, toasts and settings (switches, selects, inputs, sliders)

### Send button colored by model

The composer's send button changes color to match the selected model's provider:

| Model | Send button |
| --- | --- |
| Claude | Claude orange |
| Gemini | Gemini blue |
| Anything else | Neutral white |

**Claude**

![Composer with a Claude model selected: orange send button](images/composer-claude.png)

**Gemini**

![Composer with a Gemini model selected: blue send button](images/composer-gemini.png)

**Other models**

![Composer with another model selected: white send button](images/composer-default.png)

## Design approach

The theme follows Claude Desktop's flat, minimal style. T3 Code's default theme takes a more layered approach with translucent panels, cards and accent colors; this one goes the other way and keeps styling to the elements that carry meaning. It follows a few rules:

**A short grey scale.** Every surface comes from a small ladder of greys, each a step apart:

| Grey | Used for |
| --- | --- |
| `#191919` | Canvas |
| `#1F1F1F` | Panels |
| `#262626` | Sidebar |
| `#2A2A2A` | Input fields |
| `#303030` | Message box |
| `#3B3B3B` | Selected items |
| `#404040` | Buttons |

Anything raised or interactive is one shade lighter, so structure reads without extra borders or shadows.

**Each color has one job.**

- **Blue** means on or focused: toggles, sliders, checkboxes and the focus ring.
- **Brand color** means which model you're using: the Claude asterisk, Gemini blue and the send button.
- **Red and green** mean removed and added in diffs. Red also marks destructive buttons.
- **Everything else is grey**, so when color shows up, it tells you something.

**Flat layout.** Settings, panels and the composer sit directly on the page, separated by thin dividers instead of framed cards.

**Contrast sets priority.** The main action in a dialog is light grey with dark text, the brightest thing on screen. Secondary buttons are mid grey and destructive ones are muted red.

**Inputs are easy to spot.** Every field is the same borderless box, one shade lighter than its background.

**Consistent proportions.** Corners use one scale: 8px for controls, 10px for panels, 12px for dialogs and the message box. Text sizes follow Claude Desktop's ratios (headings about 1.1× row titles, descriptions about 0.95×), and settings headings use medium weight instead of bold.

**Your work comes first.** Messages, code and diffs get the strongest text color and the most room. The interface around them stays quieter and lower contrast.

## Colors-only version (T3 Code search / Open VSX)

The theme is also listed in T3 Code's theme search: **Settings → Appearance → Add a theme**, search **Claude Desktop T3**.

> [!WARNING]
> The search version is **colors only**. It doesn't have the custom CSS, so no model-colored send button, composer styling or restyled menus and dialogs. Use the file above for the full theme.
>
> Why: T3 Code's search installs from Open VSX, which hosts VS Code extensions. A VS Code color theme can only hold colors, and T3 Code's importer reads just a fixed list of them. Anything else, including CSS, is ignored.

The same package also works as a regular VS Code color theme in VSCodium, Cursor and other editors that use Open VSX.

## Light mode

`claude-desktop.json` also has a light variant. It hasn't been checked against the Claude app's light mode, so treat it as a bonus rather than a match. The Open VSX version is dark only.

## Files

| Path | What it is |
| --- | --- |
| `claude-desktop.json` | **The theme.** Colors, custom CSS and an untested light variant |
| `themes/claude-desktop-dark.json` | Colors-only VS Code theme used for the Open VSX package |
| `package.json` | Extension manifest for Open VSX |
| `images/` | Icon and screenshots |

## Building the Open VSX package

Releases publish automatically: bump `version` in `package.json`, commit, then push a matching tag (`git tag v1.0.2 && git push --tags`). The [publish workflow](.github/workflows/publish.yml) uses Open VSX trusted publishing, so no token is stored.

To build and publish by hand instead:

```sh
npx @vscode/vsce package
npx ovsx publish claude-desktop-t3-<version>.vsix -p <token>
```

## Credits

Made by [sitefinitysteve](https://www.sitefinitysteve.com). Not affiliated with Anthropic.

## License

[MIT](./LICENSE)
