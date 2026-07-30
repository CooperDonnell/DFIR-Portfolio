# Screenshot Index

These screenshots are cropped and annotated analysis views used to support the report findings.

| File | What It Shows |
| --- | --- |
| [01-autopsy-invoice-docm.png](01-autopsy-invoice-docm.png) | Autopsy view of `Invoice_March2024.docm` in the user Downloads folder |
| [02-autopsy-prefetch-execution-artifacts.png](02-autopsy-prefetch-execution-artifacts.png) | Prefetch artifacts for Word, PowerShell, MSHTA, VSSADMIN, `svchost_tmp.exe`, and LockBit |
| [03-autopsy-powershell-stage1.png](03-autopsy-powershell-stage1.png) | PowerShell staging content and attack commands |
| [04-autopsy-lockbit-config.png](04-autopsy-lockbit-config.png) | `lb_config.json` with C2, exfiltration target, extension, ransom note, and anti-recovery settings |
| [05-wireshark-dns-docm-download.png](05-wireshark-dns-docm-download.png) | DNS resolution for `meridian-invoices.com` and HTTP retrieval of `Invoice_March2024.docm` |
| [06-wireshark-c2-and-smb.png](06-wireshark-c2-and-smb.png) | C2 traffic and SMB activity involving internal host `192.168.1.88` |
| [07-wireshark-exfil-lockbit-dns.png](07-wireshark-exfil-lockbit-dns.png) | Mega-related traffic and LockBit onion DNS lookup |
