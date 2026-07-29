# Evidence Notes

## Evidence Set

Case: Meridian Financial Services - Ransomware Incident

Files:

- `meridian_workstation.E01`
- `meridian_incident.pcap`

Original ZIP MD5:

```text
F875B60AB2DF099805978DE9A2DA74EE
```

## Network Capture Note

The original network capture was distributed as `meridian_incident.pcap`, but the file was identified as malformed pcapng. The packet records were still readable. A clean working copy was rebuilt into standard libpcap format for Wireshark analysis.

Clean analysis copy:

```text
meridian_incident_clean.pcap
MD5: 2ffb673f5ffc1b76692c7f3872a53a53
Packets: 62
```

The clean analysis copy should be treated as a derived working file. The original evidence ZIP and original capture should be retained separately.

## Timestamp Caution

Disk artifact timestamps and network capture timestamps differ significantly:

- Network capture dates: `2024-03-14`
- MFT and Prefetch file metadata dates shown by Autopsy: `2026-05-23`

The report should avoid overclaiming exact cross-source ordering unless additional case documentation explains the timestamp discrepancy. The timeline separates source-specific timestamps and identifies source/timezone when known.

## Screenshots to Capture

Recommended screenshots are listed in [screenshots/README.md](screenshots/README.md).

