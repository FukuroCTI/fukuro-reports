# Fukuro Triage Report

- **Indicator:** `hxxp://iiot[.]gmi[.]edu[.]my/` (url)
- **Verdict:** SUSPICIOUS (score -3)
- **Generated:** 2026-10-12 23:36 UTC
- **Sharing:** TLP:CLEAR (published publicly)
- **Resolves to:** `216[.]194[.]175[.]95`

## Why this verdict

- VirusTotal: clean across 57 engines
- LeakIX: 39 exposed service(s) indexed on this IP. Context, not a verdict on this indicator
- AbuseIPDB: no abuse reports on record
- Followed the page's form target to hxxp://iiot[.]gmi[.]edu[.]my/search
- iiot[.]gmi[.]edu[.]my points to iiot[.]aimcomsolution[.]com; aimcomsolution[.]com appears in web archives since 2018-08-05 but its current registration is dated 2026-01-20: consistent with a lapsed third-party domain now held by a different party (possible subdomain takeover, unconfirmed)
- Defacement watch: Gambling spam (seen 2026-10-12): terms: gacor, bandar togel, togel, situs toto, situs togel, situs slot
- Landing page is an online gambling page: "YUANTOTO Resmi : Langkah Bermain Slot Toto Gacor & Bandar Togel Online Gampang Menang"

The score is a transparent rule-based sum of the findings above, not an analyst judgment.

## Subdomain takeover check

- **DNS:** `iiot[.]gmi[.]edu[.]my` is a CNAME to `iiot[.]aimcomsolution[.]com`
- **Controlling domain:** `aimcomsolution[.]com` (registrar: NameCheap, Inc.)
- **Current registration:** 2026-01-20
- **Seen in the Wayback Machine since:** 2018-08-05
- **Assessment:** iiot[.]gmi[.]edu[.]my points to iiot[.]aimcomsolution[.]com; aimcomsolution[.]com appears in web archives since 2018-08-05 but its current registration is dated 2026-01-20: consistent with a lapsed third-party domain now held by a different party (possible subdomain takeover, unconfirmed)

## Defacement watch

- **Finding:** Gambling spam, seen 2026-10-12 23:13 UTC from the Fukuro sandbox
- **Page title:** "YUANTOTO Resmi : Langkah Bermain Slot Toto Gacor & Bandar Togel Online Gampang Menang"
- **Detail:** terms: gacor, bandar togel, togel, situs toto, situs togel, situs slot

## Analyst assessment (unconfirmed)

**Possible subdomain takeover of iiot[.]gmi[.]edu[.]my through a lapsed third-party domain (unconfirmed)**

- **Status:** Unconfirmed. Our own research from public sources; not verified with the affected organisation
- **Confidence:** medium

> **Disclaimer:** This assessment is based only on publicly available data (DNS, domain registration records, certificate logs, web archives and what the site served to an automated visitor). It has not been confirmed by the organisations named. It describes a technical situation and does not allege wrongdoing by any organisation or person named here, who may themselves be victims of it. Corrections are welcome.

Public DNS shows iiot[.]gmi[.]edu[.]my as a CNAME to iiot[.]aimcomsolution[.]com. Web archive captures from 2018 to January 2025 show aimcomsolution[.]com as the website of AIMCOM Solution, a Malaysian web design and hosting provider, which suggests the GMI IIoT site was hosted through that provider. Public registration records (RDAP) now show aimcomsolution[.]com with a registration date of 20 January 2026, which is consistent with the domain having lapsed and been registered again by a different party.

Since at least 15 February 2026, iiot[.]gmi[.]edu[.]my has served an Indonesian online gambling page (YUANTOTO, slot and togel). On 13 October 2026 it still did, for desktop and phone visitors alike, under Let's Encrypt certificates issued in July and September 2026 that also name an unrelated domain, miebangla[.]store.

If this reading is correct, the content is controlled by whoever now holds aimcomsolution[.]com, and no system run by GMI needs to have been breached. GMI and AIMCOM Solution would then both be affected parties rather than responsible ones. The most likely window is 20 January to 15 February 2026. This is our own research from public sources and has not been confirmed by GMI or AIMCOM Solution.

