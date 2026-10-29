# Photon OSINT Reconnaissance Lab

> **Educational lab notes by [PsychoMods](https://github.com/Psychomods666)**  
> Tool: [Photon by s0md3v](https://github.com/s0md3v/Photon) · Focus: website footprinting and reconnaissance

This repository documents a controlled, educational run of **Photon**, an open-source web-crawling and OSINT reconnaissance tool. The goal is to understand how a crawler discovers a website's internal links, external links, and other publicly exposed web resources.

## Contents

- [Overview](#overview)
- [Lab environment](#lab-environment)
- [Workflow](#workflow)
- [Screenshots](#screenshots)
- [Understanding the output](#understanding-the-output)
- [What I learned](#what-i-learned)
- [Safety and responsible use](#safety-and-responsible-use)
- [References](#references)

## Overview

Photon automates parts of website reconnaissance by crawling a supplied URL and collecting information exposed through the website. Depending on the selected options and the target's public content, results may include internal URLs, external links, JavaScript-related resources, files, and other crawl findings.

This is **documentation of a learning exercise**, not a claim that the target is vulnerable or compromised. A crawler's output is a starting point for manual review—not proof of a security issue.

## Lab environment

The screenshots show a Linux terminal session with:

- Python virtual environment: `venv`
- Python package installation from `requirements.txt`
- Photon command-line execution
- Output saved to a target-named results directory

The screenshots are included as supporting evidence. Identifying details in the output screenshot have been redacted for privacy before publication.

## Workflow

### 1. Obtain the project

Use the upstream repository and review its instructions before installing:

```bash
git clone https://github.com/s0md3v/Photon.git
cd Photon
```

If the directory already exists, do **not** clone over it. Enter the existing folder and review its contents first.

### 2. Create and activate a virtual environment

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Use the Python version supported by the upstream project and its dependencies. If installation fails, read the error and check the project's current documentation rather than forcing incompatible packages.

### 4. Run a crawl against an authorized target

The screenshots document this example command format:

```bash
python photon.py -u example.com
```

Replace `example.com` only with a domain you own or have explicit permission to assess. Review Photon’s current help and documentation for supported options, crawl depth, rate controls, and output behavior.

### 5. Review the generated results

Photon saves its findings in an output directory named for the target by default (unless a custom output directory is selected). In the recorded run, the terminal reported:

- **26 total requests**
- **4 seconds** total runtime
- **5 requests per second**
- **69 internal links** and **4 external links** reported in the displayed summary

These are the values shown in this particular terminal run; results will vary by website, network conditions, configuration, and tool version.

## Screenshots

### 1. Creating a local Linux user

![Linux user creation terminal](images/01-linux-user-setup.jpg)

This screenshot records a Linux `adduser` workflow. It is included as environment/setup context, not as a Photon feature.

### 2. Preparing and running Photon

![Photon setup and command-line run](images/02-photon-setup-and-run.jpg)

This screenshot shows an existing Photon directory, virtual-environment activation, dependency installation, and a command-line crawl.

### 3. Reviewing crawl results

![Photon crawl results and redacted external links](images/03-photon-results-redacted.jpg)

This screenshot shows the crawl summary and result-file review. External profile links and contact details have been redacted in this public version.

## Understanding the output

- **Internal links** generally refer to URLs on the same website discovered during crawling.
- **External links** are links from the target website to other domains.
- **JavaScript-related results** can help an analyst identify client-side resources worth reviewing.
- **Files and endpoints** may reveal publicly linked documents or application routes.

A discovered URL is not automatically sensitive, exploitable, or a vulnerability. Verify findings manually, record the source and timestamp, and avoid collecting or publishing unnecessary personal information.

## What I learned

- How to work inside a Python virtual environment.
- How to install a tool's Python dependencies.
- How to run a command-line web crawler against a specified URL.
- How to locate and inspect generated text output.
- Why crawl results require validation and careful handling before being shared.

## Safety and responsible use

- Test only on systems you own or have explicit written authorization to assess.
- Follow applicable laws, site terms, and the scope of any assessment.
- Use conservative crawl settings; aggressive crawling can burden services or trigger security controls.
- Do not use results to harass, profile, or expose private individuals.
- Never commit credentials, session cookies, API keys, private messages, personal phone numbers, or unredacted target data.
- Treat discovered secrets as sensitive: do not test or use them; notify the system owner through an appropriate channel.
- Keep reports factual and distinguish observed data from assumptions.

## References

- [Photon source repository](https://github.com/s0md3v/Photon)
- [Photon usage documentation](https://github.com/s0md3v/Photon/wiki/Usage)
- [PsychoMods GitHub profile](https://github.com/Psychomods666)

---

**Author:** PsychoMods  
**Purpose:** Cybersecurity education, authorized reconnaissance, and OSINT learning  
**Status:** Personal lab notes; not an official Photon project
