# Fukuro Triage Report

- **Indicator:** `hxxps://tng[.]jkmss-a[.]sbs/Rayamacam2[.]my7/` (url)
- **Verdict:** MALICIOUS (score -9)
- **Generated:** 2026-09-21 23:41 UTC
- **Sharing:** TLP:CLEAR (published publicly)
- **Impersonates:** Touch 'n Go
- **Resolves to:** `172[.]67[.]187[.]163`

## Why this verdict

- Analyst confirmed this is a phishing page impersonating Touch 'n Go. This was a human decision, not detected automatically
- AbuseIPDB: no abuse reports on record
- .sbs is a TLD commonly used for throwaway phishing domains
- Impersonation: jkmss-a.sbs contains "tng" but is not an official Touch 'n Go domain (touchngo.com.my).
- Landing page asks for a password while imitating Touch 'n Go
- Landing page asks for a phone number to send a Telegram login code while imitating Touch 'n Go

The score is a transparent rule-based sum of the findings above, not an analyst judgment.

## QR code

- **Type:** Web link
- **Contents:** `hxxps://tng[.]jkmss-a[.]sbs/Rayamacam2[.]my7/`

## Where the link goes

| Hop | URL | Result | Server IP |
| --- | --- | --- | --- |
| 1 | `hxxps://tng[.]jkmss-a[.]sbs/Rayamacam2[.]my7/` | HTTP 200 | `104[.]21[.]92[.]69` |

Final destination: `hxxps://tng[.]jkmss-a[.]sbs/Rayamacam2[.]my7/`

## Landing page

- **Title:** A surprise Money Packet for you!
- **Title:** A surprise Money Packet for you!
- **Password field:** Yes
- **Phone number field:** Yes (the page mentions Telegram)
- **Asks for a phone number and a one-time code:** Yes

## Where it was posted

This link or QR code was posted by the accounts below. The accounts are not verified: an account that posts a lure can belong to the adversary, or be compromised or an impersonation, so this is a distribution channel and not attribution.

- Threads: `@sittizakiahdzulkhadir` (posted 2026-09-21)

## Evidence

![Evidence 1](evidence-1.png)

## TTPs

Tactics, techniques and procedures, mapped to MITRE ATT&CK. Each row is backed by something that was observed.

| Tactic | Technique | ID | Procedure |
| --- | --- | --- | --- |
| Initial Access | Phishing: Spearphishing Link | T1566.002 | A phishing link delivered as a QR code |
| Resource Development | Acquire Infrastructure: Domains | T1583.001 | A domain that imitates Touch 'n Go |
| Reconnaissance | Phishing for Information: Spearphishing Link | T1598.003 | The page asks for a password and a Telegram phone number |

## Intrusion analysis

Event: Phishing impersonating Touch 'n Go, from a QR code (jkmss-a[.]sbs, 2026-09-21).

Confidence is High when the finding was observed directly, and Medium or Low when it is an assessment. Unknown means it could not be determined.

```mermaid
%%{init: {'flowchart': {'curve': 'linear'}}}%%
flowchart TB
  A["Adversary<br/>Unattributed"]
  C["Capability<br/>Credential phishing,<br/>QR lure"]
  I["Infrastructure<br/>jkmss-a[.]sbs, AS13335"]
  V["Victim<br/>Touch 'n Go customers<br/>(Malaysia)"]
  A --- C
  A --- I
  C --- V
  I --- V
  classDef adv fill:#f9d5dc,stroke:#d20f39,color:#1e1e2e
  classDef cap fill:#fde6d2,stroke:#c25b00,color:#1e1e2e
  classDef inf fill:#d6e4ff,stroke:#1e66f5,color:#1e1e2e
  classDef vic fill:#d9f0d9,stroke:#2c8a2c,color:#1e1e2e
  class A adv
  class C cap
  class I inf
  class V vic
```

