<div align="center">

<h1>Arash Abraham</h1>

<b>Backend Engineer</b>

[Email](mailto:arashebi777@gmail.com) &nbsp;·&nbsp; [Telegram](https://t.me/Octawian) &nbsp;·&nbsp; [X](https://x.com/Arash_Aryans) &nbsp;·&nbsp; [GitHub](https://github.com/Arash-abraham)

<br />

<img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExYWpocXdieXRxY2liM3E2ZG95cmsyZmgxZ3JwdTlteXhmYnZpY2R0OSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/odQ5A4pdaDU8E/giphy.gif" width="320" />

</div>

<br />

I build backend systems, APIs and data-driven applications, primarily with Laravel and Python. My focus is on maintainable software, reliable infrastructure and decisions that hold up under review.

Most of my work starts at the same place: understanding how data actually moves through a system before choosing how it should be stored, cached or queued. That usually decides more about how a service behaves in production than the framework does. I prefer boring, explicit solutions over clever ones, and I would rather ship a smaller system that is understood than a larger one that only works when nothing goes wrong.

I try to leave a trail behind each project: what is covered by tests, what has been measured, and what is still missing. Where a limitation is known, it is written down in the repository rather than left for someone to discover later.

I am currently working mostly on Laravel services and REST APIs, with Python around them for tooling and data collection. Beyond that, I am most useful on data models that need to stay correct over time, authentication and session boundaries, background jobs, and taking an existing backend that has grown awkward and making it predictable again.

<br />

## Technologies

| | |
|:--|:--|
| **Languages** | <img src="https://cdn.simpleicons.org/php/818CF8" width="20" height="20" alt="PHP" title="PHP" /> PHP &nbsp; <img src="https://cdn.simpleicons.org/python/818CF8" width="20" height="20" alt="Python" title="Python" /> Python &nbsp; <img src="https://cdn.simpleicons.org/typescript/818CF8" width="20" height="20" alt="TypeScript" title="TypeScript" /> TypeScript &nbsp; SQL &nbsp; <img src="https://cdn.simpleicons.org/c/818CF8" width="20" height="20" alt="C" title="C" /> C &nbsp; <img src="https://cdn.simpleicons.org/cplusplus/818CF8" width="20" height="20" alt="C++" title="C++" /> C++ |
| **Backend & Frameworks** | <img src="https://cdn.simpleicons.org/laravel/818CF8" width="20" height="20" alt="Laravel" title="Laravel" /> Laravel &nbsp; Sanctum &nbsp; <img src="https://cdn.simpleicons.org/vuedotjs/818CF8" width="20" height="20" alt="Vue 3" title="Vue 3" /> Vue 3 &nbsp; <img src="https://cdn.simpleicons.org/react/818CF8" width="20" height="20" alt="React" title="React" /> React &nbsp; <img src="https://cdn.simpleicons.org/pytest/818CF8" width="20" height="20" alt="pytest" title="pytest" /> pytest &nbsp; PHPUnit |
| **Data & Infrastructure** | <img src="https://cdn.simpleicons.org/mysql/818CF8" width="20" height="20" alt="MySQL" title="MySQL" /> MySQL &nbsp; <img src="https://cdn.simpleicons.org/mongodb/818CF8" width="20" height="20" alt="MongoDB" title="MongoDB" /> MongoDB &nbsp; <img src="https://cdn.simpleicons.org/docker/818CF8" width="20" height="20" alt="Docker" title="Docker" /> Docker &nbsp; <img src="https://cdn.simpleicons.org/nginx/818CF8" width="20" height="20" alt="Nginx" title="Nginx" /> Nginx &nbsp; <img src="https://cdn.simpleicons.org/githubactions/818CF8" width="20" height="20" alt="GitHub Actions" title="GitHub Actions" /> GitHub Actions |

<br />

## Projects

<table>
<tr>
<td width="50%" valign="top">

**[Watch Tower](https://github.com/AryaKhorasan/watch-tower)**

A bug-bounty scope monitoring platform that collects public datasets, tracks changes between snapshots and delivers Telegram or Discord notifications.

A Python collector normalises every program's in-scope and out-of-scope assets into one shared document shape, diffs each run against the previous snapshot and records one alert per change; a Laravel API exposes programs, changes, stats and health, and a Vue dashboard reads the same data.

The collector can run once or on a schedule, supports a dry-run mode and never lets a failed fetch kill the loop. Notifications are marked as sent per alert, so nothing is announced twice. The stack ships as Docker Compose services with health checks and CI.

`Python` `Laravel` `Vue` `MongoDB` `Docker`

<sub><b>Active development</b></sub>

</td>
<td width="50%" valign="top">

**[A-Train](https://github.com/Arash-abraham/A-Train)**

A multi-format diff tool supporting text, binary, JSON, CSV and directory comparisons, with Git integration and a terminal interface.

Rather than forcing one algorithm onto every input, A-Train selects a dedicated engine per format: semantic comparison for JSON where key order is irrelevant, row matching keyed on a chosen column for CSV, rolling-hash change regions for binaries, and parallel hashing for directory trees.

Output is available as patch-compatible unified diff, colored terminal view, side-by-side, standalone HTML or machine-readable JSON, with a watch mode, an interactive TUI and support for Git's external-diff protocol. Identical inputs exit early on a hash, and every edit script is checked to reconstruct the target exactly. Benchmarks and their methodology are published, including the cases where GNU diff is faster. Runs on the standard library alone; the TUI is optional.

`Python` `pytest` `GitHub Actions`

<sub><b>Early development · 0.5</b></sub>

</td>
</tr>
<tr>
<td width="50%" valign="top">

**[File-Store](https://github.com/Arash-abraham/File-Store)**

A digital bookstore built with Laravel and React, featuring payment integration, wallet management, authenticated downloads and content moderation.

The storefront is a React 19 + TypeScript SPA backed by a Laravel 12 API with Sanctum session cookies, covering catalog and search, cart and coupons, orders and support tickets.

Payment runs through Zarinpal, with a wallet that covers partial payments; balance changes are applied inside locked transactions, and wallet top-ups become payable only after verification. Purchased files never have public URLs, and download authorization is checked per user. User content stays hidden until it is moderated, authentication routes are rate-limited, and analytics stores a daily salted hash rather than IP addresses. Deployment steps and known limitations are documented.

`Laravel` `React` `MySQL`

<sub><b>Functional · documented limitations</b></sub>

</td>
<td width="50%" valign="top">

**[Oscar](https://github.com/Arash-abraham/Oscar)**

A Python CLI project for organizing multi-language components into a unified build workflow.

The interface is a Python menu that prepares source files and invokes a native compiler, with components grouped by operating system, component type and programming language. Implementations in C, C++ and Assembly sit alongside the tooling rather than being embedded in it.

Each component's status is tracked individually in the repository, because presence in the tree does not mean a workflow completes end to end. Linux support is not implemented in the current interface, and the modular plugin architecture is planned rather than finished.

`Python` `C` `C++`

<sub><b>Prototype · in development</b></sub>

<br />

<sub>For educational purposes, malware analysis and authorized security research only.</sub>

</td>
</tr>
</table>

<br />

<div align="center">
<sub>Backend Engineer · Laravel &amp; Python</sub>
</div>
