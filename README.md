# Hello there, I'm [Andrew Weeden](https://www.linkedin.com/in/weeden-andrew/)

I'm a computer science student at UTEP and a software developer based in Texas. I build stateful backend tools and experiment in agentic systems. I'm especially interested in systems design, secure local persistence, testable architecture, and AI infrastructure.

## Featured project: [Auto Interner](https://github.com/WeedenAndrew/auto_Interner)

Auto Interner is a local-first internship discovery and résumé-tailoring pipeline designed for unattended operation on a Raspberry Pi. It combines deterministic screening, guarded network retrieval, structured model responses, durable local state, and reproducible document generation without automatically submitting applications.

### Architecture

- **Acquisition:** year-swappable SimplifyJobs Git snapshots with protected HTTP retrieval, redirect revalidation, response limits, and an isolated browser fallback
- **Decision pipeline:** deterministic location and keyword filters followed by a strict provider-neutral model boundary with an Anthropic adapter
- **Persistence:** single-writer state, atomic updates, deduplication, retry tracking, recovery behavior, and collision-safe company/role output paths
- **Documents:** controlled DOCX rewriting that preserves the source résumé structure and keeps private runtime data outside the repository
- **Operations:** hardened ARM64/x86_64 Docker deployment with non-root execution, read-only filesystems, health checks, bounded resources, rotated logs, and SSD-backed state
- **Verification:** 399 automated tests with 91.01% combined line and branch coverage, strict typing, formatting, linting, and offline container contracts

**Stack:** Python 3.12, Docker Compose, Selenium/Chromium, python-docx, GitHub Actions, Linux, and ARM64

> **Deployment status:** offline software validation is complete; Docker image execution and Raspberry Pi 4B browser, reboot-persistence, thermal, and 24-hour soak tests remain pending.

## Other project

### [Goblin Flip](https://github.com/WeedenAndrew/Goblin-Flip)

A Flutter fantasy coin-flip game with animated gameplay, persistent state, interruption-safe wagers, power-ups, and a security-focused commerce boundary.

## Languages and tools

<p align="left">
  <a href="https://www.python.org" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="Python" width="40" height="40"/></a>
  <a href="https://www.docker.com" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original.svg" alt="Docker" width="40" height="40"/></a>
  <a href="https://www.selenium.dev" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/selenium/selenium-original.svg" alt="Selenium" width="40" height="40"/></a>
  <a href="https://www.linux.org" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" alt="Linux" width="40" height="40"/></a>
  <a href="https://git-scm.com" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original.svg" alt="Git" width="40" height="40"/></a>
  <a href="https://github.com/features/actions" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/githubactions/githubactions-original.svg" alt="GitHub Actions" width="40" height="40"/></a>
  <a href="https://dart.dev" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/dart/dart-original.svg" alt="Dart" width="40" height="40"/></a>
  <a href="https://flutter.dev" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/flutter/flutter-original.svg" alt="Flutter" width="40" height="40"/></a>
  <a href="https://developer.android.com/studio" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/androidstudio/androidstudio-original.svg" alt="Android Studio" width="40" height="40"/></a>
  <a href="https://www.mysql.com" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="MySQL" width="40" height="40"/></a>
</p>

[![Most used languages](https://github-stats-extended.vercel.app/api/top-langs/?username=WeedenAndrew&theme=react&title_color=e94789&text_color=ffffff&border_color=e94789&hide_border=true&custom_title=Most%20Used%20Languages&v=20260806)](https://github.com/WeedenAndrew)

## Connect with me

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=plastic&logo=github)](https://github.com/WeedenAndrew)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-e94789?style=plastic&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/weeden-andrew)
[![Kaggle](https://img.shields.io/badge/Kaggle-e94789?style=plastic&logo=kaggle&logoColor=white)](https://www.kaggle.com/weedenandrew)
![Profile views](https://komarev.com/ghpvc/?username=WeedenAndrew&label=Profile%20views&color=e94789&style=flat)
