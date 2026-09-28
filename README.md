### Jonathan Christensen

I'm a forward-deployed AI engineer. I build agents that do real IT operations work, and the
controls that make them safe to hand access to: **policy before every action, a record after,
a human on anything consequential, and evals that say whether it actually worked.**

By day I lead AI and automation delivery at an MSP in San Diego: service-desk tooling, an
investigation agent that drafts cited findings for technicians, production MCP servers, and the
Rewst workflows behind a [case study on 160+ hours a month recovered](https://rewst.io/success-stories/how-centrexit-recovered-160-hours-a-month-using-rewst).
I started on that service desk, which is why I build with the people who close the tickets.

**Franklin, my agentic home server**

At home I run the same ideas with fewer guardrails. Franklin is a Proxmox server (24 cores,
96 GB, Radeon GPUs) operated by an agent of the same name. I talk to it by voice or Discord,
and it has a real root account. It's where I find out how much autonomy an agent can carry and
which controls actually hold.

- **The machine becomes what I ask for.** "Game night" puts a Windows VM with GPU passthrough on
  the display; other scenes bring up a Linux desktop or an AI lab. An experience runtime plans
  against the live host, runs dry by default, requires confirmation for guarded actions, and
  writes a receipt for every apply.
- **It works on its own, within limits.** A persistent executive reconciles its queue every 15
  seconds, samples health every minute, and starts bounded background work under a daily budget.
  Results go to review with evidence. A worker saying "done" doesn't count as a passing check.
- **It asks before anything consequential.** Proposals reach my Discord DMs as approval requests
  tied to one exact revision. Purchases, deletions, firewall changes, and VM force-offs need an
  explicit yes.
- **Root goes through a broker.** Every request is logged with the caller, operation, target, and
  a command hash. It's documented as an authority boundary, not a sandbox, because that's what it is.
- **It ships what it builds** to a self-hosted [Openship](https://github.com/oblien/openship)
  instance, with a token scoped to its own projects.
- Local voice (Speaches, Kokoro), Qdrant memory, SearXNG search, and Prometheus/Grafana round it out.

The agent itself is private for now. [**Franklin Broadcast**](https://github.com/mejohnc-ft/Franklin-Broadcast)
is the piece that's public: Discord slash commands (`/s-start`, `/s-swap`, `/s-play`) drive a
persistent Chromium worker in a virtual desktop that joins the call and shares a tab. Franklin
orchestrates the stream but never is the streaming identity.

**Open source**

| Project | What it is |
|---|---|
| [**dotshot**](https://github.com/mejohnc-ft/dotshot) | Mac app: a screenshot, recording, or file goes to your agent's machine over SSH, and the remote path lands on your clipboard. Swift. [1.0 is out](https://github.com/mejohnc-ft/dotshot/releases/latest). |
| [**Cadre**](https://github.com/mejohnc-ft/cadre) | A self-hosted control plane for AI coworkers: each agent gets its own computer, CEL policy decides every action before it runs, and the agent never holds the credentials it uses. TypeScript, alpha. |
| [**Terminal Brain**](https://github.com/mejohnc-ft/Franklin-Brain) | Native macOS app that gives agents local-first memory over MCP from Obsidian, Apple Notes, and Drafts. Agent writes land in a reviewable inbox. Swift |
| [**Franklin Broadcast**](https://github.com/mejohnc-ft/Franklin-Broadcast) | Discord browser-streaming automation: Playwright worker, noVNC desktop, stream control API. |
| [**M365 Utilization Report**](https://github.com/mejohnc-ft/Rewst-M365-Utilization-Report) | Multi-tenant Microsoft 365 license, usage, and cost reporting as a signed Rewst workflow. |
| [**NotMyRouter**](https://github.com/mejohnc-ft/NotMyRouter) | Continuous probes that prove whether your ISP or your router is at fault. Python |
| [**MiniMix**](https://github.com/mejohnc-ft/MiniMix) | Per-app volume and mute in the menu bar, using Core Audio process taps. Swift |

**Also:** a 4-GPU AMD ROCm inference lab with a Python benchmark harness ([write-up](https://mejohnc.org/rocm-lab/)).
Talks: [FLOW 2026 Community Live](https://www.youtube.com/watch?v=EInZA_rqaYE) ·
[automation adoption webinar](https://rewst.io/resources/webinar/stop-waiting-start-now-scale-fast-centrexits-playbook).

[mejohnc.org](https://mejohnc.org) · [résumé](https://mejohnc.org/resume/) · mejohnwc@gmail.com
