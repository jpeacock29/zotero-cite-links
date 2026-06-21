# Zotero Cite Links

Cmd-click a Pandoc-style `@citekey` in an Obsidian note to open the cited PDF in Zotero — at the page locator from the citation, with annotation-aware page-label offsetting.

`[@hickman1987, p. 8]` → Cmd-click `hickman1987` → Zotero opens the linked PDF at page 8.

## Why

Obsidian's citation-aware plugins (e.g. Pandoc Reference List) show a bibliography sidebar and tooltips, but their best "open" action drops you in the Zotero collection view — you still have to navigate to the PDF and the page yourself. This plugin closes the last step.

## Requirements

- Obsidian 1.4.0+ (desktop only — uses Node `http` against localhost).
- [Zotero](https://www.zotero.org/) with the [Better BibTeX](https://retorque.re/zotero-better-bibtex/) extension installed and running.

This plugin communicates only with your local Zotero/Better BibTeX over `127.0.0.1`, to resolve citation keys to their PDF attachments and page locators — no data leaves your machine, and it makes no other network requests.

## Installation

### From the community plugin directory

*(pending review — for now, install manually below.)*

### Manual

1. Download `main.js`, `manifest.json`, and `styles.css` from the latest [release](https://github.com/jpeacock29/zotero-cite-links/releases).
2. Place them in `<vault>/.obsidian/plugins/zotero-cite-links/`.
3. Reload Obsidian → Settings → Community plugins → enable **Zotero Cite Links**.

## Usage

- **Cmd-click** any `@citekey` in a note. If the citation includes a page locator (`[@key, p. 5]` or `[@key, 5]`), the PDF opens at that page.
- **Command palette** → "Zotero Cite Links: Open citation at cursor in Zotero" — opens the citekey nearest the cursor without clicking. Useful in source mode or when you'd rather use a hotkey.
- **Command palette** → "Zotero Cite Links: Refresh Zotero library list" — re-queries Better BibTeX for the list of libraries to search (groups and your personal library). Run after adding a new Zotero group.

## Settings

- **Zotero port** — Better BibTeX JSON-RPC port. Default `23119`.
- **Click modifier** — choose between Cmd/Ctrl-click (default, doesn't interfere with normal editor text selection) or plain click.

## Acknowledgements

The Better BibTeX integration approach draws on patterns from [mgmeyers/obsidian-pandoc-reference-list](https://github.com/mgmeyers/obsidian-pandoc-reference-list).
