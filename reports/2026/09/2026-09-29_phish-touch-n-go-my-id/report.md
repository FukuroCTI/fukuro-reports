# Fukuro Triage Report

- **Indicator:** `hxxps://tng5[.]mobilegrub20[.]my[.]id` (url)
- **Verdict:** MALICIOUS (score -10)
- **Generated:** 2026-09-28 21:29 UTC
- **Sharing:** TLP:CLEAR (published publicly)
- **Impersonates:** Touch 'n Go
- **Resolves to:** `202[.]73[.]25[.]122`

## Why this verdict

- Analyst confirmed this is a phishing page impersonating Touch 'n Go. This was a human decision, not detected automatically
- OpenPhish: 1 other page(s) on my.id are on the live phishing feed
- LeakIX: 519 exposed service(s) and 5 leak(s) indexed on this IP. Context, not a verdict on this indicator
- AbuseIPDB: no abuse reports on record
- Impersonation: my.id contains "tng" but is not an official Touch 'n Go domain (touchngo.com.my).
- Followed the page's continue link to https://tng5.mobilegrub20.my.id/login.php
- The next page asks for a phone number to send a Telegram login code while imitating Touch 'n Go

The score is a transparent rule-based sum of the findings above, not an analyst judgment.

## QR code

- **Type:** Web link
- **Contents:** `hxxps://tng5[.]mobilegrub20[.]my[.]id`

## Where the link goes

| Hop | URL | Result | Server IP |
| --- | --- | --- | --- |
| 1 | `hxxps://tng5[.]mobilegrub20[.]my[.]id/` | HTTP 200 | `202[.]73[.]25[.]122` |

Final destination: `hxxps://tng5[.]mobilegrub20[.]my[.]id/`

## Landing page

- **Title:** Touch 'n Go Rewards
- **Title:** Touch 'n Go Rewards
- **Password field:** No

## Page after continue

- **How it was found:** a continue link on the landing page
- **URL:** `hxxps://tng5[.]mobilegrub20[.]my[.]id/login[.]php`
- **Title:** TELEGRAM
- **Password field:** No
- **Phone number field:** Yes (the page mentions Telegram)
- **Asks for a phone number and a one-time code:** Yes

## Where it was posted

This link or QR code was posted by the accounts below. The accounts are not verified: an account that posts a lure can belong to the adversary, or be compromised or an impersonation, so this is a distribution channel and not attribution.

- Threads: `@_camell_12` (posted 2026-09-29)

## Evidence

![Evidence 1](evidence-1.png)

![Evidence 2](evidence-2.png)

## TTPs

Tactics, techniques and procedures, mapped to MITRE ATT&CK. Each row is backed by something that was observed.

| Tactic | Technique | ID | Procedure |
| --- | --- | --- | --- |
| Initial Access | Phishing: Spearphishing Link | T1566.002 | A phishing link delivered as a QR code |
| Resource Development | Acquire Infrastructure: Domains | T1583.001 | A domain that imitates Touch 'n Go |
| Reconnaissance | Phishing for Information: Spearphishing Link | T1598.003 | The page asks for a Telegram phone number (on the page after continue) |

## Intrusion analysis

Event: Phishing impersonating Touch 'n Go, from a QR code (my[.]id, 2026-09-28).

Confidence is High when the finding was observed directly, and Medium or Low when it is an assessment. Unknown means it could not be determined.

![Diamond model](diamond.svg)

| Feature | Aspect | Finding | Confidence |
| --- | --- | --- | --- |
| Adversary | Identity | Unattributed | Unknown |
| Adversary | Operator or customer | Unknown. Nothing shows whether the operator built the kit or bought it | Unknown |
| Adversary | Likely motivation | Financial: theft of account credentials | Medium (assessed) |
| Capability | Lure | Page that asks for a Telegram phone number impersonating Touch 'n Go | High |
| Capability | Delivery | QR code (quishing) | High |
| Capability | ATT&CK techniques | T1566.002, T1583.001, T1598.003 | Medium (assessed) |
| Infrastructure | Lure domain | my[.]id | High |
| Infrastructure | Infrastructure type | Type not determined: adversary-owned or compromised, this cannot be told apart | Unknown |
| Infrastructure | Distribution channel | Threads @_camell_12 (2026-09-29) posted the lure | High (analyst) |
| Infrastructure | Account type | Not determined: the accounts may belong to the adversary, be compromised, or be impersonations | Unknown |
| Infrastructure | Hosting | 202[.]73[.]25[.]122 (AS141892 CV Andhika Pratama Sanggoro, ID) | High |
| Infrastructure | Independently flagged by | OpenPhish | High |
| Victim | Persona | Customers of Touch 'n Go in Malaysia | High |
| Victim | Target assets | Telegram account access: the page asks for a phone number, and a login code is the usual next step | Medium (assessed) |
| Victim | How it reached them | A QR code. Where it was displayed is not recorded | High |
| Victim | Real individuals | None identified or recorded here | Unknown |

| Meta-feature | Value |
| --- | --- |
| Timestamp | Analysed 2026-09-28. First seen posted on 2026-09-29 |
| Phase | Delivery: the link is presented to the victim as a QR code, posted on Threads; Exploitation: the victim is asked for a Telegram phone number (form observed, on the page after continue); Actions on objectives: credential theft for fraud or account takeover (assessed) |
| Result | Unknown. This tool cannot see whether anyone was deceived |
| Direction | Adversary to victim |
| Methodology | Phishing: phone number and one-time code capture, delivered by QR code (quishing), using a lookalike domain |
| Resources | A domain, hosting at AS141892 CV Andhika Pratama Sanggoro |
| Social-political axis | A financially motivated actor targeting users of a Malaysian brand (assessed, low confidence) |
| Technology axis | A QR lure leading to a phone and code capture page hosted at AS141892 CV Andhika Pratama Sanggoro |

Where to pivot next:

- Look through the public posts of Threads @_camell_12 for the same link, QR image or wording, and for other accounts reposting it
- Find other domains on 202[.]73[.]25[.]122 (reverse IP: Censys, Shodan, VirusTotal relations)
- Look for other lookalikes of Touch 'n Go registered recently (certificate transparency: search crt.sh for the brand name)
- Check my[.]id on urlscan.io and VirusTotal for sibling domains and related pages

What is not known:

- Who the adversary is
- Whether anyone was deceived, and how many
- Whether the accounts that posted it belong to the adversary
- Which phishing kit or toolset was used

## Indicators (defanged)

| Type | Value | Use |
| --- | --- | --- |
| url | `hxxps://tng5[.]mobilegrub20[.]my[.]id` | Block |
| ipv4 | `202[.]73[.]25[.]122` | Context, review first |
| domain | `tng5[.]mobilegrub20[.]my[.]id` | Block |
| url | `hxxps://tng5[.]mobilegrub20[.]my[.]id/` | Block |
| url | `hxxps://tng5[.]mobilegrub20[.]my[.]id/login[.]php` | Block |

## Recommended actions

1. Keep the message and attachment quarantined. Do not release.
2. Search mail logs for other recipients of the same sender, subject or hash.
3. Block the indicators marked for blocking at the gateway, proxy and EDR.
4. If anyone opened it, isolate that host and reset their credentials.
5. Share the indicators to MISP or OpenCTI using the exports.
6. Report the page to Touch 'n Go's abuse or fraud team and to MyCERT (Cyber999) for takedown.
7. Submit the URL to Google Safe Browsing and VirusTotal so browsers and scanners start blocking it.
8. If the QR code was a physical sticker or poster, photograph it, remove it, and check nearby codes.
