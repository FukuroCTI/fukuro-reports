# Fukuro Triage Report

- **Indicator:** `hxxps://jkmss-a[.]sbs/x` (url)
- **Verdict:** MALICIOUS (score -6)
- **Generated:** 2026-09-22 20:39 UTC
- **Impersonates:** Touch 'n Go
- **Resolves to:** `45[.]33[.]32[.]156`

## Why this verdict

- Analyst confirmed this is a phishing page impersonating Touch 'n Go. This was a human decision, not detected automatically

The score is a transparent rule-based sum of the findings above, not an analyst judgment.

## QR code

- **Type:** undefined
- **Contents:** `undefined`

## Where the link goes

| Hop | URL | Result | Server IP |
| --- | --- | --- | --- |
| 1 | `hxxps://jkmss-a[.]sbs/x` | HTTP 200 | `45[.]33[.]32[.]156` |

Final destination: `hxxps://jkmss-a[.]sbs/x`

## Landing page

- **Title:** Verify
- **Title:** Verify
- **Password field:** Yes

## TTPs

Tactics, techniques and procedures, mapped to MITRE ATT&CK. Each row is backed by something that was observed.

| Tactic | Technique | ID | Procedure |
| --- | --- | --- | --- |
| Initial Access | Phishing: Spearphishing Link | T1566.002 | A phishing link delivered as a QR code |
| Resource Development | Acquire Infrastructure: Domains | T1583.001 | A domain registered 6 days ago |
| Reconnaissance | Phishing for Information: Spearphishing Link | T1598.003 | The page asks for a password |

## Intrusion analysis

Event: Phishing impersonating Touch 'n Go, from a QR code (jkmss-a[.]sbs, 2026-09-22).

Confidence is High when the finding was observed directly, and Medium or Low when it is an assessment. Unknown means it could not be determined.

![Diamond model](diamond.svg)

| Feature | Aspect | Finding | Confidence |
| --- | --- | --- | --- |
| Adversary | Identity | Unattributed | Unknown |
| Adversary | Operator or customer | Unknown. Nothing shows whether the operator built the kit or bought it | Unknown |
| Adversary | Likely motivation | Financial: theft of account credentials | Medium (assessed) |
| Capability | Lure | Credential-harvesting page impersonating Touch 'n Go | High |
| Capability | Delivery | QR code (quishing) | High |
| Capability | ATT&CK techniques | T1566.002, T1583.001, T1598.003 | Medium (assessed) |
| Infrastructure | Lure domain | jkmss-a[.]sbs, registered 6 days ago | High |
| Infrastructure | Infrastructure type | Type 1 (likely): newly registered, so probably bought by the adversary | Medium (assessed) |
| Infrastructure | Hosting | 45[.]33[.]32[.]156 | High |
| Victim | Persona | Customers of Touch 'n Go in Malaysia | High (analyst) |
| Victim | Target assets | Online account credentials (a login form was observed) | High |
| Victim | Target assets | Account credentials, assessed from the impersonated login. No form was observed | Low (assessed) |
| Victim | How it reached them | A QR code. Where it was displayed is not recorded | High |
| Victim | Real individuals | None identified or recorded here | Unknown |

| Meta-feature | Value |
| --- | --- |
| Timestamp | Analysed 2026-09-22. The domain was registered about 2026-09-16 |
| Phase | Delivery: the link is presented to the victim as a QR code; Exploitation: the victim is asked to type credentials into the fake page (login form observed); Actions on objectives: credential theft for fraud or account takeover (assessed) |
| Result | Unknown. This tool cannot see whether anyone was deceived |
| Direction | Adversary to victim |
| Methodology | Phishing: credential harvesting, delivered by QR code (quishing) |
| Resources | A recently registered domain |
| Social-political axis | A financially motivated actor targeting users of a Malaysian brand (assessed, low confidence) |
| Technology axis | A QR lure leading to a credential page on a newly registered domain |

Where to pivot next:

- Find other domains on 45[.]33[.]32[.]156 (reverse IP: Censys, Shodan, VirusTotal relations)
- Look for other lookalikes of Touch 'n Go registered recently (certificate transparency: search crt.sh for the brand name)
- Check jkmss-a[.]sbs on urlscan.io and VirusTotal for sibling domains and related pages

What is not known:

- Who the adversary is
- Whether anyone was deceived, and how many
- Which phishing kit or toolset was used

## Indicators (defanged)

| Type | Value | Use |
| --- | --- | --- |
| url | `hxxps://jkmss-a[.]sbs/x` | Block |
| ipv4 | `45[.]33[.]32[.]156` | Context, review first |
| domain | `jkmss-a[.]sbs` | Block |

## Recommended actions

1. Keep the message and attachment quarantined. Do not release.
2. Search mail logs for other recipients of the same sender, subject or hash.
3. Block the indicators marked for blocking at the gateway, proxy and EDR.
4. If anyone opened it, isolate that host and reset their credentials.
5. Share the indicators to MISP or OpenCTI using the exports.
6. Report the page to Touch 'n Go's abuse or fraud team and to MyCERT (Cyber999) for takedown.
7. Submit the URL to Google Safe Browsing and VirusTotal so browsers and scanners start blocking it.
8. If the QR code was a physical sticker or poster, photograph it, remove it, and check nearby codes.
