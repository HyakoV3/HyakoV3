# Eduardo Garcia

**English** · [Português](README.pt-BR.md)

**Software engineer · BI architect · operations.** Two decades of shipping Java and Python, turning data into decisions, and running the systems it all lives on — including a small self-hosted fleet I treat as an engineering constraint, not an excuse.

Most of my work lives in private repositories. The contribution graph shows the volume; this page is what's behind it.

---

## What I build

**Java is where most of my code lives.** Spring Boot services in a hexagonal architecture (ports & adapters), backed by PostgreSQL: JPA, versioned schema migrations with Flyway, Spring Security with an external identity provider, Redis for caching, Actuator for health and metrics. Each one ships as a full application — Java API, Vue/TypeScript frontend, nginx, all defined in Compose and deployed to a self-hosted control plane behind my own DNS.

**Go for the parts that need throughput** — long-running workers and integration services where a JVM per process would be the wrong trade.

**Media automation pipeline** — ~18k lines of Bash and Python around ffmpeg: loudness normalization, subtitle generation and cleanup through LLM calls, and an audit trail of every model invocation in SQLite, so cost and quality are measurable instead of vibes.

## Data & BI

**Two decades on the data side of the public sector**, where the volumes are large and the questions are political: ETL pipelines in Pentaho, dimensional models over PostgreSQL and Oracle, dashboards in Power BI for the business and in Grafana for operations, Python automation gluing it together.

The part I'm proudest of is unglamorous: a **versioned service-desk analytics layer** — Grafana dashboards and a SQL library for management indicators (ticket volumes by department, incidents by group, SLA compliance) kept in git like any other code, so a number on a slide can be traced back to the query that produced it.

It shows up in everything I write: every application above has a reporting and aggregation layer, because a system that can't explain itself in numbers isn't finished.

## What I actually run

A six-host fleet (home + cloud), hosts named after a Norse pantheon because infrastructure you can't name is infrastructure you can't talk about at 3 a.m.

- **~60 containerized services across 26 Compose stacks** — layered networks, only the reverse proxy exposed to the internet, secrets never committed.
- **Three reverse proxies in production** (Traefik, Caddy, and a PaaS-managed Traefik), because the right ingress depends on who has to operate it, not on what's trendy.
- **Authoritative DNS I own end to end**, plus firewall, fail2ban, and per-host recovery docs for the state that Compose files can't capture.
- **Full-fleet ARM64 → x86_64 migration**, planned in phases and executed without losing a service — the old nodes were deleted only after the new ones proved themselves.

---

## By the numbers

![Metrics](github-metrics.svg)

<sub>Generated daily. Includes private repositories in aggregate — counts and languages only, never names.</sub>

---

## Toolbox

**Languages** — Java · Go · Python · TypeScript/Vue · Bash · SQL / PL/SQL

**Data & BI** — PostgreSQL · Oracle · Power BI · Pentaho Data Integration · Grafana · Prometheus

**Infrastructure** — Docker Compose · Traefik · Caddy · Linux · authoritative DNS

**Media** — ffmpeg · SQLite · Redis

<sub>Certified: Grafana Labs (Grafana, Loki, Prometheus) · Power BI · advanced ETL with PDI · Python for SysAdmins.</sub>

---

## How I work

- **If it isn't measured, it's an opinion.** Dashboards for the business, dashboards for the servers, an audit table for the LLM calls — same instinct, three domains.
- **If it isn't in version control and a recovery doc, it doesn't exist.** Every host has a written path back from zero.
- **Boring beats clever.** Six hosts don't need Kubernetes; they need Compose files someone can read in a hurry.
- **Migrations are phased, reversible, and documented** — including the decisions I reversed, and why.
- **I kill things on purpose.** Services that stopped earning their keep get removed and written down as a decision, not left running "just in case."
- **Portuguese and English**, terminal-first, `vim` only.

---

<sub>Repositories here are private by design — client, public-sector and infrastructure work. Happy to walk through architecture, trade-offs, and failure modes in a conversation.</sub>

📫 **Contact:** edicgarcia@outlook.com
