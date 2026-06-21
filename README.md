# ShiftIDE Release Notes

Intelligent cross-platform terminal by **Scalovate Systems Solutions**  
Web console: [shiftide.web.app](https://shiftide.web.app) · Company: [scalovate.com](https://www.scalovate.com)

---

## v1.3.1 — June 2026

### File browser rail

- **Folder icon opens picker** — clicking 📁 in the side rail opens the OS folder dialog; the chosen folder appears in the file browser pane and syncs terminal cwd

---

## v1.3.0 — June 2026

### Production readiness release

**Desktop**
- File browser cwd uses in-shell `cd` (no longer kills running processes)
- Pending commands retry when terminal finishes loading
- Shell exit / spawn failure reflected in footer connection status
- Deploy Architect goal race fixed
- Unix file browser parent navigation fixed
- SSH sessions skip local file-browser cwd sync
- Auth handoff requires session nonce (blocks stray local POSTs)
- API keys encrypted via OS safeStorage when available
- `autoLearn` setting honored; atomic JSON writes with backup
- Intent cloud sync opt-in (`syncIntentsEnabled`)
- Infra Hub opens Deploy Architect tab
- Footer prioritizes active workflow step command
- React error boundary + main-process crash logging

**Web**
- Terms of Business and Privacy Policy pages
- Download links to GitHub releases
- Docs accuracy (87+ playbooks, shortcuts, guest mode, variables)
- 404 page, cookie notice, security headers
- Google re-auth before account deletion
- Handoff nonce support

**CI**
- GitHub Actions: test, typecheck, web build

---

## v1.2.7 — June 2026

### Autocomplete fix

- **No more duplicated prefix** — selecting a suggestion (e.g. `npm run dev` after typing `npm`) replaces the current line instead of appending
- Popup selection **prefills** the command; press Enter to run

---

## v1.2.6 — June 2026

### File browser cwd fix

- **Fixed broken directory sync** — relaunching the shell no longer orphans the PTY (stale `onExit` handler was unregistering the new session)
- **Fallback cd** — if relaunch fails, falls back to in-shell directory change so folder pick always works
- **Navigate up** — parent folder in file browser now syncs terminal cwd

---

## v1.2.5 — June 2026

### UX polish

- **Themed scrollbars** — sidebar, panels, and terminal scroll areas match dark/light ShiftIDE theme (violet hover accent)
- **Silent folder sync** — file browser changes working directory by relaunching the shell in that folder; no `cd` / `Set-Location` line appears in the terminal and nothing is recorded as a executed command

---

## v1.2.4 — June 2026

### File browser → terminal working directory

- **Fixed cwd sync** — selecting a folder in the file browser now runs `cd` / `Set-Location` in the active shell (was UI-only before)
- **Spawn with cwd** — new terminal sessions start in the session’s configured directory
- **Cross-shell** — PowerShell, cmd, bash, zsh, and SSH sessions each get the correct change-directory command

---

## v1.2.3 — June 2026

### Terminal split view

- **Fixed split layout** — side-by-side and stacked panes render in a real grid (was broken due to absolute positioning)
- **Split with one tab** — automatically opens a second session when only one terminal exists
- **Clearer footer controls** — Split / Unsplit and Side by side / Stacked (replaces confusing unicode labels)
- **Split lifecycle** — closes cleanly when a split pane is closed or when switching to a third tab

---

## v1.2.2 — June 2026

Deploy Architect UX fixes, network/datacenter playbooks, and web documentation.

### Deploy Architect

- **Fixed interview flow** — collected answers now sent on every turn; no repeated questions
- **Send / Generate UX** — interview completes after up to 4 questions; Send disables, Generate enables
- **Robust JSON parsing** — handles truncated LLM output; 8192 tokens for playbook generation

### Network & datacenter

- **12 new playbooks** — Juniper, Huawei, FortiGate, iDRAC, iLO, IPMI, NetBox, Proxmox, ESXi
- **Infrastructure Hub presets** — grouped Network, Datacenter, and Private cloud device templates
- **Expanded command library** — Cisco/Juniper/Huawei Ansible, PAN-OS/FortiGate API, ipmitool, racadm

### Web

- **Documentation** — [shiftide.web.app/docs](https://shiftide.web.app/docs/getting-started) with 11 guides (terminal, ShiftAI, workflows, Deploy Architect, Infra Hub, network/datacenter, shortcuts)

---

## v1.2.1 — June 2026

Deployment workflow library, ShiftAI Deploy Architect, Infrastructure Hub, and private cloud playbooks.

### Infrastructure Hub & private cloud

- **Infrastructure Hub** (icon rail ⬡) — local device registry by role (compute, storage, network, security, control); quick SSH connect to any host
- **Real SSH sessions** — native OpenSSH PTY to `user@host` with optional key and port
- **13 private cloud playbooks** — Red Hat (RHOSP, OCP, Ceph, Satellite, oVirt), Canonical (MicroCloud, Juju, MAAS, Landscape), cross-stack Ansible/FreeIPA/NetApp
- **Deploy Architect** quick-starts for Red Hat and Canonical private cloud stacks
- **Web:** expanded marketing site including [Private cloud](https://shiftide.web.app/private-cloud) page

### Deployment playbook library (75+ playbooks)

- **Cloud** — Azure (VM, AKS, Container Apps), AWS (EC2, EKS, SAM), GCP (GKE, Cloud Run)
- **Infra** — Canonical MicroCloud, multi-server SSH/Ansible, k3s HA clusters
- **Network** — Cisco IOS-XE, Palo Alto PAN-OS API, Terraform network IaC
- **CI/CD** — GitHub Actions, Azure DevOps, GitLab CI, Jenkins pipelines with dev/test/prod stages
- **GitHub** — auth, create repo, push, releases, Pages, Actions secrets
- **Bare metal** — systemd deploy, nginx, blue/green, rack-scale parallel SSH
- **Config** — per-env `.env`, Ansible vars, Vault/Consul, nginx/IIS
- **Database** — Flyway, Liquibase, Prisma, Alembic, safe prod migration path

### ShiftAI Deploy Architect

- **Multi-turn interview** in the workflow wizard — clarifies dev/test/prod, stack, targets, then curates 8–20 terminal steps
- **Quick-start chips** — CI/CD, multi-env infra, GitHub publish, bare metal, migrations
- **Variable substitution** — `{{placeholders}}` and `{{var:dev}}` / `{{var:prod}}` resolved before each step runs
- **Category browse** — filter playbooks by Cloud, CI/CD, GitHub, Bare metal, Config, Database, and more

---

## v1.1.0 — June 2026

Production completion: Ask ShiftAI streaming, mockup shell, cloud wiring, notebook pane.

### Ask ShiftAI

- **Streaming chat** across all 10 providers (Ollama, OpenAI, Anthropic, Groq, DeepSeek, Gemini, Grok, vLLM, llama.cpp, RunPod)
- **Terminal context** — last command + recent output (opt-in, default on, never uploaded)
- **Project context** — `.shiftide/context.md` prepended to every prompt
- Entry points: icon rail ✦, footer **Ask ShiftAI**, `Ctrl/Cmd+Shift+A`

### UI shell (mockup)

- **Icon rail** — sessions, file browser, command search, AI assistant, settings
- **File browser** — browse home directory, open folder as terminal cwd, double-click `.ipynb`
- **Split terminals** — horizontal/vertical split from status bar
- **Git branch** — current branch shown in footer for active session cwd

### Cloud & workflows

- **Upload learned commands** — syncs to `users/{uid}/commands` when enabled and signed in
- **Community workflows** — anonymized step fingerprints to `community_commands` when opted in
- **Search merge** — cloud + community commands merged into autocomplete ranking
- **LLM workflow wizard** — ShiftAI proposes 3–5 steps when local match fails

### Notebook pane

- Open `.ipynb` from file browser as a dedicated session tab
- Run cell / Run all / Add cell / Save
- Python execution via subprocess (full Jupyter Lab still available as PTY session type)

### v1.1.0 patch — production gap closure

- **Keyboard shortcuts** — configurable in Settings; `Mod+K`, `Mod+Shift+A`, split toggles
- **Ranked autocomplete** — exact → learned → cloud → sequences → AI (signed in)
- **Community read gated** — community commands merge only when contribute toggle is on
- **File browser sandbox** — home-only by default; Open folder… grants extra roots
- **Workflow wizard** — auto LLM suggest when Find returns no matches
- **Vitest** — SSE parser, ranking, and path sandbox unit tests
- Version **1.1.0** installer; see [TESTING.md](TESTING.md) for manual matrix

### Developer

```bash
npm run typecheck
npm run dist:win
```

---

## v1.0.0 — June 2026

First public release of ShiftIDE desktop and the hosted account console.

### Desktop app (Windows)

- **Cross-platform terminal** — PowerShell on Windows; bash/zsh on macOS and Linux via `node-pty` and xterm.js
- **Multi-session UI** — title tabs, sidebar, command library, guided workflows, settings and info drawers
- **Local intelligence** — command library with adaptive learning, workflow suggestions, and autocomplete overlay
- **Appearance** — fonts, opacity, blur, accent colors, optional display-name suffix
- **Google sign-in** — Menu → Sign in opens the system browser; session syncs back to the desktop app via localhost handoff (no Cloud Functions required)
- **Windows installer** — build with `npm run dist:win` → `dist-app/ShiftIDE Setup 1.0.0.exe`
- **Custom protocol** — `shiftide://auth` fallback when loopback handoff is blocked by the browser

### Web console

- **Hosted at** [shiftide.web.app](https://shiftide.web.app) on Firebase Hosting (Spark / free tier)
- **Account console** — profile, saved workflows, activity, privacy and data deletion
- **Register vs sign in** — separate flows; sign-in requires an existing Firestore profile
- **Desktop connect** — after Google auth, the web app POSTs OAuth tokens to the running desktop app on `127.0.0.1:47834`

### Authentication

- **Firebase Auth** — Google OAuth and email/password
- **Firestore profiles** — user data under `users/{uid}` with security rules
- **Spark-only stack** — Auth, Firestore, and Hosting; no Blaze plan or Cloud Functions
- **Desktop handoff** — Google `idToken` + `accessToken` delivered over loopback; renderer signs in with `signInWithCredential`
- **OAuth setup helper** — `npm run oauth:setup` opens Google Cloud Console to add redirect URI `https://shiftide.web.app/__/auth/handler`

### Firebase & deploy

| Script | Purpose |
|--------|---------|
| `npm run web:deploy` | Build web app and deploy Hosting only |
| `npm run firebase:deploy` | Build web app and deploy Hosting + Firestore rules |
| `npm run oauth:setup` | Open Google OAuth credential setup (one-time) |

Cloud Functions and related deploy scripts were removed to prevent accidental Blaze deployments.

### Developer setup

```bash
npm install
npm run dev          # Desktop (Electron)
npm run web:dev      # Web console (Vite)
npm run dist:win     # Windows installer
```

### Known limitations

- **Chrome local network** — when connecting the desktop app, Chrome may prompt *“Connect to devices on your local network”*; click **Allow** and keep ShiftIDE open
- **Google OAuth** — redirect URI and JavaScript origin for `shiftide.web.app` must be registered in Google Cloud Console (see `npm run oauth:setup`)
- **JSON local storage** — settings and commands use JSON under Electron `userData` (not SQLite)
- **Notebook cells** — Python subprocess runner for v1; use Jupyter Lab PTY session for full kernel features

### Security & privacy

- API keys and terminal output stay on the device
- Optional cloud sync covers command text and workflow sequences only when the user opts in
- Firestore rules restrict profile and user data to the signed-in account

---

## Upgrade notes

Install the latest `ShiftIDE Setup *.exe` or run from source with `npm run dev`.

For web, production is updated via `npm run web:deploy`. Desktop users need a new installer after main-process or renderer changes.

---

## Links

- **Repository:** [github.com/rulhaq/shiftIDE](https://github.com/rulhaq/shiftIDE)
- **Web app:** [shiftide.web.app](https://shiftide.web.app)
<img width="1912" height="1102" alt="shiftide-user-console" src="https://github.com/user-attachments/assets/e1ef09dd-5390-4840-8e7d-98477bf17627" />
<img width="1912" height="1137" alt="shiftide-infra" src="https://github.com/user-attachments/assets/002053df-d760-4600-902a-454bf0aee36f" />
<img width="1919" height="1135" alt="shiftide-settings" src="https://github.com/user-attachments/assets/fb486d09-6586-451a-a282-f398c6bde7eb" />
<img width="1917" height="1132" alt="shiftide-ai" src="https://github.com/user-attachments/assets/d1d17bc1-2bea-4a65-b54d-4250adf4773d" />
<img width="1911" height="1132" alt="shiftide-commands" src="https://github.com/user-attachments/assets/9f1af3a5-78f4-4195-8d6c-696e4c388c19" />
<img width="1917" height="1135" alt="shiftide-workflow" src="https://github.com/user-attachments/assets/7f634340-0d71-417f-89b6-f948b04289a2" />
<img width="1915" height="1132" alt="shiftide-Main" src="https://github.com/user-attachments/assets/f5097ba9-b89d-4b01-8cb0-b5e4a185e843" />

