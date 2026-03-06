# NODES — Personal Knowledge System

TRON Ares–themed encrypted note viewer with local edit server.

## Files

| File | Role |
|---|---|
| `index.html` | Login screen + Archimedes auth animation → deploys to GitHub Pages |
| `view.html` | Read-only note viewer (3-column grid, laser widget) → deploys to GitHub Pages |
| `edit.html` | Full CRUD editor — **requires local server** |
| `nodes_server.py` | Local Python HTTP server (no dependencies) |
| `data/notes.json` | Note data |
| `start_nodes.bat` | Windows one-click launcher |

## PIN

Default: **3141**  (change `const PIN` in `index.html`)

## Local editing workflow

```bash
python nodes_server.py
# Opens http://localhost:5000  →  editor
# http://localhost:5000/view   →  viewer (live JSON)
# http://localhost:5000/login  →  login page
```

`Ctrl+S` saves in the editor. Theme and auth state persist via `sessionStorage` — switching between viewer and editor keeps you logged in.

## GitHub Pages deployment

Push `index.html`, `view.html`, and `data/notes.json` to the repo root.
Enable GitHub Pages → branch `main` → root `/`.

Public URL serves the login page (`index.html`).  
The viewer (`view.html`) fetches `./data/notes.json` statically.  
The editor (`edit.html`) is local-only — no need to push it.

## Theme

Toggle between **CLASSIC** (cyan) and **ARES** (red-orange) on any screen.
Theme choice persists across all pages via `sessionStorage`.
