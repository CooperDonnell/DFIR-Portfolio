# Evidence Notes

## Evidence Set

Case: HackForge - Unusual Process

Evidence:

```text
unusual-process.7z
```

Expected MD5:

```text
8833BDB908601A2FBBE38B679624A8A2
```

## Handling Notes

- Store the raw archive and extracted memory image outside this repository.
- Do not commit the memory image, archive, or extracted raw evidence.
- Commit only notes, screenshots, timelines, indicators, and final reporting artifacts.

## Tool Scope

This case should use only:

- Volatility 3
- PowerShell `Get-FileHash`

Additional tools should be added only if the Volatility output creates a specific unanswered question.