| Date | What happened | Source |
| --- | --- | --- |
| 2018-08-05 | aimcomsolution[.]com first archived, AIMCOM Solution company site | Wayback Machine |
| 2024-06-02 | iiot[.]gmi[.]edu[.]my is a normal WordPress site (redirects to its WordPress login) | Wayback Machine |
| 2025-01-07 | aimcomsolution[.]com still the AIMCOM Solution site (web design and hosting) | Wayback Machine |
| 2026-01-20 | aimcomsolution[.]com shows a new registration date (registrar NameCheap) | RDAP |
| 2026-02-15 | Earliest capture of the YUANTOTO gambling page on iiot[.]gmi[.]edu[.]my | Wayback Machine |
| 2026-03-15 | Gambling page still present (title changed) | Wayback Machine |
| 2026-06-18 | Gambling page still present: YUANTOTO Resmi | Wayback Machine |
| 2026-07-23 | Let's Encrypt certificate for iiot[.]gmi[.]edu[.]my, also naming iiot[.]gmi[.]edu[.]my[.]miebangla[.]store | Certificate transparency (CertSpotter) |
| 2026-09-22 | Certificate renewed, same names | Certificate transparency (CertSpotter) |
| 2026-10-13 | Still live for every visitor on desktop and phone; flagged by Fukuro Defacement watch | Fukuro sandbox |

**Other explanations considered**

- The page was put up deliberately, for example as a test, by GMI or its provider. We consider this less likely: it is a functioning commercial gambling page with login and registration buttons, it has been visible for about eight months, and the registration of the provider domain changed shortly before it appeared. Only GMI can rule this out.
- The original provider still holds aimcomsolution[.]com under a new registration. We consider this less likely: the domain now redirects to an unrelated site (enjoymelona[.]com). Only the domain holder can confirm.
- GMI's own servers were compromised. Not supported by what we can see: the subdomain is answered by a third-party server (216[.]194[.]175[.]95) reached through the CNAME, not by GMI infrastructure.

**Recommendations**

1. GMI IT may wish to review the iiot record in the gmi.edu.my DNS zone and remove it, or point it to a server GMI controls, if the IIoT site is no longer in use.
2. GMI IT may also wish to check the zone for other records pointing at third-party domains that may have lapsed.
3. Share with MyCERT (Cyber999) so they can coordinate with GMI.
4. Once resolved, request removal of the gambling pages indexed under iiot[.]gmi[.]edu[.]my from search engines.

_Notes last updated 2026-10-12._

## Where the link goes

| Hop | URL | Result | Server IP |
| --- | --- | --- | --- |
| 1 | `hxxp://iiot[.]gmi[.]edu[.]my/` | HTTP 200 | `216[.]194[.]175[.]95` |

Final destination: `hxxp://iiot[.]gmi[.]edu[.]my/`

## Landing page

- **Title:** YUANTOTO Resmi : Langkah Bermain Slot Toto Gacor & Bandar Togel Online Gampang Menang
- **Password field:** No
- **Forms send data to:** `iiot[.]gmi[.]edu[.]my`

## Page after continue

- **How it was found:** the target of a form on the landing page
- **URL:** `hxxp://iiot[.]gmi[.]edu[.]my/search`
- **Title:** 404 Not Found
- **Password field:** No

## Evidence

![Evidence 1](evidence-1.png)

![Evidence 2](evidence-2.jpg)

## Seen elsewhere

- **VirusTotal** already has a record of it (seen or scanned before). No engine flagged it as malicious at the time of this check.

## Indicators (defanged)

| Type | Value | Use |
| --- | --- | --- |
| url | `hxxp://iiot[.]gmi[.]edu[.]my/` | Block |
| ipv4 | `216[.]194[.]175[.]95` | Context, review first |
| domain | `iiot[.]gmi[.]edu[.]my` | Block |
| url | `hxxp://iiot[.]gmi[.]edu[.]my/search` | Block |
| domain | `iiot[.]aimcomsolution[.]com` | Block |
| domain | `aimcomsolution[.]com` | Block |
| domain | `miebangla[.]store` | Context, review first |

## Recommended actions

1. Keep the message quarantined until an analyst reviews the findings.
2. Detonate the file or open the URL in a sandbox if it has not been analyzed.
3. Search mail logs for other recipients before deciding.
