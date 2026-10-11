# FUTURE_CS_02 — Phishing Email Detection & Awareness System

**Cyber Security Task 2 — Future Interns Cyber Security Internship**

| | |
|---|---|
| **Prepared by** | Kartik Chaudhary |
| **Assessment date** | 10 October 2026 |
| **Assessment type** | Email security analysis and awareness |
| **Samples analyzed** | 3 email examples |
| **Approach** | Passive / read-only analysis |

**Purpose:** identify common phishing indicators, classify email risk, explain the attack in simple language, and provide practical prevention guidance.

---

## 1. Executive Summary

This assessment analyzes three email examples to demonstrate a practical phishing-awareness workflow. Each sample was reviewed for sender context, visible content, links or attachment lures, brand impersonation, urgency, and available authentication evidence. The samples were classified as Phishing, Safe, or Suspicious.

### Classification Summary

| Email | Classification | Primary evidence |
|---|---|---|
| 01 | **PHISHING** | Account-lock threat with a “Verify Now” link, sent via fake mailer to Gmail |
| 02 | **SAFE** | SPF, DKIM and DMARC passed |
| 03 | **SUSPICIOUS** | Account-suspension alert from an unauthenticated sender with a Verify Account button |

### Key outcome

- Phishing indicators can often be identified without clicking links or opening attachments.
- Authentication results are useful evidence, but passing SPF/DKIM/DMARC does not prove that every link or message intent is safe.
- When evidence is incomplete, the safer analytical approach is to classify the message as Suspicious rather than overstate certainty.

---

## 2. Scope & Methodology

> **Scope:** Three email examples were reviewed for security-awareness purposes. No live malicious links were intentionally visited, no credential submission was attempted, and no attachment was executed.

### Analysis workflow

1. **Collect samples:** two test phishing emails created with a fake mailer and received in Gmail, and a legitimate Internshala email.
2. **Review headers:** inspect sender, Reply-To, authentication results, and mail-flow indicators where available.
3. **Inspect content:** review subject, wording, branding, links, attachments, urgency, and requested action.
4. **Identify indicators:** record observable behaviors without assuming malicious intent when evidence is insufficient.
5. **Classify risk:** Safe, Suspicious, or Phishing.
6. **Document:** explain the attack pattern in simple language and provide prevention guidance.

### Tools / Sources

| Tool / source | Observation | Use |
|---|---|---|
| Fake-mailer test emails | Phishing test emails created with a fake mailer and delivered to Gmail for analysis. | Sample creation and content analysis |
| Email headers | Gmail raw email header data for the legitimate Internshala email sample. | SPF / DKIM / DMARC review |
| Browser / visual inspection | Screenshots and visible email content reviewed without interacting with suspicious links. | Content and lure analysis |
| Report documentation | Markdown analysis notes and this PDF report. | Evidence and awareness output |

> **Safety note:** Defanged or screenshot-based evidence was preferred. Raw recipient addresses, message identifiers, authentication signatures, cookies, and tracking tokens are not reproduced in this report.

---

## 3. Email 01 — Phishing

**Classification: PHISHING**

**Theme:** fake mailer to Gmail; urgent account-lock notification

**Observed lure:** a fake mailer was used to send an email to a Gmail inbox. It imitates a security alert (“Urgent: Your Account Will Be Locked”), claims suspicious activity, and tells the recipient to verify details through a “Verify Now” link within 24 hours.

### Visible indicators

| Indicator | Observation | Risk relevance |
|---|---|---|
| Urgent subject line | The subject “Urgent: Your Account Will Be Locked” pushes the reader to act immediately. | Suspicious |
| Account-lock threat | It warns that failure to verify within 24 hours “will result in permanent account lock”. | High relevance |
| “Verify Now” link | The user is told to verify details through a “Verify Now” link to secure-account-verify\[.\]com (defanged). | High relevance |
| Generic greeting and sender | “Dear User” and a “security team” sender at security-alert@fhdfc.com, with nothing tying it to a known organization. | Suspicious |
| Spoofed sender via fake mailer | The sender identity is forged with a fake mailer rather than sent by a genuine security service. | High relevance |
| Gmail spam placement | Gmail filed it in Spam with an External tag as similar to past spam messages. | Suspicious |

---

## 4. Email 01 — Attack Pattern & Response

![Email 01 — phishing email in the Gmail Spam folder](images/email01_phishing.jpg)

### How the attack works

**Simple explanation:** The attacker uses a fake mailer to send a security-alert style email to the victim's Gmail inbox. It claims suspicious activity, threatens a permanent account lock within 24 hours, and supplies a “Verify Now” link. Such a link would typically lead to a fake sign-in page used to steal credentials or personal details.

### Recommended response

- Do not click the “Verify Now” link.
- Do not enter passwords, OTPs or personal details after following an email link.
- Check the account status by signing in through the official website or app, typed manually or opened from a bookmark, not through the email link.
- Report the message to the security team or mail-reporting process.
- Delete the message after reporting it if organizational policy allows.

> **Evidence source:** Test phishing email sent with a fake mailer to a Gmail inbox for awareness and educational purposes. The screenshot shows it in the Spam folder; the link is shown defanged.

---

## 5. Email 02 — Safe / Legitimate Email

**Classification: SAFE**

**Subject:** Update: Your Google AI Plus access is waiting to be claimed | Confirm your 12-month access at no cost

