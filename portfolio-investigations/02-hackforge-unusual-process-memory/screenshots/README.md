# Screenshot Index

These screenshots are cropped and annotated Volatility output views used to support the report findings.

| File | What It Shows |
| --- | --- |
| [01-volatility-windows-info.png](01-volatility-windows-info.png) | `windows.info` output showing Windows version, kernel base, DTB, symbol table, and system time |
| [02-volatility-pslist-scvhost-annotated.png](02-volatility-pslist-scvhost-annotated.png) | `windows.pslist` output showing `scvhost.exe` with PID `5924` |
| [03-volatility-pstree-scvhost-parent-annotated.png](03-volatility-pstree-scvhost-parent-annotated.png) | `windows.pstree` output showing `scvhost.exe` spawned by `powershell.exe` |
| [04-volatility-cmdline-scvhost-annotated.png](04-volatility-cmdline-scvhost-annotated.png) | `windows.cmdline` output showing the suspicious process among normal process command lines |
| [05-volatility-vadinfo-scvhost-temp-path-annotated.png](05-volatility-vadinfo-scvhost-temp-path-annotated.png) | `windows.vadinfo` output showing the suspicious Temp-path executable mapping |
