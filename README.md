# Arash Abraham

### Backend Architect · Laravel & Python Engineer · Security-Oriented Builder

> **Systems designed to scale cleanly, remain maintainable, and stay secure under pressure.**

<table>
<tr>
<td width="60%" valign="center">

```text
Architecture.
Backend engineering.
Security.
Performance.
Infrastructure.
```

Scalable backend systems, secure APIs, and
infrastructure-aware software — with an emphasis
on clean architecture, predictable behavior,
and long-term maintainability.

</td>

<td width="40%" align="right">

<img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExYWpocXdieXRxY2liM3E2ZG95cmsyZmgxZ3JwdTlteXhmYnZpY2R0OSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/odQ5A4pdaDU8E/giphy.gif" width="320" />

</td>
</tr>
</table>

---

## Profile

```yaml
role:      Backend Architect
core:      Laravel / PHP  ·  Python  ·  TypeScript
low-level: C · C++ · Assembly  (when the job needs it)
focus:     architecture · APIs · security · performance · developer tooling
```

I work close to the system: how data is accessed, how queues behave under
pressure, where caching pays off, how a deployment fails at 3 a.m. Most of my
time goes into **Laravel** services and APIs, with **Python** and **Node.js /
TypeScript** around them — and C-family code when a problem needs to sit
closer to the metal.

Two things I care about more than feature count: **numbers that can be
reproduced** (benchmarks, parity checks, golden tests) and **decisions that can
be explained** — including the ones that say *stop*.

---

## Architecture

```text
╔════════════════════════════════════════════════════════════╗
║  INTERFACE      REST APIs · Webhooks · Auth & Sessions     ║
║  APPLICATION    Laravel · PHP · Python · TypeScript        ║
║  DATA           PostgreSQL · MySQL · MongoDB · Redis       ║
║  INFRASTRUCTURE Docker · Linux · Nginx · Observability     ║
╟────────────────────────────────────────────────────────────╢
║  SECURITY       cross-cutting concern in every layer       ║
╚════════════════════════════════════════════════════════════╝
```

The layers are designed together, not bolted on in sequence — and security is
not one of them, it runs through all of them.

---

## Selected Work

