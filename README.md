# fukuro-reports

A public log of phishing and QR-code lure investigations, with a focus on Malaysian brands and payment apps.

Browse the reports: [reports/](reports/README.md)

## What each report contains

- A verdict with the reasons behind it, written out in plain words
- Where the link really goes: the redirect chain and the landing page
- Indicators of compromise, defanged so nothing is clickable
- MITRE ATT&CK techniques, only where the evidence supports them
- Recommended actions for a SOC
- Where useful: a YARA rule, and STIX and MISP exports for sharing

## How the findings are produced

Each case is triaged with a tool I built (Fukuro). A QR code is decoded locally, and the link is followed safely, with internal addresses blocked, and checked against Malaysian brand lookalike rules and around 17 public threat sources. The verdict comes from a transparent rule-based score, not a black box. When I have seen a page myself and confirmed it is phishing, the report says that was my decision and not something the tool detected.

## Handling

- Reports are TLP:CLEAR and published publicly.
- Links in reports are defanged. YARA rules and STIX or MISP files contain live indicators, because they are meant for detection and blocking.
- No victim, employer or customer data is included.
- Verdicts are triage assessments, not legal findings.
