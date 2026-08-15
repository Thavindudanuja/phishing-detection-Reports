# Phishing Detection Reports

A hands-on SOC analyst portfolio project analyzing real-world phishing emails to
practice email header forensics, malicious URL investigation, and phishing
indicator documentation — skills directly used in Tier 1 SOC phishing triage.

## What this project covers

- **Email header analysis** — tracing sender authentication (SPF/DKIM/DMARC),
  Return-Path mismatches, and originating infrastructure
- **Payload decoding** — extracting and decoding base64-encoded HTML bodies
  to identify hidden links
- **URL & infrastructure investigation** — using URLScan.io to check redirect
  chains, TLS certificate issue dates, domain lifecycle, and cloud-hosting
  abuse (e.g. Azure Static Websites)
- **Threat classification** — distinguishing credential-harvesting phishing,
  engagement/reconnaissance phishing, cloud-hosted redirect attacks, and
  unsolicited spam that isn't phishing at all

## Tools used

- **Google Admin Toolbox (Messageheader)** — header parsing and authentication results
- **MXToolbox** — header cross-checking and IP/ASN lookups
- **CyberChef** — decoding base64-encoded email bodies
- **URLScan.io** — URL/domain scanning, screenshot capture, redirect tracing

## Samples analyzed

| Sample | Type | Key Technique Identified |
|---|---|---|
| [Sample 01](./Sample%2001) | Credential phishing | Bank/loyalty-program impersonation, scanner cloaking, domain lifecycle (active → parked) |
| [Sample 02](./Sample%2002) | Engagement-harvesting phishing | Mailto-based "actions" instead of a fake login page, tracking pixel |
| [Sample 03](./Sample%2003) | Spam (not phishing) | Unauthenticated bulk marketing via legitimate affiliate ad-tracker |
| [Sample 04](./Sample%2004) | PDF/cloud-hosting redirect | Full-page invisible link in a PDF, abuse of Azure static hosting |

Each report documents header findings, URL/infrastructure analysis, identified
social engineering tactics, red flags, and a final verdict with confidence level,
following a consistent [analysis template](./phishing-analysis-template.md).

## Indicator guide

A one-page decision tree and indicator checklist compiled from these findings
is available in [phishing-indicators-guide.md](./phishing-indicators-guide.md).

## Author

Thavindu — 4th-year BSc (Hons) IT undergraduate specializing in Cyber Security,
ISC² Certified in Cybersecurity (CC), building toward a SOC Analyst (L1) role.
