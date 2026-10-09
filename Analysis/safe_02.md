# Email 02 — Safe Email Analysis

## Classification

**Risk:** Safe / Legitimate

## Sample Description

This sample is an email received from Internshala and was analyzed using the email headers available in Gmail.

**Sender:** Internshala `<student@mail.internshala.com>`

**Subject:** Update: Your Google AI Plus access is waiting to be claimed | Confirm your 12-month access at no cost

The email appears to be a notification related to an offer or access provided through Internshala.

## Header Analysis

The email header shows successful authentication results:

- **SPF:** PASS
- **DKIM:** PASS
- **DMARC:** PASS

The sender domain shown in the authentication results is `mail.internshala.com`.

The SPF, DKIM and DMARC results indicate that the email passed the standard email authentication checks for the sending domain.

## Phishing Indicator Analysis

| Indicator | Finding |
|---|---|
| Sender domain | `mail.internshala.com` |
| SPF | Pass |
| DKIM | Pass |
| DMARC | Pass |
| Sender authentication | Successfully authenticated |
| Unexpected credential request | Not observed in the available evidence |
| Payment request | Not observed in the available evidence |
| Password/OTP request | Not observed in the available evidence |
| Urgent account warning | Not observed |
| Suspicious sender domain | Not indicated by the header evidence |

## Why It Is Classified as Safe

The available email header shows that SPF, DKIM and DMARC authentication all passed.

The sender address uses the `mail.internshala.com` domain, and the authentication results are associated with that domain.

No password, OTP, payment or account-lock request is visible in the available evidence.

Based on the available header and message information, the email is classified as **Safe / Legitimate** for this analysis.

However, successful SPF, DKIM and DMARC authentication does not guarantee that every link or piece of content in an email is safe. Links and the actual email content should still be verified before interacting with them.

## Recommended User Action

- Verify that the sender domain is expected.
- Check the destination of links before clicking them.
- Do not provide passwords or OTPs through unexpected links.
- Use the official Internshala website or application if verification is required.
- Report the message if later analysis reveals suspicious links or content.

## Evidence

### Email Header Screenshot

<img width="1140" height="872" alt="Internshala email header showing SPF, DKIM, and DMARC authentication results" src="https://github.com/user-attachments/assets/aab96706-e667-4295-a376-8a3a986cad05" />

The screenshot shows the original message details and the SPF, DKIM and DMARC authentication results.

## Final Assessment

**Classification: SAFE / LEGITIMATE**

The email is classified as safe for this analysis because the available header evidence shows successful SPF, DKIM and DMARC authentication, and no obvious credential, payment, OTP or account-lock request is visible in the available evidence.

Authentication results alone are not sufficient to guarantee complete safety, so links and message content should still be verified before interaction.
