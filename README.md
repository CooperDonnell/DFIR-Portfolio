# DFIR Education Portfolio

This repository documents a focused 105-hour digital forensics and incident
response training sprint from June 22 through August 7, 2026. It begins from a
documented beginner baseline and emphasizes measurable improvement rather than
implied prior expertise.

## Goals

- Investigate Windows endpoint, memory, network, and identity evidence.
- Build defensible timelines and explain conclusions with cited artifacts.
- Connect forensic findings to containment, eradication, and recovery.
- Demonstrate forensic-tool engineering through a validated project.
- Publish professional case reports that can be discussed in interviews.

## Portfolio investigations

- [Meridian Financial Services Ransomware Incident](portfolio-investigations/01-meridian-ransomware-incident/) - Windows disk and PCAP analysis of a LockBit-style ransomware intrusion.

Planned next cases:

1. Windows memory triage investigation
2. Scoped enterprise compromise investigation
3. HeaderHunter forensic-tool engineering case study

## Existing flagship project

**HeaderHunter** is a cross-platform forensic CLI and GUI developed during an
internship to identify encrypted containers and expose defensible metadata for
triage and recovery workflows. The project includes format-aware detectors,
entropy and statistical analysis, tests, documentation, and packaging for
Windows, macOS, and Linux.

Because the source project was developed in an internship environment, this
repository contains only a sanitized case-study template. Source code,
screenshots, employer details, datasets, and internal design information must
not be published without written authorization from the rights holder.

See [projects/headerhunter-case-study.md](projects/headerhunter-case-study.md).

## Repository standard

Every published case will include:

- An executive summary
- Scope and investigative questions
- Evidence inventory and integrity information
- Methodology and tools
- UTC-normalized timeline
- Findings with artifact-level support
- MITRE ATT&CK mapping
- Indicators and detection opportunities
- Containment, eradication, and recovery recommendations
- Limitations and unanswered questions

The portfolio investigation index is in [portfolio-investigations/README.md](portfolio-investigations/README.md).

The detailed schedule is in [STUDY_PLAN.md](STUDY_PLAN.md). The working
checklist is in [TRACKER.md](TRACKER.md).

The starting assessment is in [notes/baseline.md](notes/baseline.md).
