<div align="center">

# 🔎 Photon OSINT Reconnaissance Lab

### Website Footprinting & Reconnaissance with Linux

![Photon](https://img.shields.io/badge/Photon-OSINT%20Tool-blue?style=for-the-badge&logo=github&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-Terminal-black?style=for-the-badge&logo=linux&logoColor=white)
![Cybersecurity](https://img.shields.io/badge/Cybersecurity-Learning-red?style=for-the-badge)
![OSINT](https://img.shields.io/badge/OSINT-Reconnaissance-orange?style=for-the-badge)
![PsychoMods](https://img.shields.io/badge/PsychoMods-Tech%20Lab-8AFF00?style=for-the-badge&logo=github&logoColor=black)

**A hands-on learning project documenting web crawling, link discovery, and responsible reconnaissance.**

[GitHub Profile](https://github.com/Psychomods666) · [Photon Repository](https://github.com/s0md3v/Photon)

</div>

---

## 🧭 Overview

This project documents the use of **Photon**, an open-source web crawler and OSINT reconnaissance tool, in a Linux terminal environment.

Photon can help discover internal links, external links, and other publicly reachable resources connected to a supplied website. The purpose of this lab is to understand the workflow, inspect the generated results, and learn how to document observations responsibly.

This is a learning exercise. The output shown here is not proof that a website is vulnerable or compromised.

```text
Environment Setup
       ↓
Dependency Installation
       ↓
Photon Execution
       ↓
Website Crawling
       ↓
Output File Review
       ↓
Result Interpretation
```

> ⚠️ **Ethical use:** Scan only websites and systems you own or have explicit authorization to assess.

---

## 🎯 Objectives

- Understand the purpose of Photon in website reconnaissance.
- Review a Python-based command-line tool workflow.
- Activate a Python virtual environment.
- Install project dependencies.
- Run Photon against an authorized target.
- Review generated output files.
- Understand internal links, external links, and crawl statistics.
- Document terminal evidence in a GitHub repository.
- Learn why automated results require careful interpretation.

---

## 🛠️ Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| 🐧 Linux | Command-line environment |
| 🔎 Photon | Web crawling and reconnaissance |
| 🐍 Python | Runtime for the tool |
| 📦 pip | Python dependency installation |
| 🧪 Virtual environment | Isolated Python packages |
| 📝 GitHub Markdown | Project documentation |

---

# 🧪 Practical Walkthrough

## 01 — Photon Project Directory

The screenshots show an existing local Photon project directory. When the repository already exists, enter that directory instead of cloning another copy over it.

### Clone the upstream repository (new installation only)

```bash
git clone https://github.com/s0md3v/Photon.git
cd Photon
```

If you already have the project, use:

```bash
cd ~/Photon
```

> 💡 The directory path may differ on your machine. Always check that you are inside the correct project folder before running commands.

---

## 02 — Activate the Python Virtual Environment

A virtual environment keeps the project's Python packages separate from system-wide packages.

### Command

```bash
source venv/bin/activate
```

When activated, the terminal prompt usually displays `(venv)`.

If the environment does not exist yet, create it first:

```bash
python3 -m venv venv
source venv/bin/activate
```

### Why this matters

- Keeps dependencies isolated.
- Helps avoid conflicts with other Python projects.
- Makes the environment easier to manage and reproduce.

---

## 03 — Install Dependencies

Photon's project dependencies are listed in `requirements.txt`.

### Command

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### Explanation

- `python -m pip` runs pip through the active Python interpreter.
- `install` installs the requested packages.
- `-r requirements.txt` reads the dependency list from the file.

If packages are already installed, pip may report that the requirements are already satisfied. Use a Python version supported by the current upstream project and its dependencies.

### 📸 Terminal Evidence

![Photon setup and command-line execution](images/02-photon-setup-and-run.jpg)

---

## 04 — Run Photon Against an Authorized Target

The recorded command uses the `-u` option to supply a target URL.

### Command format

```bash
python photon.py -u example.com
```

Replace `example.com` with a domain you own or are explicitly authorized to assess.

### What happens?

Photon crawls the supplied website and reports information it discovers. The results depend on the website, the tool's configuration, network conditions, and the version in use.

Review Photon’s current help and documentation for supported options:

- [Photon source repository](https://github.com/s0md3v/Photon)
- [Photon usage documentation](https://github.com/s0md3v/Photon/wiki/Usage)

---

## 05 — Review the Generated Results

In the recorded terminal run, Photon completed the crawl and reported the following summary.

<div align="center">

| 26 | 69 | 4 |
|:---:|:---:|:---:|
| **Total requests** | **Internal links** | **External links** |

| Runtime | Reported request rate |
|:---:|:---:|
| **4 seconds** | **5 requests/second** |

</div>

These are the values displayed in this particular run, not expected results for every target.

### 📸 Terminal Evidence

![Photon crawl summary and result review](images/03-photon-results-redacted.jpg)

The screenshot shows the crawl summary and the review of output files. Personal profile links and contact details have been redacted from the public copy.

---

## 06 — Inspect the Output Files

The recorded session lists an output directory containing:

```text
target-output/
├── external.txt
└── internal.txt
```

The exact directory name depends on the target and the tool's output settings.

### View the discovered internal links

```bash
cat internal.txt
```

### View the discovered external links

```bash
cat external.txt
```

Run these commands from the actual results directory. The filenames above reflect the files shown in the recorded session; output may differ between runs.

### Understanding the files

| Output | General meaning |
|---|---|
| `internal.txt` | Internal URLs discovered during the crawl |
| `external.txt` | Links to other domains discovered on the target website |

A discovered URL is not automatically sensitive or vulnerable. Check the context and verify any security-related observation manually.

---

# 📸 Screenshots Gallery

The screenshots below document the learning workflow. The first screenshot is Linux account setup context; it is not a Photon feature.

<details>
<summary><strong>📷 Screenshot 1 — Linux User Setup</strong></summary>

![Linux user creation terminal](images/01-linux-user-setup.jpg)

*Terminal evidence showing a Linux `adduser` workflow.*

</details>

<details>
<summary><strong>📷 Screenshot 2 — Photon Setup and Execution</strong></summary>

![Photon setup and execution](images/02-photon-setup-and-run.jpg)

*Existing Photon directory, virtual environment activation, dependency checks, and command execution.*

</details>

<details>
<summary><strong>📷 Screenshot 3 — Crawl Results</strong></summary>

![Photon results with identifying details redacted](images/03-photon-results-redacted.jpg)

*Summary statistics and review of the generated output. Identifying details have been redacted for public sharing.*

</details>

---

# 📊 Understanding Photon Output

Photon may help identify:

- Internal links on a website.
- External links pointing to other domains.
- Publicly referenced web resources.
- JavaScript-related resources, depending on crawl behavior and options.
- Other crawl results supported by the tool and its configuration.

### Important limitation

Automated crawling is only one part of reconnaissance. It does not independently prove that a website has a security vulnerability, and the absence of findings does not prove that a website is secure.

Use the output as a starting point for authorized, manual analysis.

---

# 🔬 Reconnaissance Workflow

```text
        Authorized Target
               │
               ▼
        Photon Crawler
               │
               ▼
      Discovered Web Links
               │
               ▼
       Generated Text Files
               │
               ▼
       Manual Result Review
               │
               ▼
      Document Observations
               │
               ▼
       Responsible Reporting
```

---

# 🧠 Key Learning

Through this practical, I learned how to:

- Navigate a local tool repository.
- Activate a Python virtual environment.
- Install or verify Python dependencies.
- Run a web crawler from the terminal.
- Read internal and external link output.
- Interpret request counts and runtime statistics.
- Redact identifying information before publishing evidence.
- Distinguish crawler output from confirmed security findings.

---

# 🛡️ Scope & Authorization

| Activity | Environment | Authorization |
|---|---|---|
| Tool installation | Local Linux system | Own system |
| Dependency setup | Local Python environment | Own system |
| Website crawling | Authorized website or lab | Permission required |
| Result analysis | Generated local output | Handle data responsibly |
| Public documentation | GitHub repository | Remove private and identifying data |

> 🔐 **Only assess systems you own or have explicit permission to test.** Respect applicable laws, website terms, and the agreed scope. Use conservative crawl settings to avoid unnecessary load.

Never publish passwords, tokens, session cookies, private messages, personal contact details, or unredacted target information.

---

# 📁 Project Structure

```text
photon-osint-recon-notes/
│
├── README.md
│
└── images/
    ├── 01-linux-user-setup.jpg
    ├── 02-photon-setup-and-run.jpg
    └── 03-photon-results-redacted.jpg
```

Keep the `images/` directory and filenames unchanged so that the README image links work on GitHub.

---

# 🚀 Future Improvements

- [ ] Add a dedicated local web-crawling lab.
- [ ] Document additional Photon options using authorized test targets.
- [ ] Compare crawl output across different test pages.
- [ ] Add sanitized sample output files.
- [ ] Record tool and environment versions for reproducibility.
- [ ] Compare crawler observations with manual verification.
- [ ] Create a structured reconnaissance report template.

---

# 👨‍💻 Author

<div align="center">

## PsychoMods

**Cybersecurity · Ethical Hacking · OSINT · Technology**

Learning by building, testing, and documenting.

[![GitHub](https://img.shields.io/badge/GitHub-Psychomods666-181717?style=for-the-badge&logo=github)](https://github.com/Psychomods666)

**Cybersecurity Learning Project**

</div>

---

<div align="center">

### 🔐 Learn • Test • Verify • Document

<sub>Created for cybersecurity education and authorized reconnaissance.</sub>

<sub>Photon is an upstream open-source project. This repository contains personal lab notes and is not an official Photon project.</sub>

</div>
