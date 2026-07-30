# Working Notes

Use this file as the answer sheet while analyzing the memory image.

## Evidence Verification

- Archive name: Unusual Process
- Archive MD5: 8833BDB908601A2FBBE38B679624A8A2
- Expected MD5:8833BDB908601A2FBBE38B679624A8A2
- Extracted memory image name: compromised_workstation.elf

## System Information

- Windows version/build: Windows 10
- Kernel base: 0xf8046a80e000
- DTB: 0x1aa000
- Symbol table: ntkrnlmp.pdb/89284D0CA6ACC8274B9A44BD5AF9290B-1
- System time: 2026-01-03 06:41:58 UTC
- PE timestamp: Fri May 20 08:24:42 2101

## Process Findings

### Suspicious Process Candidate

- Process name: scvhost.exe
- PID: 5924
- PPID: 3520
- Parent process: powershell.exe
- Process path if shown: C:\Users\Bob\AppData\Local\Temp\scvhost.exe
- Command line: 

### Why It Is Suspicious

List the evidence, not just the conclusion.

- svchost.exe is the correct spelling. Scvhost.exe is incorrect and its running from a user-writeable location. 

## Process Tree Notes

- Suspicious parent-child relationship: powershell to scvhost.exe
- Normal-looking processes nearby: svchost.exe
- Anything that appears masqueraded or oddly named: scvhost.exe

## Network Findings

- PID tied to network activity: 3520 powershell.exe
- Local address/port: 0.0.0.0:0 and :::0
- Remote address/port: *:0 / none shown
- State: UDP, no TCP state
- Why it matters: powershell.exe is the parent of suspicious PID 5924. No direct network socket was found for scvhost.exe, but its parent showed network artifacts before scvhost.exe started.

## Malfind Findings

- PID: 5924
- Process: scvhost.exe
- Memory region: No malfind regions reported
- Protection flags: No malfind protection flags reported
- Notable bytes/strings: None from malfind
- Interpretation: malfind did not identify injected or suspicious private executable memory for scvhost.exe. The process is still suspicious based on name, parent process, path, and VAD/file evidence.

## IOCs

| Type | Value | Context |
| --- | --- | --- |
| Process | scvhost.exe | Misspelled svchost.exe lookalike |
| PID | 5924 | Suspicious process spawned by powershell.exe |
| IP | 10.10.10.50 | Local host address observed in netscan |
| Port | N/A | No confirmed remote port tied directly to scvhost.exe |
| File path | \Users\Bob\AppData\Local\Temp\scvhost.exe | Suspicious executable path from pstree/filescan/vadinfo |

## Preliminary Conclusion

```text
The unusual process appears to be scvhost.exe, PID 5924. It is suspicious because it imitates the legitimate Windows svchost.exe name, was launched by powershell.exe, and ran from Bob's Temp directory rather than C:\Windows\System32. VAD analysis confirmed an executable memory mapping for \Users\Bob\AppData\Local\Temp\scvhost.exe.
```