| Status | Project | What it is |
| :-- | :-- | :-- |
| `● SHIPPED` | **[A-Train](https://github.com/Arash-abraham/A-Train)** | Fast file & directory comparison for developers |
| `● IN DESIGN` | **[GitLens](https://github.com/Arash-abraham/GitLens)** | Change intelligence for the human + agent era |
| `● SHIPPED` | **[Oscar](https://github.com/Arash-abraham/Oscar)** | Modular payload-generation framework |
| `● SHIPPED` | **[FileStore](https://github.com/Arash-abraham/File-Store)** | Laravel marketplace for digital books |

### A-Train · *shipped*

**A high-performance file comparison tool for developers** — named after the
fastest member of The Seven, because a diff should arrive before you finish
blinking. It compares two files or whole directory trees with purpose-built
engines instead of forcing one general algorithm onto every input: **text**
(line diff with intra-line word refinement), **binary** (rolling-hash change
regions, hex display), **JSON** (semantic, key order irrelevant, JSONPath-style
reporting), **CSV** (row comparison keyed on a column), and **tree** (parallel
hashing, per-file diffs). Output as patch-compatible unified diff, colored
terminal view, side-by-side, standalone HTML, or machine-readable JSON — plus
watch mode, an interactive TUI, and Git integration that even speaks Git's
external-diff protocol.

The speed is measured, not claimed. A hash-based early exit handles identical
inputs, Myers O(ND) runs over pre-hashed integer line ids, linear-space
middle-snake refinement keeps memory flat, and a wall-clock guard bounds
pathological inputs. That gives **100 MB identical files in 0.34 s** and
**15.6× faster than `difflib`** on scattered 5 MB changes. Correctness gets the
same treatment: every edit script is verified to reconstruct the target exactly
(property-based round trips plus golden tests against GNU diffutils, applied
with GNU `patch`). Benchmarks, roadmap, and a per-bug development report all
live in the repository — including the results where GNU diff still wins.

`Python` · `Algorithms` · `Myers Diff` · `CLI` · `TUI` · `Benchmarks`

### GitLens · *in design*

**A deterministic, evidence-first change-intelligence layer for the human +
agent era.** The plan is to ingest a repository's full git history — provider
agnostic, GitHub first — and model *every change*: commits, files, lines,
authors, including AI agents and bots, each with an honest confidence tier. On
that fact model it computes reproducible answers to questions teams currently
cannot answer: which changes **survive**, where **rework** concentrates, what
**co-changes** with what, how far **blast radius** reaches, and how review
latency is trending — then turns versioned rules into **explainable risk
signals** instead of a "Risk Score = 87" black box. AI is allowed to *explain*
the evidence; it is never allowed to *measure* it.

What makes this project different from a feature list is how it was planned.
The master plan is a 1,700-line engineering document: a repository audit with
reproduced defects, a product thesis with cited market evidence, an explicit
**do-not-build register** (no GitHub clone, no git client, no vanity dashboard,
no developer ranking, no black-box scores), architecture decision records, a
data model and metric catalog, failure modes, and a six-month roadmap with a
**decision gate at the end of month two** — if the thesis fails validation, the
project stops on written criteria instead of sunk cost. **Nothing is
implemented yet**; the plan is the current deliverable, and it is deliberately
honest about the skeleton that exists today.

`TypeScript` · `PostgreSQL` · `Git Internals` · `System Design` · `Analytics Engineering`

### Oscar · *shipped*

**A modular payload-generation framework** — and the first project I ever put on
GitHub, back in 2020. It started as a simple Windows builder and became the
project that taught me **C, C++, and Assembly** by hand, back when an AI
assistant couldn't explain a segfault in seconds: documentation digging, broken
builds, and long nights in a terminal.

Python is only the interface layer. The payloads themselves are written in C,
C++, and Assembly, where performance, binary size, and control over system
resources actually matter — the completed Windows keylogger set ships in all
three, with Telegram delivery. The original builder still works end to end:
give it a name, a token and an icon, and it produces a compiled binary with no
manual commands. The current rewrite turns it into a true modular framework —
a payload registry, multiple payload types, Linux and macOS support, and custom
implementations in any language.

It exists strictly for **education, malware-analysis research, and authorized
security testing** on systems you own — and that disclaimer is the first thing
in the repository, as it should be.

`C` · `C++` · `Assembly` · `Windows Internals` · `Python Tooling` · `Security Research`

### FileStore · *shipped*

A **digital book marketplace** built with Laravel, covering the full lifecycle
of digital commerce: catalog and search, cart, discount codes, wallet with
partial payments, orders, and secure file delivery.

The interesting part was never the storefront — it's what sits behind it:
multiple authentication paths (password, email code, SMS code), **ZarinPal**
payment integration, download authorization that actually holds, support
tickets, moderated comments, and an admin dashboard with real sales analytics.

`Laravel` · `MySQL` · `Payments` · `Wallet` · `Secure Downloads` · `Admin Analytics`

---

## Process

```text
  UNDERSTAND ─▶ DESIGN ─▶ BUILD ─▶ HARDEN ─▶ OPTIMIZE ─▶ SHIP
   problem      system    code     security  evidence    release
```

Security is part of the architecture from the first commit, not a checklist at
the end. Performance decisions come from measurement, not assumption. And scale
is treated as a property of the whole system — data access, workload patterns,
queues, caching, bottlenecks, failure modes — not something you buy with more
servers.

---

## Collaboration

Developer tooling and CLI utilities · backend-heavy products · Laravel packages
and ecosystem tooling · security-oriented utilities · infrastructure and
monitoring systems · performance and scalability work · data-model and
analytics engine design · legacy backend modernization · open-source projects.

> **Real problems. Serious engineering. Useful software.**

---

## Contact

<p align="left">
  <a href="mailto:arashebi777@gmail.com">
    <img src="https://img.shields.io/badge/Email-Contact%20Me-EA4335?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
  <a href="https://t.me/Octawian">
    <img src="https://img.shields.io/badge/Telegram-Message%20Me-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" />
  </a>
  <a href="https://twitter.com/Arash_Aryans">
    <img src="https://img.shields.io/badge/X-Follow-000000?style=for-the-badge&logo=x&logoColor=white" />
  </a>
</p>

---

<div align="center">

> **"Don't make it harder than it needs to be — understand the path first."**

**Arash Abraham · Backend Architect**

</div>
