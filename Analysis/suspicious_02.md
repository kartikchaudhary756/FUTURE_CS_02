# Email 03 — Suspicious Email Analysis

## Classification

**Risk:** Suspicious

## Sample Description

This sample is a simulated account-security alert email received in Gmail. The email was sent using a fake-mailer tool and claims that suspicious activity has been detected on the recipient's account.

It urges the recipient to verify their account immediately through a link and threatens permanent account lockout if verification is not completed within 24 hours.

## Key Suspicious Indicators

1. **Urgent account-lock warning**
   - The subject claims that the recipient's account will be locked, creating pressure to act quickly.

2. **Generic greeting**
   - The email addresses the recipient as "Dear User" rather than using a specific name.

3. **Suspicious verification link**
   - The message contains a link labelled "Verify Now" that uses the displayed domain `secure-account-verify[.]com`. The actual destination and ownership of the domain have not been independently verified.

4. **Threat of permanent account lockout**
   - The email threatens permanent account lockout within 24 hours to encourage immediate action.

5. **Unverified sender identity**
   - The sender is displayed as `security-alert@fhdfc.com`. The sender's identity and authorization to send the alert have not been independently verified.

6. **Gmail spam classification**
   - Gmail displayed a warning that the message was in Spam because it resembled messages previously identified as spam. This is a warning sign, but it does not independently prove that the email is malicious.

## Attack Explanation

The message uses urgency and fear of account suspension to encourage the recipient to click a verification link.

Possible attack flow:

Unexpected account-security alert  
↓  
Recipient is warned about account suspension  
↓  
Recipient is encouraged to click the verification link  
↓  
The destination could attempt to collect credentials or perform another malicious action

*Note: The final stages describe a possible attack scenario, not confirmed behavior. The link's actual destination has not been verified.*

## Recommended User Action

- Do not click the suspicious link or enter account credentials.
- Verify account-security warnings through the service's official website or application.
- Check the sender and email headers for additional evidence.
- Report the email as phishing or spam according to the applicable policy.
- Avoid forwarding or sharing the suspicious link unnecessarily.

## Evidence

Evidence screenshots:
<img width="1560" height="955" alt="Screenshot 2026-10-11 001300" src="https://github.com/user-attachments/assets/0c22189e-3820-43dc-af17-f94676911c4e" />

## Final Assessment

**Classification: SUSPICIOUS**

The email contains several warning signs, including urgency, a threat of account lockout, a generic greeting, and a verification link whose destination has not been verified. Gmail also classified the message as spam.

The sample was simulated using a fake-mailer tool. The available evidence supports classifying it as suspicious, but the actual behavior of the link and the sender's identity have not been independently confirmed. Therefore, this report does not claim that credential theft or malware delivery occurred.
