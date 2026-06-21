# ShiftIDE

**AI-native terminal for cloud architects, systems engineers, and SREs.**

ShiftIDE brings guided deployment playbooks, an AI assistant, and real shell execution together in one desktop app — with a hosted account console at [shiftide.web.app](https://shiftide.web.app).

![ShiftIDE Main](https://github.com/user-attachments/assets/270a926b-d01c-49eb-8b49-1743378becb7)

---

## Features

**Terminal**
- Cross-platform PTY — PowerShell on Windows; bash/zsh on macOS and Linux
- Multi-session tabs, split view (side-by-side or stacked), and file browser rail
- Adaptive command learning with ranked autocomplete
- Themed scrollbars, configurable fonts, opacity, blur, and accent colors

**ShiftAI**
- Streaming chat across 10 providers: Ollama, OpenAI, Anthropic, Groq, DeepSeek, Gemini, Grok, vLLM, llama.cpp, RunPod
- Terminal context — last command + recent output sent with each prompt (opt-in, never uploaded)
- Project context via `.shiftide/context.md`
- Entry points: icon rail ✦, footer **Ask ShiftAI**, or `Ctrl/Cmd+Shift+A`

**Deploy Architect**
- Multi-turn AI interview that clarifies stack, targets, and environments, then curates 8–20 terminal steps
- Quick-start chips for CI/CD, multi-env infra, GitHub publish, bare metal, and migrations
- Variable substitution with `{{placeholders}}` and `{{var:dev}}` / `{{var:prod}}`

**87+ Deployment Playbooks**
- **Cloud** — Azure (VM, AKS, Container Apps), AWS (EC2, EKS, SAM), GCP (GKE, Cloud Run)
- **CI/CD** — GitHub Actions, Azure DevOps, GitLab CI, Jenkins
- **Network** — Cisco IOS-XE, Juniper, Huawei, FortiGate, Palo Alto PAN-OS, Terraform
- **Datacenter** — iDRAC, iLO, IPMI, NetBox, Proxmox, ESXi
- **Private cloud** — Red Hat (RHOSP, OCP, Ceph, Satellite, oVirt), Canonical (MicroCloud, Juju, MAAS)
- **Bare metal** — systemd, nginx, blue/green, rack-scale parallel SSH
- **Database** — Flyway, Liquibase, Prisma, Alembic

**Infrastructure Hub**
- Local device registry by role: compute, storage, network, security, control
- Real SSH sessions via native OpenSSH PTY (`user@host` with optional key and port)

**Notebook pane**
- Open `.ipynb` files as dedicated session tabs
- Run cell / Run all / Add cell / Save; Python via subprocess (use Jupyter Lab PTY for full kernel)

---

## Screenshots

| Commands | ShiftAI | Workflows |
|----------|---------|-----------|
| ![commands](https://github.com/user-attachments/assets/8f05915b-03d0-489e-bb58-434a8a669574) | ![ai](https://github.com/user-attachments/assets/2229e94b-d1c9-4e12-991e-aefec296fd12) | ![workflow](https://github.com/user-attachments/assets/b2bf2b3b-878f-43e7-82f3-cfedd49793dd) |

| Settings | Infra Hub | User Console |
|----------|-----------|--------------|
| ![settings](https://github.com/user-attachments/assets/edb9db41-a316-4cf8-bd19-4d06f50f2b53) | ![infra](https://github.com/user-attachments/assets/deeb7957-e66e-46ee-b877-b6e57c3d1edf) | ![console](https://github.com/user-attachments/assets/5bf669f7-5c90-4df1-ab2b-40aebfc3a200) |

---

## Download

Get the latest installer from [GitHub Releases](https://github.com/Scalovate/shiftIDE/releases/download/1.3.1/ShiftIDE.Setup.1.3.1.exe)


The web console is available at [shiftide.web.app](https://shiftide.web.app) — no install needed.


---

## Known limitations

- **Chrome local network** — Chrome may prompt *"Connect to devices on your local network"* when the desktop app connects; click **Allow** and keep ShiftIDE open
- **Notebook cells** — Python subprocess runner; use a Jupyter Lab PTY session for full kernel features

---

## Security & privacy

- API keys and terminal output stay on your device
- Cloud sync covers command text and workflow sequences only, and only when you opt in
- Firestore rules restrict all profile and user data to the signed-in account

---

## Links

- **Web app:** [shiftide.web.app](https://shiftide.web.app)
- **Docs:** [shiftide.web.app/docs](https://shiftide.web.app/docs/getting-started)

---

Product of © [Scalovate Systems Solutions](https://www.scalovate.com)