**Sender:** Internshala \<student@mail.internshala.com\>

The raw email header was reviewed for authentication and message context. The recipient address and raw tokens are intentionally omitted from this report.

### Header authentication evidence

| Indicator | Observation | Risk relevance |
|---|---|---|
| SPF | Pass | Supports authorized sending infrastructure |
| DKIM | Pass | Message was cryptographically signed by the stated sending domains |
| DMARC | Pass | Domain alignment/authentication check passed |

> **Why classified Safe:** The available evidence shows successful SPF, DKIM and DMARC authentication and a recognizable sender domain. No credential, OTP, payment, or account-verification request was observed in the reviewed message.

> **Important limitation:** Authentication passing does not guarantee that every URL in an email is harmless. Users should still verify unexpected links and avoid sharing credentials through email.

---

## 6. Email 03 — Suspicious

**Classification: SUSPICIOUS**

**Theme:** fake mailer to Gmail; generic account-suspension alert

**Observed lure:** the recipient is told the account will be suspended in 24 hours and is asked to click a “Verify Account” button.

![Email 03 — suspicious email in the Gmail Spam folder](images/email03_suspicious.jpg)

### Visible indicators

| Indicator | Observation | Risk relevance |
|---|---|---|
| Urgent subject line | The message is headed “URGENT: Verify Your Account”, pushing the reader to act quickly. | Suspicious |
| Account-suspension threat | It claims the account “will be suspended in 24 hours” to create pressure. | High relevance |
| Click-to-verify action | The email asks the user to “click here to verify your account” using a \[Verify Account\] button. | High relevance |
| Generic, unknown sender | Sent from security-alert@fake-example.com, an address that does not belong to a recognizable organization. | Suspicious |
| Gmail spam warning | Gmail shows “(no subject)”, an External tag and a warning that the message is similar to past spam. | Suspicious |
| Unprofessional layout | The body is a plain-text box drawn with line characters, with no logo, signature or recipient name. | Suspicious |

---

## 7. Email 03 — Analysis & Safe Handling

![Email 03 — Gmail warning that the sender can't be verified](images/email03_gmail_warning.jpg)

### Why it remains Suspicious rather than definitively Phishing

The message shows clear warning signs: an urgent subject, a 24-hour suspension threat, a “Verify Account” button, a generic sender, and a Gmail warning that the message “isn't authenticated and the sender can't be verified”. It is kept as Suspicious rather than Phishing because the body is a plain-text template with no visible working link or attachment, so the sample does not independently show a malicious destination.

### Recommended response

- Do not click the “Verify Account” button or any link in the message.
- Check the account status through the official website or app, typed manually or opened from a bookmark.
- Do not reply to the sender or share personal information.
- Report the message to the security team.
- Use Gmail’s “Report phishing” option and report the message to the security team.

---

## 8. Phishing Prevention & Employee Awareness

> **Remember: STOP — CHECK — VERIFY**
> Stop before clicking. Check the sender, domain, wording, link destination, and requested action. Verify through a trusted channel when the message is unexpected.

### Do

- Check the sender address and domain carefully.
- Be cautious with urgent or unexpected requests.
- Hover over links before clicking, when your mail client allows it.
- Use bookmarks or manually typed official websites for account access.
- Verify unusual requests through a known phone number or internal contact.
- Report suspected phishing to the security team.

### Don't

- Do not enter passwords or OTPs after following an unexpected email link.
- Do not open unexpected attachments.
- Do not trust branding alone; attackers can copy logos and layouts.
- Do not assume HTTPS alone means a website is legitimate.
- Do not forward suspicious messages to colleagues without following organizational reporting procedures.

### Simple employee rule

> **If you did not expect it, verify it before you interact with it.**
> When in doubt, use a trusted route to reach the service instead of the link or attachment provided by the email.

---

## 9. Conclusion & Deliverable Structure

This assessment demonstrates a repeatable phishing-awareness workflow using three contrasting email examples.

The analysis focuses on observable indicators and avoids unsafe interaction with suspicious content.

### Final classification

| Email | Classification | Summary |
|---|---|---|
| Email 01 | Phishing | Account-lock threat with a “Verify Now” link, sent via fake mailer to Gmail |
| Email 02 | Safe | Authenticated Internshala email with SPF, DKIM and DMARC passing |
| Email 03 | Suspicious | Account-suspension alert from an unauthenticated sender; verify button, no working link shown |

### Recommended GitHub repository structure

```text
FUTURE_CS_02/
├── Analysis/
│   ├── Email_01_Phishing.md
│   ├── Email_02_Safe.md
│   └── Email_03_Suspicious.md
├── Emails/
├── Evidence/
│   ├── Email_01_Phishing/
│   └── Email_03_Suspicious/
├── Report/
│   └── FUTURE_CS_02_Phishing_Email_Detection_Awareness_Report.pdf
├── assessment-info.md
└── README.md
```

### Status

> **FINAL REPORT — READY FOR GITHUB / TASK SUBMISSION**
> The PDF is structured as an awareness-focused security analysis. Raw personal addresses, authentication signatures, tracking tokens, and other unnecessary sensitive values are excluded.

### Source note

Email 01 and Email 03 are test phishing emails created with a fake mailer and delivered to a Gmail inbox for awareness purposes. Email 02 is based on a raw Internshala email supplied for analysis.