| Feature | Aspect | Finding | Confidence |
| --- | --- | --- | --- |
| Adversary | Identity | Unattributed | Unknown |
| Adversary | Operator or customer | Unknown. Nothing shows whether the operator built the kit or bought it | Unknown |
| Adversary | Likely motivation | Financial: theft of account credentials | Medium (assessed) |
| Capability | Lure | Credential-harvesting page impersonating Touch 'n Go | High |
| Capability | Delivery | QR code (quishing) | High |
| Capability | ATT&CK techniques | T1566.002, T1583.001, T1598.003 | Medium (assessed) |
| Infrastructure | Lure domain | jkmss-a[.]sbs | High |
| Infrastructure | Infrastructure type | Type not determined: adversary-owned or compromised, this cannot be told apart | Unknown |
| Infrastructure | Distribution channel | Threads @sittizakiahdzulkhadir (2026-09-21) posted the lure | High (analyst) |
| Infrastructure | Account type | Not determined: the accounts may belong to the adversary, be compromised, or be impersonations | Unknown |
| Infrastructure | Hosting | 172[.]67[.]187[.]163 (AS13335 Cloudflare, Inc., US) | High |
| Victim | Persona | Customers of Touch 'n Go in Malaysia | High |
| Victim | Target assets | Online account credentials (a login form was observed) | High |
| Victim | Target assets | Telegram account access: the page asks for a phone number, and a login code is the usual next step | Medium (assessed) |
| Victim | How it reached them | A QR code. Where it was displayed is not recorded | High |
| Victim | Real individuals | None identified or recorded here | Unknown |

| Meta-feature | Value |
| --- | --- |
| Timestamp | Analysed 2026-09-21. First seen posted on 2026-09-21 |
| Phase | Delivery: the link is presented to the victim as a QR code, posted on Threads; Exploitation: the victim is asked to type credentials into the fake page (login form observed); Exploitation: the victim is asked for a Telegram phone number (form observed); Actions on objectives: credential theft for fraud or account takeover (assessed) |
| Result | Unknown. This tool cannot see whether anyone was deceived |
| Direction | Adversary to victim |
| Methodology | Phishing: credential harvesting, delivered by QR code (quishing), using a lookalike domain |
| Resources | A domain, hosting at AS13335 Cloudflare |
| Social-political axis | A financially motivated actor targeting users of a Malaysian brand (assessed, low confidence) |
| Technology axis | A QR lure leading to a credential page hosted at AS13335 Cloudflare |

Where to pivot next:

- Look through the public posts of Threads @sittizakiahdzulkhadir for the same link, QR image or wording, and for other accounts reposting it
- Find other domains on 172[.]67[.]187[.]163 (reverse IP: Censys, Shodan, VirusTotal relations)
- Look for other lookalikes of Touch 'n Go registered recently (certificate transparency: search crt.sh for the brand name)
- Check jkmss-a[.]sbs on urlscan.io and VirusTotal for sibling domains and related pages

What is not known:

- Who the adversary is
- Whether anyone was deceived, and how many
- Whether the accounts that posted it belong to the adversary
- Which phishing kit or toolset was used

## Indicators (defanged)

| Type | Value | Use |
| --- | --- | --- |
| url | `hxxps://tng[.]jkmss-a[.]sbs/Rayamacam2[.]my7/` | Block |
| ipv4 | `172[.]67[.]187[.]163` | Context, review first |
| domain | `tng[.]jkmss-a[.]sbs` | Block |
| ipv4 | `104[.]21[.]92[.]69` | Context, review first |

## Recommended actions

1. Keep the message and attachment quarantined. Do not release.
2. Search mail logs for other recipients of the same sender, subject or hash.
3. Block the indicators marked for blocking at the gateway, proxy and EDR.
4. If anyone opened it, isolate that host and reset their credentials.
5. Share the indicators to MISP or OpenCTI using the exports.
6. Report the page to Touch 'n Go's abuse or fraud team and to MyCERT (Cyber999) for takedown.
7. Submit the URL to Google Safe Browsing and VirusTotal so browsers and scanners start blocking it.
8. If the QR code was a physical sticker or poster, photograph it, remove it, and check nearby codes.
