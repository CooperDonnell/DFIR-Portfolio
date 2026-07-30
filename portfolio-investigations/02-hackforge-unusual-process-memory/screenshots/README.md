# Screenshot Index

These screenshots are cropped Volatility output views used to support the report findings.

| File | What It Shows |
| --- | --- |
| [01-volatility-windows-info.png](01-volatility-windows-info.png) | `windows.info` output showing Windows version, kernel base, DTB, symbol table, and system time |
| [02-volatility-pslist-scvhost.png](02-volatility-pslist-scvhost.png) | `windows.pslist` output showing `scvhost.exe` with PID `5924` |
| [03-volatility-pstree-scvhost-parent.png](03-volatility-pstree-scvhost-parent.png) | `windows.pstree` output showing `scvhost.exe` spawned by `powershell.exe` |
| [04-volatility-cmdline-scvhost.png](04-volatility-cmdline-scvhost.png) | `windows.cmdline` output showing the suspicious process among normal process command lines |
| [05-volatility-vadinfo-scvhost-temp-path.png](05-volatility-vadinfo-scvhost-temp-path.png) | `windows.vadinfo` output showing the suspicious Temp-path executable mapping |
