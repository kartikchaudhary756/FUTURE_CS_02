# FUTURE_CS_02 — Phishing Email Detection & Awareness System

## Future Interns Cyber Security Internship — Task 2

This project analyzes email samples to identify common phishing indicators,
classify email risk, explain phishing attacks in simple language, and provide
security-awareness guidance for users.

---

## Objective

- Analyze phishing email samples
- Identify common phishing indicators
- Inspect sender, domains, links, attachments, and email headers where available
- Classify emails as Safe, Suspicious, or Phishing
- Explain phishing attacks in simple language
- Create practical prevention and awareness guidelines

---

## Scope

This assessment was performed for security-awareness and educational purposes.

The analysis used passive/read-only inspection of email content and available
header information.

No malicious links were intentionally clicked, no credentials were submitted,
and no suspicious attachments were executed.

---

## Email Samples Analyzed

Email 01 and Email 03 are test phishing emails created with a fake mailer and
sent to a Gmail inbox for awareness and educational purposes. Email 02 is a
legitimate email received from Internshala.

| Email | Classification | Main Indicators |
|---|---|---|
| Email 01 | Phishing | Urgent account-lock threat with a "Verify Now" link, sent via fake mailer to Gmail |
| Email 02 | Safe | SPF, DKIM and DMARC passed; recognizable sender domain |
| Email 03 | Suspicious | Account-suspension alert from an unauthenticated sender with a "Verify Account" button and no working link shown |

---

## Methodology

1. Collect email samples (two fake-mailer test emails received in Gmail and one legitimate email)
2. Review available email headers
3. Inspect sender and domain information
4. Review links and requested actions
5. Identify phishing indicators
6. Classify email risk
7. Document findings
8. Create prevention and awareness guidelines

---

## Tools & Sources

- Fake mailer (used to create and send the test phishing emails to Gmail)
- Gmail (inbox/spam view and raw email header data)
- Email header analysis (SPF / DKIM / DMARC)
- Browser-based visual inspection
- Markdown documentation
- PDF reporting

All three samples were received in the author's own Gmail account.
Recipient addresses, message identifiers, authentication signatures and
tracking tokens are not reproduced.

---

## Key Findings

### Email 01 — Phishing

Subject: "Urgent: Your Account Will Be Locked"
Sender: security team \<security-alert@fhdfc.com\>

The message was sent with a fake mailer. It imitates a security alert, claims
suspicious activity on the account, and tells the recipient to verify their
details through a "Verify Now" link within 24 hours. The link is shown
defanged in this project.

Key indicators include:

- Urgent subject line
- Account-lock threat ("permanent account lock" within 24 hours)
- "Verify Now" link asking the user to verify details
- Generic greeting ("Dear User") and generic "security team" sender
- Sender identity forged with a fake mailer
- Gmail placed the message in Spam with an External tag

**Classification: Phishing**

---

### Email 02 — Safe

Sender: Internshala \<student@mail.internshala.com\>
Subject: "Update: Your Google AI Plus access is waiting to be claimed | Confirm your 12-month access at no cost"

The message was reviewed using its available raw email headers.

Authentication results:

- SPF — Pass
- DKIM — Pass
- DMARC — Pass

The message came from a recognizable sender domain and did not request
passwords, OTPs, or payments.

**Classification: Safe**

Passing email authentication does not guarantee that every URL in a message
is harmless, so users should still verify unexpected links.

---

### Email 03 — Suspicious

Subject: "URGENT: Verify Your Account"
Sender: security-alert@fake-example.com

The message was sent with a fake mailer. It states that the account will be
suspended in 24 hours and asks the recipient to click a "Verify Account"
button. Gmail displayed a warning that the message "isn't authenticated and
the sender can't be verified".

Key indicators include:

- Urgent subject line
- Account-suspension threat (24 hours)
- Click-to-verify action ("Verify Account" button)
- Generic, unknown sender
- Gmail spam / unauthenticated-sender warning
- Unprofessional plain-text layout with no logo, signature or recipient name

The body is a plain-text template with no visible working link or attachment,
so the sample does not independently show a malicious destination. For that
reason the message is classified as Suspicious.

**Classification: Suspicious**

---

## Phishing Prevention

### Do

- Check the sender address and domain
- Be cautious with unexpected or urgent requests
- Verify unusual requests through a trusted channel
- Use official websites instead of email links when possible
- Report suspicious emails to the security team
- Use Gmail's "Report phishing" option

### Don't

- Do not enter passwords or OTPs through unexpected email links
- Do not click "Verify" buttons or links in unexpected emails
- Do not trust branding alone
- Do not assume HTTPS alone proves legitimacy
- Do not ignore suspicious email behavior

---

## Repository Structure

```text
FUTURE_CS_02/
│
├── Analysis/
│   ├── phishing_02.md        # Email 01 — Phishing
│   ├── safe_02.md            # Email 02 — Safe
│   └── suspicious_02.md      # Email 03 — Suspicious
│
├── Emails/
│   └── emails_02
│
├── Evidence/
│   ├── Email_01_phishing/
│   └── Email_02_suspicious/  # screenshots for the Suspicious sample
│
├── Report/
│   ├── Future_CS_02_email_report
│   └── assessment.md
│
├── README.md
└── assessment.md
```
