# Evidence Notes

## Evidence

| Item | Value |
| --- | --- |
| Source | EVTX-ATTACK-SAMPLES, Credential Access |
| Evidence file | `CA_DCSync_4662.evtx` |
| Evidence type | Windows Security event log |
| SHA256 | `679B2FF27AF6C932C07BF3E81391E455FAE98E69BF3AFF0F524E31AADC418131` |
| Raw evidence committed | No |

## Reviewed Artifacts

| Artifact | Value |
| --- | --- |
| Channel | `Security` |
| Event ID | `4662` |
| Event count | `3` |
| Computer | `DC1.insecurebank.local` |
| Subject account | `insecurebank\Administrator` |
| Object server | `DS` |
| Accesses | `Control Access` |
| AccessMask | `0x100` |
| Observed properties | `%%7688 {1131f6ad-9c07-11d1-f79f-00c04fc2dcd2} {19195a5b-6da0-11d0-afd3-00c04fd930c9}` |

## Timestamp Notes

Event Viewer displayed the event time as `5/7/2019 7:10:43 PM`. The XML view recorded the event creation time as `2019-05-08T02:10:43.4872170Z`. The report uses the XML UTC timestamp when presenting normalized time.
