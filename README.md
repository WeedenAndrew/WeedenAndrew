# Hello there, I'm [Andrew Weeden](https://www.linkedin.com/in/weeden-andrew/)

I'm a computer science student at UTEP and a software developer based in Texas. I build stateful backend tools and experiment in agentic systems. I'm especially interested in systems design, secure local persistence, testable architecture, and AI infrastructure.

## Featured project: [Auto Interner](https://github.com/WeedenAndrew/auto_Interner)

One person's internship pipeline, built to run unattended on a Raspberry Pi. Deliberately single-user: one resume, one person, one industry. Every choice below follows from that, and generalising it for everyone else is a separate project.

### How it works

Every cycle fetches a snapshot of the public SimplifyJobs internship feed over Git, resolves it into one fixed commit, and reads a single JSON blob without checking out or executing anything. If that commit matches the last one, the cycle is skipped. Listings it has already decided on are skipped too.

Screening is tiered by what each step costs. The free tier reads fields the snapshot already carries, recruiting term, accepted degrees, role category and employer type, and answers "is this even the kind of job being looked for" before spending a fetch. Measured against the live Summer 2027 feed, the first three of those rules took 1,670 active listings to 339. What survives goes through deterministic location and keyword filters that reject only on hard disqualifiers, then a model boundary that is forced to return a fixed schema and is validated again locally. That last stage is the only paid one, so its verdicts are cached against a hash of the posting text rather than the listing, and re-screened weekly. Every tier passes on unknown, because a wasted model call costs cents and a false disqualification costs an internship. Individual posting URLs are fetched through a separate HTTP client with redirect revalidation, response size limits, and an isolated browser fallback for pages that need rendering.

Tailoring is the part that has to be trustworthy. A model rewrites your resume, then a validator rejects the result outright if it altered a numeric claim, introduced a technology absent from the source, escalated a stated proficiency, dropped a section, or reintroduced contact data. Truthfulness is enforced after the fact rather than requested in a prompt, and a rejected rewrite fails the run instead of shipping.

A second model then grades whatever the validator accepted, because a rewrite can satisfy every mechanical rule and still drift generic. The grader sits above the validator and can only reject what it already passed, so a model can never argue its way past the hard gate. Either rejection spends from one shared budget of two attempts, which bounds the cost of a listing at a fixed, knowable number of calls, and the retry is handed a category rather than the sentence it failed on.

Your contact details never reach the model at all. They are extracted into a local-only block before any request is built, and the validator refuses any rewrite that puts them back.

### Architecture

- **Acquisition:** swappable SimplifyJobs Git snapshots with protected HTTP retrieval, redirect revalidation, response limits, and an isolated browser fallback
- **Decision pipeline:** screening ordered by cost, free structured rules before any fetch, deterministic text filters after, then a strict provider-neutral model boundary with an Anthropic adapter whose verdicts are cached and re-screened weekly
- **Persistence:** single writer state, atomic updates, deduplication, retry tracking, recovery behavior, and collision-safe company/role output paths
- **Documents:** the assembler patches a copy of the base DOCX, preserves geometry and hyperlinks, scrubs identifying metadata, reopens the package to validate it, and publishes without overwriting an existing file
- **Operations:** hardened ARM64/x86_64 Docker deployment with non-root execution, read-only filesystems, health checks, bounded resources, rotated logs, and SSD-backed state
- **Verification:** 534 automated tests at 91% branch coverage, strict typing, formatting, linting, and offline container contracts

**Stack:** Python 3.12, Docker Compose, Selenium/Chromium, python-docx, GitHub Actions, Linux, ARM64

Automatic submission is deliberately out of scope. It breaks the terms of service of most application portals, and autosubmitted applications get flagged as spam. The expensive work is finding, screening, and tailoring, and that is what this automates.

> **Deployment status:** offline software validation is complete. Docker image execution and Raspberry Pi 4B browser, reboot persistence, thermal, and 24-hour soak tests remain pending.

## Other projects

### [Curat0r](https://github.com/WeedenAndrew/Curat0r)

Auto Interner generalised, for anyone rather than one person. Point it at your GitHub, upload a LinkedIn export, paste a posting. It assembles a corpus of your real work, you confirm what is true, and it selects the right subset per application under a one-page budget. It never authors a sentence about you, so it cannot invent one, and requirements nothing in your corpus supports are named in a gap report instead of quietly filled. Choosing what to show is the maximum coverage problem, so the greedy rule lands within (1 - 1/e) of optimal and every selected line records which requirement justified it. 1,545 lines, 101 tests, no runtime dependencies.

### [Goblin Flip](https://github.com/WeedenAndrew/Goblin-Flip)

A Flutter fantasy coinflip game. Animated tosses with custom art and sound, wagers that survive the app being interrupted, and three charms that bend a flip. Local saves are authenticated with rollback and replay protection, and the interface carries screen-reader labels and larger-text layouts. 10,692 lines behind gameplay, persistence, security, accessibility and release-configuration test suites.

## Languages and tools

<p align="left">
  <a href="https://www.python.org" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="Python" width="40" height="40"/></a>
  <a href="https://www.java.com" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="Java" width="40" height="40"/></a>
  <a href="https://dart.dev" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/dart/dart-original.svg" alt="Dart" width="40" height="40"/></a>
  <a href="https://www.rust-lang.org" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/rust/rust-original.svg" alt="Rust" width="40" height="40"/></a>
  <a href="https://www.r-project.org" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/r/r-original.svg" alt="R" width="40" height="40"/></a>
  <a href="https://www.typescriptlang.org" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" alt="TypeScript" width="40" height="40"/></a>
  <a href="https://fastapi.tiangolo.com" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/fastapi/fastapi-original.svg" alt="FastAPI" width="40" height="40"/></a>
  <a href="https://flutter.dev" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/flutter/flutter-original.svg" alt="Flutter" width="40" height="40"/></a>
  <a href="https://www.docker.com" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original.svg" alt="Docker" width="40" height="40"/></a>
  <a href="https://git-scm.com" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original.svg" alt="Git" width="40" height="40"/></a>
  <a href="https://github.com/features/actions" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/githubactions/githubactions-original.svg" alt="GitHub Actions" width="40" height="40"/></a>
  <a href="https://www.postgresql.org" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original.svg" alt="PostgreSQL" width="40" height="40"/></a>
</p>

[![Most used languages](https://github-stats-extended.vercel.app/api/top-langs/?username=WeedenAndrew&theme=react&title_color=e94789&text_color=ffffff&border_color=e94789&hide_border=true&custom_title=Most%20Used%20Languages&v=20260806)](https://github.com/WeedenAndrew)

## Connect with me

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=plastic&logo=github)](https://github.com/WeedenAndrew)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-e94789?style=plastic&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/weeden-andrew)
[![Kaggle](https://img.shields.io/badge/Kaggle-e94789?style=plastic&logo=kaggle&logoColor=white)](https://www.kaggle.com/weedenandrew)
