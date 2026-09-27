# FUTURE_CS_02
# Phishing Detection & Awareness Report — Task 2

Analysis of five email samples to identify phishing/spam indicators, classify risk, and produce prevention guidelines for end users and organizations.

## Repository Contents

```
├── Phishing_Detection_Awareness_Report.pdf   # Full report (analysis, indicators, risk table, prevention guidelines)
├── samples/                                  # Raw email sample evidence (5 samples)
└── README.md
```

## Dataset

The 5 email samples analyzed are drawn from the **CEAS 2008 Spam/Phishing Challenge corpus** (`gvc.ceas-challenge.cc`), a public research dataset used for spam/phishing classification benchmarking.

## Tools Used

| Tool | Purpose |
|---|---|
| **Manual header inspection** | Reviewing `From`, `To`, `Date`, and display-name fields for sender/domain mismatches. |
| **[Google Admin Toolbox — Messageheader](https://toolbox.googleapps.com/apps/main/)** | Parsing raw email headers to check **SPF** and **DKIM** authentication results and trace the full hop-by-hop delivery path (relay servers, per-hop delay, protocol, timestamps). |
| **Domain/URL review** | Comparing embedded links and sender domains against the claimed sender/brand to spot redirects to unrelated or free-hosting domains. |
| **Python (`reportlab`)** | Used to compile the findings into the final formatted PDF report. |

## Analysis Approach

Each of the 5 samples was evaluated across four dimensions:

1. **Sender / Header Analysis** — Does the display name match the actual sending domain? Is the domain plausible for the claimed sender? Cross-checked with Google Admin Toolbox for SPF/DKIM pass/fail and any unexplained relay hops.
2. **Link / URL Analysis** — Are embedded links pointing to the sender's own domain, or redirected through unrelated/free-hosting domains?
3. **Content Analysis** — Does the subject/body use urgency, unrealistic offers, brand impersonation, or obfuscated/filter-evasion text?
4. **Behavioral / Social-Engineering Pattern** — What persuasion technique is being used (discount lure, brand trust exploitation, filter-evasion noise, counterfeit goods, etc.)?

Based on these four dimensions, each email was assigned a **risk classification** — Low, Medium, Medium-High, or High — combining the degree of technical deception (domain spoofing, redirect links, failed authentication) with the potential harm (credential theft, malware delivery, financial fraud).

### Summary of Findings

| # | Sender | Type | Risk |
|---|---|---|---|
| 1 | Gretchen Suggs (loanofficertool.com) | Phishing / malicious redirect | High |
| 2 | Caroline Aragon (thaidomainnames.com) | Spam with filter-evasion obfuscation | Medium-High |
| 3 | Replica Watches (thebakercompanies.com) | Counterfeit-goods scam | Medium |
| 4 | Daily Top 10 (tcwpg.com) | Brand impersonation phishing | High |
| 5 | Apache Bugzilla (issues.apache.org) | Legitimate (ham) — control example | Low |

Full details, indicators, and the SPF/DKIM/delivery-path check for each sample are in (./Phishing_Detection_Awareness_Report.pdf).

## Prevention Guidelines (Summary)

**For end users:** verify the real sending address (not just display name), never click links in unsolicited email, be wary of urgency or "too good to be true" offers, watch for obfuscated/garbled text, and report suspicious emails to IT/security.

**For organizations:** enforce SPF/DKIM/DMARC, deploy layered spam/phishing filtering with link sandboxing, maintain domain/URL reputation blocklists, run phishing-simulation training, and provide an easy internal reporting process.

See the full report for the complete list of consolidated indicators and detailed guidelines.

