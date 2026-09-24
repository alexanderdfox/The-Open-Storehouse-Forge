# The Open Storehouse Forge — Sovereign Engine v2

A fully client-side, Git-inspired multi-file workspace.  
Repositories, branches, commits, diffs, and file trees live in your browser (`localStorage`). No server required.

Open `open-storehouse-forge-v2.html` in any modern browser to start.

---

## Quick Start

1. Open the HTML file in Chrome, Firefox, Safari, or Edge.
2. You’ll see a seed repository (`bakers-oven-v4`) already loaded.
3. Click a repo in the left sidebar, or click **🛠 Forge Repository** to create a new one.

Everything is stored locally under the key `storehouse_forge_v5`. Clearing site data will wipe your workspaces.

---

## Core Concepts

| Concept            | What it is |
|--------------------|------------|
| **Repository**     | A named blueprint workspace (like a Git repo). |
| **Track / Branch** | An independent line of history (like a Git branch). |
| **Snapshot / Commit** | A point-in-time copy of all files on a track. |
| **Component Tree** | The file list (supports nested folders). |
| **HEAD**           | The latest commit on the active track. Uncommitted edits are compared against it. |

---

## Working with Repositories

- **Create** — Header button **🛠 Forge Repository** (or the button on the welcome screen).  
  You’ll be asked for a name and a short description.
- **Switch** — Click any repo in the left **Blueprints** list.
- **Delete** — Open a repo → **Scrap Repository** (permanent, no undo).

---

## Files & Folders

- **Add file** — **+ File**. Paths with `/` create nested folders automatically  
  (example: `src/core/thermal.config`).
- **Add folder** — **+ Folder**. Creates a placeholder `.keep` file inside the path.
- **Open** — Click any file in the Component Tree.
- **Rename** — With a file open, click **Rename**.
- **Delete** — **Delete** button (a repo must keep at least one file).
- **Dirty indicator** — Orange dot next to a file = uncommitted changes.  
  Repos also show a badge with the number of dirty files.

### Search

Use the **Search** box in the sidebar. It filters by filename **and** file content.

---

## Editing & Committing

1. Select a file and edit in the textarea.
2. The **Uncommitted Changes** panel shows a live line diff against HEAD.
3. Write a message in the commit box and click **Commit changes**  
   (or press `Ctrl/Cmd + S` / `Ctrl/Cmd + Enter`).

The commit button stays disabled when there is nothing to commit.

### Markdown preview

For `.md` files, click **Preview MD** (or press `Ctrl/Cmd + P`) to toggle a simple rendered view.

---

## Branches (Tracks)

- **Active track** is shown in the branch bar dropdown.
- **+ Fork** — Creates a new branch as a full copy of the current track and switches to it.
- **⎔ Merge** — Merges another track into the current one.  
  Conflicting files receive standard conflict markers:
  ```
  <<<<<<< CURRENT (branch-name)
  ...
  =======
  ...
  >>>>>>> INCOMING (other-branch)
  ```
  Resolve the markers manually, then commit.
- **Delete Track** — Removes the active branch (you cannot delete the last remaining branch).

---

## Commit History (Chronicle)

Each commit shows four actions:

| Button              | Effect |
|---------------------|--------|
| **Inspect file**    | Loads that file’s content from the chosen snapshot into the editor (edits still affect the live workspace). |
| **Restore full tree** | Replaces *all* files on the current track with the snapshot. |
| **Branch from here** | Creates a new track starting from that commit. |
| **Revert to this**  | Creates a *new* commit that restores the tree to the chosen snapshot (history is not rewritten). |

---

## Mesh Network (Simulated)

Enter a peer address (any string, e.g. `ipfs://…`) and click **Mesh Pull** or **Mesh Push**.  
This is a visual/demo simulation only — no real network calls are made.

---

## Cold-Storage Vault

| Action | Description |
|--------|-------------|
| **Export Ledger JSON** | Downloads the entire local state (all repos, branches, history). |
| **Import Ledger JSON** | Replaces current state with a previously exported ledger (asks for confirmation). |
| **Export Active Repo** | Downloads only the files of the currently open repo + branch. |

---

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl/Cmd + S` or `Ctrl/Cmd + Enter` | Commit |
| `Ctrl/Cmd + P` | Toggle Markdown preview (`.md` files) |
| `Ctrl/Cmd + N` | New file |
| `Esc` | Close modal |

---

## Data & Persistence

- All data lives in `localStorage` under `storehouse_forge_v5`.
- Export regularly if the work matters — browser storage can be cleared by the user or by privacy tools.
- The seed repo is only used when no existing data is found.

---

## Tips

- Keep commit messages descriptive; they appear in the Chronicle.
- Use nested paths (`docs/`, `src/`, `config/`) to keep larger blueprints organized.
- After a merge with conflicts, search the file for `<<<<<<<` to find every conflict block.
- “Restore full tree” is powerful — it overwrites the working copy. Prefer **Branch from here** if you only want to explore an old state.

---

## File Overview

| File | Purpose |
|------|---------|
| `open-storehouse-forge-v2.html` | The complete application (open this). |
| `README.md` | This guide. |

Enjoy forging.
