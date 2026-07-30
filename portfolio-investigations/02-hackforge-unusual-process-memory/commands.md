# Minimal Volatility Workflow

Replace `<memory-image>` with the extracted memory image path.

## Hash the Evidence Archive

```powershell
Get-FileHash ".\unusual-process.7z" -Algorithm MD5
```

Expected MD5 from Evidence Locker:

```text
8833BDB908601A2FBBE38B679624A8A2
```

## Baseline System Information

```powershell
python vol.py -f "<memory-image>" windows.info
```

Record:

- Kernel base
- DTB
- Symbol table
- Windows version/build
- System time if shown

## Process Review

```powershell
python vol.py -f "<memory-image>" windows.pslist
python vol.py -f "<memory-image>" windows.pstree
python vol.py -f "<memory-image>" windows.cmdline
```

Look for:

- Odd process names
- Processes running from unusual paths
- Suspicious parent-child relationships
- Command lines using encoded commands, temp paths, scripts, or network tooling

## Network Review

```powershell
python vol.py -f "<memory-image>" windows.netscan
```

Look for:

- External connections
- Suspicious listening ports
- Network activity tied to the unusual process PID

## Injection / Suspicious Memory Review

```powershell
python vol.py -f "<memory-image>" windows.malfind
```

Look for:

- Suspicious executable memory regions
- Regions tied to the unusual process PID
- Output that shows `MZ`, shellcode-like bytes, or suspicious protection flags

## Focused Follow-Up

Only run these if the previous outputs point to a specific PID:

```powershell
python vol.py -f "<memory-image>" windows.dlllist --pid <PID>
python vol.py -f "<memory-image>" windows.handles --pid <PID>
```

Look for:

- DLLs loaded from temporary or user-writable directories
- Handles to suspicious files, registry keys, or network-related objects

