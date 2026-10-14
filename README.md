# Project 4 — System Exploitation Fundamentals with Metasploit

A GitHub-ready documentation and reporting workspace for the **Ethical Hacking Project 4** brief: controlled exploitation validation in an isolated lab, post-exploitation evidence collection, and mitigation recommendations.

> **Safety boundary:** Use only systems you own or have explicit written permission to test. The lab must be isolated from the internet and production networks. This repository intentionally does not include automated exploitation, credential-dumping, persistence, or lateral-movement scripts. Perform any hands-on exercise only under your instructor's approved procedure and document the actual results.

## Objectives from the project brief

- Research at least three services/vulnerabilities identified by an earlier assessment.
- Review relevant Metasploit modules and their options.
- Validate approved findings against intentionally vulnerable lab VMs.
- Record session evidence and limited system information.
- Explain impact and recommend mitigations.
- Close sessions and restore/reset lab machines according to the lab rules.

The uploaded brief names **Metasploitable2**, a deliberately vulnerable **Windows 7** VM, and examples including vsftpd 2.3.4, MS17-010/EternalBlue, and an UnrealIRCd backdoor. Treat these as lab examples, not targets to scan on public or shared networks.

## Repository layout

```text
metasploit-project-4/
├── README.md
├── .gitignore
├── requirements.txt
├── docs/
│   ├── lab-safety.md
│   ├── workflow.md
│   └── mitigation-reference.md
├── templates/
│   ├── authorization-and-scope.md
│   ├── exploitation-logbook.csv
│   ├── post-exploitation-report.md
│   └── evidence-register.csv
└── evidence/
    └── README.md
```

## Prerequisites

- Kali Linux or another approved testing host with Metasploit Framework installed.
- Instructor-approved, intentionally vulnerable target VMs.
- A host-only or isolated virtual network with **no outbound connectivity**.
- A snapshot/checkpoint of each target before testing.
- Written scope and approval completed in `templates/authorization-and-scope.md`.

No Python dependencies are required for this documentation-only repository. `requirements.txt` is intentionally empty except for a note.

## Workflow

1. Complete the scope and authorization template.
2. Confirm the virtual network is isolated and record the lab IP addresses.
3. Start with non-invasive module research and option review.
4. Follow your instructor's approved validation procedure one target at a time.
5. Record every attempt, including unsuccessful attempts, in the logbook.
6. Save redacted screenshots and metadata in `evidence/`; never commit credentials, hashes, tokens, personal data, or sensitive files.
7. Write the impact and mitigation report.
8. Close all sessions, remove any lab-only changes, and reset VMs if required.
9. Review the repository for secrets before pushing it to GitHub.

## Safe Metasploit research commands

Run these in `msfconsole` to learn about modules without launching an exploit:

```text
help
search vsftpd
search eternalblue
search unrealircd
info <module-path-from-search-results>
```

Use `info` to review the module description, references, targets, and options. Do not run a module until the target, authorization, expected impact, and rollback plan are confirmed. Use the exact module path returned by your installed version; module names can change between releases.

## GitHub setup

From the directory containing this README:

```bash
git init
git add .
git status
git commit -m "Add Metasploit Project 4 lab documentation"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main
```

Create an empty repository on GitHub first, then replace the URL with your repository URL. If Git asks for identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

If this folder is already inside an existing Git repository, do **not** run `git init` again; inspect `git status` first.

## References

- [Rapid7 Metasploit module documentation](https://docs.rapid7.com/metasploit/modules/)
- [Metasploit Framework: using Metasploit](https://docs.metasploit.com/docs/using-metasploit/basics/using-metasploit.html)

## Project status

This repository provides a safe workflow and report structure. Fill in actual observations from your authorized lab; do not claim a vulnerability was exploited unless you personally verified it and recorded evidence.
