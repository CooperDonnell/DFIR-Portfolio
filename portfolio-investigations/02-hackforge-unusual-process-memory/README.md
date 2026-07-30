# HackForge Unusual Process Memory Triage

## Case Summary

This investigation analyzes a small public Windows memory image from HackForge. The unusual process was identified as `scvhost.exe`, a misspelled `svchost.exe` lookalike launched by PowerShell from a user-writable Temp directory.

This is intentionally scoped as a tight memory-triage case, not a full enterprise incident response investigation.

## Evidence Source

- Source: HackForge, "Unusual Process"
- Evidence file: `unusual-process.7z`
- Category: Windows memory
- OS listed by Evidence Locker: Windows 10 (19045)
- Size listed by Evidence Locker: 103 MB
- Hash listed by Evidence Locker: `8833BDB908601A2FBBE38B679624A8A2`
- Download: `https://hackforge.com/downloads/challenges/forensics/unusual-process.7z`
- Challenge info: `https://hackforge.com/app/challenge/20`

Raw evidence, command logs, and analyst scratch notes are not included in this repository. Download and analyze the evidence outside the repo, then add only final reporting artifacts, evidence summaries, annotated screenshots, and derived indicators here.

## Tools

- Volatility 3
- PowerShell `Get-FileHash`

No Autopsy, no Zimmerman tools, and no custom lab are needed for this case.

## Investigation Goal

Answer one core question:

```text
What process is unusual, why is it suspicious, and what evidence in memory supports that conclusion?
```

## Key Findings

- The suspicious process was `scvhost.exe` with PID `5924`.
- The process name imitates legitimate Windows `svchost.exe`, but the letters are transposed.
- The process ran from `C:\Users\Bob\AppData\Local\Temp\scvhost.exe`, a user-writable path.
- The parent process was `powershell.exe` with PID `3520`.
- Volatility network review did not identify a confirmed remote connection tied directly to `scvhost.exe`.
- `malfind` did not report injected or suspicious private executable memory for `scvhost.exe`.
- The conclusion is based on process masquerading, suspicious parentage, user-writable execution path, and memory artifact evidence.

## Repository Contents

- [report.md](report.md): Main investigation report
- [evidence-notes.md](evidence-notes.md): Evidence handling notes
- [iocs.csv](iocs.csv): Indicators of compromise
- [screenshots/README.md](screenshots/README.md): Screenshot checklist

## Evidence Policy

Raw evidence and internal working material are not included in this repository. Only final reports, evidence summaries, indicators, and annotated screenshots should be committed.
