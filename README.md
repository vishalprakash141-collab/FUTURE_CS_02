# FUTURE_CS_02
# Phishing Email Detection & Awareness Report

**Future Interns – Cyber Security Task 2 (2026)**

A security-analyst style study of five emails: four real phishing samples and one legitimate email. The report identifies phishing indicators, classifies each email's risk, explains each attack in plain language, and gives prevention guidance and Do's and Don'ts for employees.

## Repository contents

| Path | Description |
|---|---|
| `Phishing_Detection_Awareness_Report.docx` | Final report (also export to PDF) |
| `evidence/` | Header-analysis screenshots for each email and the list of sample files used |
| `samples/` | Add the analysed `.eml` files here (see note below) |

## Results at a glance

| # | Email | Classification |
|---|---|---|
| 1 | Fake Bradesco / Livelo rewards alert | Phishing (High) |
| 2 | Fake Microsoft "unusual sign-in" alert | Phishing (High) |
| 3 | Unsolicited solar-panel offer | Suspicious (Medium) |
| 4 | "Donation For You" advance-fee scam | Phishing (High) |
| 5 | Google Community Team newsletter (own mailbox) | Safe (Low) |

## Tools used

- **Google Admin Toolbox – Messageheader** for decoding headers and SPF/DKIM/DMARC results
- **phishing_pot** (GitHub, study only) as the source of real phishing samples
- An email client for safely viewing `.eml` files
- Microsoft Word / PDF for the report

## Analysis approach

1. Collect sample emails (`.eml`).
2. Extract and decode headers with the header analyzer.
3. Inspect the sender: display name vs. address vs. domain.
4. Check SPF, DKIM and DMARC results.
5. Trace the "Received" path and timestamps for anomalies.
6. List phishing indicators (urgency, mismatched or look-alike domains, bulk delivery, etc.).
7. Classify as **Safe / Suspicious / Phishing**.
8. Write plain-language explanations and prevention guidelines.

All analysis was passive: no links were clicked and no attachments were opened.

## Notes

- Phishing samples come from [rf-peixoto/phishing_pot](https://github.com/rf-peixoto/phishing_pot) and are used for learning only. Credit belongs to the original repository.
- The personal email address in the safe sample was redacted. Do the same in the screenshot before publishing.
