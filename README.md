# Cooper Donnell DFIR Portfolio

This repository contains digital forensics and incident response case studies built from public evidence sets. Each case is written as a practical investigation with evidence handling notes, artifact-level findings, timelines, indicators, annotated screenshots, and remediation recommendations.

## Goals

- Analyze public forensic images, memory captures, and network captures.
- Build defensible timelines and explain conclusions with cited artifacts.
- Connect findings to incident response, detection, and remediation.
- Present each investigation clearly enough to discuss in interviews.

## Portfolio investigations

- [Meridian Financial Services Ransomware Incident](portfolio-investigations/01-meridian-ransomware-incident/) - Windows disk and PCAP analysis of a LockBit-style ransomware intrusion.
- [HackForge Unusual Process Memory Triage](portfolio-investigations/02-hackforge-unusual-process-memory/) - Windows memory triage of a suspicious `svchost.exe` lookalike process.

Planned next case:

1. Scoped enterprise compromise investigation

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

Raw evidence, tool output dumps, and analyst scratch notes are intentionally excluded so the repository stays focused on polished case reporting.

The portfolio investigation index is in [portfolio-investigations/README.md](portfolio-investigations/README.md).
