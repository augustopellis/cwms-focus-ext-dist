# cwms-focus-ext-dist

Public **distribution / auto-update host** for the **CWMS Focus Companion**
browser extension. It contains only the packaged extension and its update
manifest — no application code and no secrets.

- `ext/update.xml` — Chrome/Edge update manifest (`ExtensionInstallForcelist` points here)
- `ext/cwms-focus-companion.crx` — the signed extension package

Served via GitHub Pages:
- https://augustopellis.github.io/cwms-focus-ext-dist/ext/update.xml
- https://augustopellis.github.io/cwms-focus-ext-dist/ext/cwms-focus-companion.crx

Extension ID: `ahoblaffehjlaokdkmiklmhlpipgbble`

The extension only brings the CWMS browser tab/window to the front when the
CWMS inactivity prompt fires. Source, deployment guide and tooling live in the
private **CWMS-Web** repo under `tools/cwms-focus-extension/`.

## Publishing an update

1. Bump `version` in the extension `manifest.json` and re-pack with the **same**
   `.pem` signing key.
2. Replace `ext/cwms-focus-companion.crx` and bump `version="..."` in
   `ext/update.xml` to match.
3. Commit and push — deployed PCs update automatically within a few hours.
