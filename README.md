# Eduardo Garcia

**English** · [Português](README.pt-BR.md)

**Infrastructure & backend engineer.** I run a small, self-hosted production fleet — and I treat "small" as an engineering constraint, not an excuse.

Most of my work lives in private repositories. The contribution graph shows the volume; this page is what's behind it.

<!-- METRICS: reativar assim que github-metrics.svg for gerado pelo workflow
---

## By the numbers

![Metrics](github-metrics.svg)

<sub>Generated daily. Includes private repositories in aggregate — counts and languages only, never names.</sub>
-->

---

## What I actually run

A six-host fleet (home + cloud), hosts named after a Norse pantheon because infrastructure you can't name is infrastructure you can't talk about at 3 a.m.

- **~60 containerized services across 26 Compose stacks** — layered networks, only the reverse proxy exposed to the internet, secrets never committed.
- **Three reverse proxies in production** (Traefik, Caddy, and a PaaS-managed Traefik), because the right ingress depends on who has to operate it, not on what's trendy.
- **Authoritative DNS I own end to end**, plus firewall, fail2ban, and per-host recovery docs for the state that Compose files can't capture.
- **Full-fleet ARM64 → x86_64 migration**, planned in phases and executed without losing a service — the old nodes were deleted only after the new ones proved themselves.

## What I build

**Media automation pipeline** — ~18k lines of Bash and Python around ffmpeg: loudness normalization, subtitle generation and cleanup through LLM calls, and an audit trail of every model invocation in SQLite, so cost and quality are measurable instead of vibes.

**Application work** — Go services, Java backends, Vue/TypeScript frontends, PostgreSQL. Containerized, deployed through a self-hosted control plane, behind my own DNS.

---

## Toolbox

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Java](https://img.shields.io/badge/Java-E76F00?style=flat-square&logo=openjdk&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Vue](https://img.shields.io/badge/Vue-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Traefik](https://img.shields.io/badge/Traefik-24A1C1?style=flat-square&logo=traefikproxy&logoColor=white)
![Caddy](https://img.shields.io/badge/Caddy-1F88C0?style=flat-square&logo=caddy&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-1A1A1A?style=flat-square&logo=linux&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![ffmpeg](https://img.shields.io/badge/ffmpeg-007808?style=flat-square&logo=ffmpeg&logoColor=white)
![Vim](https://img.shields.io/badge/Vim-019733?style=flat-square&logo=vim&logoColor=white)

---

## How I work

- **If it isn't in version control and a recovery doc, it doesn't exist.** Every host has a written path back from zero.
- **Boring beats clever.** Six hosts don't need Kubernetes; they need Compose files someone can read in a hurry.
- **Migrations are phased, reversible, and documented** — including the decisions I reversed, and why.
- **I kill things on purpose.** Services that stopped earning their keep get removed and written down as a decision, not left running "just in case."
- **Portuguese and English**, terminal-first, `vim` only.

---

<sub>Repositories here are private by design — client and infrastructure work. Happy to walk through architecture, trade-offs, and failure modes in a conversation.</sub>

📫 **Contact:** [LinkedIn](https://linkedin.com/in/edu-costa-garcia/) · edicgarcia@outlook.com
