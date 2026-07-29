# Meridian Financial Services Ransomware Incident

## Case Summary

This investigation analyzes a public ransomware case involving a Windows workstation and network capture. The suspected incident began with a malicious macro-enabled Word document and progressed through PowerShell-based staging, command-and-control communication, defense evasion, lateral movement, data staging, and LockBit ransomware execution.

![Autopsy view of malicious document](screenshots/01-autopsy-invoice-docm.png)

## Evidence Source

- Source: RedHatPentester DIGITAL-FORENSICS-CTF-LAB, "Meridian Financial Services - Ransomware Incident"
- Evidence files:
  - `meridian_workstation.E01`
  - `meridian_incident.pcap`
- Original ZIP MD5: `F875B60AB2DF099805978DE9A2DA74EE`

Raw evidence is not included in this repository. Only analysis notes, screenshots, derived indicators, and reporting artifacts are included.

## Tools Used

- Autopsy
- Wireshark
- PowerShell `Get-FileHash`

## Key Findings

- Initial access was linked to `Invoice_March2024.docm`, a macro-enabled Word document.
- The host communicated with `meridian-invoices.com`, which resolved to `185.220.101.47`.
- The observed PowerShell cradle retrieved `stage1.ps1` from `http://meridian-invoices.com/stage1.ps1`.
- The malware configuration identified `185.220.101.47` as C2 and `https://mega.nz/upload` as the exfiltration target.
- Windows Defender real-time protection was disabled.
- Shadow copies were deleted using `vssadmin` and `wmic`.
- The attacker accessed internal host `192.168.1.88` over SMB.
- User documents were compressed into `C:\Windows\Temp\exfil_pack.zip`.
- LockBit indicators were present, including `.lockbit`, `Restore-My-Files.txt`, and a LockBit onion domain.

## Repository Contents

- [report.md](report.md): Main investigation report
- [timeline.csv](timeline.csv): Condensed incident timeline
- [iocs.csv](iocs.csv): Indicators of compromise
- [evidence-notes.md](evidence-notes.md): Evidence handling and artifact notes
- [screenshots/README.md](screenshots/README.md): Screenshot index
