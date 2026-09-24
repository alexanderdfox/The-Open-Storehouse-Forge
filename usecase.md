# Use Cases — Open Storehouse Forge vs GitHub

Open Storehouse Forge is a **browser-native** blueprint and Git workspace. It borrows GitHub’s look and many Git workflows, but runs entirely on the client (with optional real Git over HTTPS).

Use this document to decide when the Forge is enough, when GitHub is better, and how they complement each other.

---

## Comparison table

| Capability | Open Storehouse Forge | GitHub |
|------------|----------------------|--------|
| **Where it runs** | Browser only (static HTML + JS) | Cloud SaaS + git clients |
| **Account required** | No | Yes (for private / collab) |
| **Local offline editing** | Yes (localStorage + in-browser FS) | Partial (needs clone + desktop/CLI) |
| **UI familiarity** | GitHub-like dark UI (repos, Code / Commits tabs, file table, branch control) | Full product UI |
| **Multi-file repos** | Yes (nested paths, dirty markers, search) | Yes |
| **Branches** | Yes (fork, switch, delete, merge with conflict markers) | Yes (full model) |
| **Commits** | Forge ledger + optional real Git commits | Full Git history |
| **Diff view** | Line diff vs HEAD (LCS-based) | Full diff / PR review UI |
| **Clone remote Git** | Yes (HTTPS via CORS proxy) | Native |
| **Push / Pull** | Yes (token for private & push) | Native |
| **Pull requests / Issues** | No | Yes |
| **CI / Actions** | No | Yes |
| **Code review** | Manual (inspect / restore commits) | PR reviews, suggestions, checks |
| **Collaborators & permissions** | Single-browser / shared export | Fine-grained org & team access |
| **Large / binary repos** | Limited (text-oriented; browser memory) | Scales with Git LFS, etc. |
| **Search** | Filename + content in active repo | Global code search (advanced on GH) |
| **Markdown preview** | Built-in for `.md` | README + wiki + docs |
| **Export / backup** | JSON ledger + per-repo file export | Always remote; also archive download |
| **Hosting the app itself** | Any static host (e.g. GitHub Pages) | N/A (you use github.com) |
| **Cost** | Free (your browser + optional public CORS proxy) | Free tier + paid plans |
| **Trust / data location** | Data stays in *your* browser unless you push | Data on GitHub’s servers |

---

## When to use Open Storehouse Forge

| Use case | Why the Forge fits |
|----------|-------------------|
| **Sketch architecture offline** | No signup; open the HTML file and start writing configs, READMEs, notes. |
| **Teach Git concepts** | Visual branches, commits, merge conflicts, and dirty files without installing Git. |
| **Personal blueprint vault** | Oven plans, lab notes, infra sketches — versioned locally, exportable as JSON. |
| **Quick edit of a small public repo** | Clone → edit → commit → push (with PAT) from a phone or locked-down machine. |
| **Demo / portfolio tool** | Host the Forge on GitHub Pages; visitors try a Git-like UI without accounts. |
| **Air-gapped or low-trust networks** | Work in-browser; only open the network when you choose to clone or push. |
| **Single-player version control** | Full enough history for one author without org overhead. |

---

## When to use GitHub

| Use case | Why GitHub fits |
|----------|-----------------|
| **Team collaboration** | PRs, reviews, protected branches, CODEOWNERS. |
| **Open-source community** | Issues, Discussions, Stars, discoverability. |
| **CI/CD and automation** | Actions, environments, deployments. |
| **Large codebases** | Performance, LFS, partial clone, desktop + CLI. |
| **Compliance & audit** | SSO, audit log, enterprise policies. |
| **Package / release distribution** | Releases, Packages, Pages as product surface. |

---

## Combined workflow (recommended)

Many people use **both**:

1. **Forge** — draft and iterate on a blueprint (or a small repo) in the browser.
2. **Init Git** or **Clone** — attach a real remote when the idea stabilizes.
3. **Commit + Push** — publish to GitHub for backup, sharing, or CI.
4. **GitHub** — open PRs, run Actions, invite reviewers.
5. **Pull** back into the Forge when you want to continue lightweight editing.

```
  ┌─────────────┐     clone / push      ┌─────────────┐
  │   Forge     │ ←──────────────────→  │   GitHub    │
  │  (browser)  │     HTTPS + PAT       │   (remote)  │
  └─────────────┘                       └─────────────┘
        │                                      │
        │ localStorage + LightningFS           │ issues, PRs, Actions
        ▼                                      ▼
   offline drafts                         collaboration & CI
```

---

## Feature mapping (mental model)

| You want to… | In the Forge | On GitHub |
|--------------|--------------|-----------|
| Create a project | **New repository** | New repository |
| Switch branch | Branch dropdown | Branch dropdown / `git checkout` |
| See files | **Code** tab file table | Code tab |
| See history | **Commits** tab | Commits / history |
| Save a snapshot | **Commit changes** | Commit |
| Experiment safely | **New branch** | New branch |
| Combine work | **Merge** (markers in files) | Merge PR or `git merge` |
| Sync remote | **Pull** / **Push** | Pull / Push |
| Back up everything | **Export ledger** | Always on remote (+ download ZIP) |

---

## Limitations to remember

- **CORS:** Browser Git uses a public proxy (`cors.isomorphic-git.org`) so GitHub HTTPS works from sites like GitHub Pages.
- **Not a full Git client:** No interactive rebase UI, submodules UI, or LFS workflow.
- **Single-user by default:** Sharing means export/import JSON or push to a real remote.
- **Storage:** Browser quotas apply; export ledgers for anything important.
- **Secrets:** Never commit tokens; use the PAT field only in the UI session.

---

## Summary

| Prefer Forge when… | Prefer GitHub when… |
|--------------------|---------------------|
| You want zero setup and instant editing | You need teams, PRs, and CI |
| Work is personal or exploratory | Work is shared or production-bound |
| You’re on a machine without Git installed | You already live in git + GitHub daily |
| You care about local-first / sovereign storage | You care about network effects and integrations |

**Open Storehouse Forge** is the workbench. **GitHub** is the warehouse and shipping dock. Use the workbench to build; use the warehouse to store, ship, and collaborate.
