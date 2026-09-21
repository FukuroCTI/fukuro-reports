# fukuro-reports

Malaysia-focused threat hunting reports on IPs, domains, URLs, file hashes and QR codes, with a focus on Malaysian brands, organisations and payment apps.

Browse the reports: [reports/](reports/README.md)

## What each report contains

- A verdict with the reasons behind it, written out in plain words
- Where a link goes, or what a file did when it was run
- Indicators of compromise, defanged so nothing is clickable
- TTPs mapped to MITRE ATT&CK, only where the evidence supports them
- An intrusion analysis (adversary, capability, infrastructure, victim), with what is not known stated
- Recommended actions for a SOC
- Where useful: a YARA rule, and STIX and MISP exports for sharing

## About the findings

Each case is triaged with a tool I built (Fukuro). The verdict comes from a transparent, rule-based assessment. When I have seen a page myself and confirmed it is phishing, the report says that was my decision and not something the tool detected.

## Handling

- Reports are TLP:CLEAR and published publicly.
- Links in reports are defanged. YARA rules and STIX or MISP files contain live indicators, because they are meant for detection and blocking.
- No victim, employer or customer data is included.
- Verdicts are triage assessments, not legal findings.
