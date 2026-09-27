# FUTURE_CS_02
# Phishing Email Detection & Awareness System

Security-analyst-style breakdown of 5 phishing/scam email samples: red-flag identification, risk classification (Safe / Suspicious / Phishing), plain-language attack explanations, and an employee Do's & Don'ts checklist.

## Repository Contents

```
├── Phishing_Detection_Awareness_Report.pdf   # Full report
├── samples/                                  # Raw email sample evidence (.txt, links defanged)
│   ├── sample_1_bank_lockout.txt
│   ├── sample_2_prize_winner.txt
│   ├── sample_3_it_helpdesk_reset.txt
│   ├── sample_4_delivery_notification.txt
│   └── sample_5_internal_memo_safe.txt
├── images/                                   # Annotated example screenshots used in the report
│   ├── annotated_phishing_example.png        # Red-flag callouts on a phishing email
│   └── header_analysis_example.png           # Example header-analyzer output (SPF/DKIM)
└── README.md
```

> **Note on the samples:** the 5 emails are illustrative examples modeled on the most common real-world phishing patterns (fake account-lockout alerts, prize/lottery scams, fake IT-helpdesk password resets, fake delivery notices, plus one genuine internal email for contrast). This keeps the repo safe to make public — no real victims, companies, or live malicious links are involved, and every link in the sample files is defanged with `[.]` so it can't be clicked by accident.

## Tools Used

| Tool | Purpose |
|---|---|
| **Manual header & domain inspection** | Compare the visible sender name against the real sending domain. |
| **[Google Admin Toolbox — Messageheader](https://toolbox.googleapps.com/apps/messageheader/)** | Parses raw headers to check SPF/DKIM authentication and trace the delivery path hop-by-hop. |
| **[MxToolbox Email Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)** | Cross-checks header analysis and flags suspicious/blacklisted relay servers. |
| **Browser-based link inspection (no click)** | Reveal a link's real destination (hover / "copy link address") without ever visiting it. |
| **Python (`reportlab`) / PDF** | Compiling the analysis into a clean, client-ready report. |

## Analysis Approach

Each sample was worked through the same steps a security analyst follows:

1. **Collect the sample** — capture the full email, including headers, not just the visible body.
2. **Analyze the headers** — check the real "From" domain and, where available, SPF/DKIM results and the delivery path.
3. **Inspect the sender domain & links** — compare the claimed brand/organization against the actual domain and where links really point.
4. **Identify phishing indicators** — urgency language, generic greetings, mismatched domains, unrealistic offers.
5. **Classify the risk** — **Safe / Suspicious / Phishing**.
6. **Document findings in plain language** — so any employee, not just IT, understands the attack.
7. **Write prevention guidance** — a practical Do's and Don'ts checklist.

### Summary of Findings

| # | Sender Domain | Subject | Risk |
|---|---|---|---|
| 1 | secure-alert-bank[.]com | Account Will Be Locked | 🔴 Phishing |
| 2 | global-rewardcenter-payout[.]net | You Have Won $850,000 | 🔴 Phishing |
| 3 | corp-mail-support[.]com | Password Expires Today | 🔴 Phishing |
| 4 | track-parcel-status[.]info | Parcel is on hold | 🟠 Suspicious |
| 5 | yourcompany.com (internal) | Monthly Town Hall reminder | 🟢 Safe |

Full indicator lists, plain-language explanations, and the annotated example images are in (./Phishing_Detection_Awareness_Report.pdf).

## Prevention Guidelines (Summary)

**Do:** verify the sender's real address, hover over links before clicking, go directly to official sites, verify unusual requests through a second channel, report anything suspicious.

**Don't:** click links/attachments from unexpected emails, enter credentials or payment info via an email link, share personal data because an email asked for it, trust urgency as a sign of legitimacy.

See the full report for the complete Do's & Don'ts checklist and IT/security-team guidelines (SPF/DKIM/DMARC, phishing simulations, reporting workflow).
