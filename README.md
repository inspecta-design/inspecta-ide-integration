# Inspecta IDE Integration

A VS Code/Cursor IDE extension that integrates with Inspecta to receive CSS changes and custom prompts and apply them using AI capabilities (Cursor AI, GitHub Copilot, or manual processing).

## Features

- **Edit in the browser, apply in your code** — Tweaks you make with Inspecta show up in Cursor right away so you can put them into your real CSS files.
- **AI does the heavy lifting** — Cursor AI or GitHub Copilot suggests where and how to apply changes, so you spend less time hunting for the right selectors and files.
- **Fits your project** — The extension looks at your workspace and applies changes in a way that matches how your project is set up.
- **Your choice of AI** — Use Cursor’s built-in AI, GitHub Copilot, or apply changes yourself; the extension works with whatever you prefer.

## Installation

### Prerequisites

- Cursor IDE or VS Code (latest version)
- Inspecta Chrome extension
- GitHub Copilot (optional, for VS Code users who want Copilot processing)

### Install from VSIX

1. Download or obtain the extension `.vsix` file
2. Open Cursor or VS Code
3. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac)
4. Run **Extensions: Install from VSIX**
5. Select the `.vsix` file

## Usage

### Starting the server

The server does not start automatically. Start it in either way:

- **Click the status bar** — In the bottom-right you’ll see something like “Inspecta: Closed (Click to Open)”. Click it to start; click again when you’re done to turn it off.
- **Use the command palette** — Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac), type **Inspecta**, then pick **Start Inspecta Server** or **Toggle Inspecta Server**.

That’s it. The connection uses port 8080 by default; you can change it in settings if you need to.

### Using with Inspecta

1. Start the Inspecta server in Cursor (see above)
2. Open a webpage with the Inspecta Chrome extension
3. Make CSS changes in Inspecta
4. Click **Send to Cursor** in Inspecta
5. Changes are sent to the IDE and processed by AI; you can then apply them to your CSS files

## Configuration

In Cursor/VS Code settings you can set:

| Setting | Description | Default |
|--------|-------------|--------|
| `inspecta-ide.serverPort` | Port for the Inspecta server | 8080 |
| `inspecta-ide.autoStart` | Start the server when the IDE opens | false |

## How it works

1. **Inspecta** (browser) sends CSS changes over WebSocket to the extension
2. The **extension** receives them and hands them to Cursor AI or GitHub Copilot
3. The **AI** suggests edits; you apply them to the right CSS files in your workspace

## Troubleshooting

**Server won’t start**

- Ensure port 8080 (or your configured port) is free
- Change the port in settings if needed, then restart the IDE

**No changes received**

- Confirm the server is running (status bar shows “Inspecta: Open…”)
- In the browser, check that Inspecta is sending to the same port (e.g. 8080)
- In browser dev tools, check the WebSocket connection for errors

**AI doesn’t apply changes**

- Ensure Cursor AI or GitHub Copilot is available and working
- Check the IDE’s output/console for errors from the extension

## License

This extension is part of the Inspecta and follows the same license terms.
