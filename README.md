# The Open Storehouse Forge (Pro - Enterprise Sovereign Edition)

A **browser-native, decentralized Git-like forge** for crafting, versioning, and synchronizing sovereign blueprints, architectural plans, and document meshes.

Built as a single-file HTML application — no server, no installation, no corporate lock-in. Everything runs locally in your browser with persistent storage.

![Demo](https://github.com/alexanderdfox/The-Open-Storehouse-Forge/blob/main/screenshot.png) <!-- Add a screenshot if you upload one -->

## ✨ Features

- **Multi-Repository Management** — Create, switch, and delete independent blueprint workspaces ("Repos")
- **Branching & Forking** — Full timeline track support with easy forking and merging
- **Multi-File Editing** — Work on multiple documents per repository (Markdown, configs, plans, etc.)
- **Visual Diff Engine** — Real-time line-by-line diff between working changes and last commit
- **Commit Ledger / History** — Chronological record of all snapshots with inspectable states
- **Merge Engine** — Automatic conflict detection with standard conflict markers
- **Sovereign Mesh Network** — Simulated peer-to-peer synchronization (IPFS-style addressing)
- **Cold Storage Vault** — Export/import entire ledger state as JSON for backup & portability
- **Dark GitHub-inspired UI** — Clean, keyboard-friendly, fully functional in one file

## Philosophy

> "Free from centralized Oracle resources. Own your blueprints. Forge your own timeline."

The Open Storehouse Forge is designed for **makers, architects, tinkerers, and sovereign individuals** who want version control without depending on GitHub, GitLab, or any central service.

## How to Use

1. **Open the Forge**  
   Just open `index.html` in any modern browser (Chrome, Firefox, Edge, etc.).

2. **Forge a New Blueprint**  
   Click **"🛠 Forge Blueprint Repository"** to create your first project.

3. **Craft & Iterate**  
   - Add/edit files in the component tree
   - Make changes in the editor
   - See live diffs
   - Commit your snapshots with meaningful messages

4. **Branch & Experiment**  
   Fork new tracks for alternative designs or experiments.

5. **Synchronize**  
   Simulate mesh network pulls/pushes with other peers.

6. **Backup**  
   Export your entire storehouse as a JSON ledger anytime.

## Tech

- Pure HTML + CSS + Vanilla JavaScript (single file)
- LocalStorage persistence
- In-memory Git-style data model (commits, branches, diffs)
- Responsive dark theme modeled after modern developer tools

## Project Status

**Early Sovereign Edition** — Fully functional prototype with core version control primitives.

Future ideas (open to contributions):
- Real IndexedDB persistence
- File upload / image support
- Export to actual Git repository
- P2P sync via WebRTC or IPFS
- Plugin / extension system for specialized blueprints

## License

MIT © 2026 Alex Fox

---

**Made for those who build their own tools.**
