# Incident Response Report - Phishing
A short incident response report derived from a fictious scenario where I must investigate a phishing alert as a SOC analyst. This report was part of the coursework for the Google Cybersecurity Professional Certificate.

### Scenario [excerpt]
You are a level-one security operations center (SOC) analyst at a financial services company. Previously, you received a phishing alert about a suspicious file being downloaded on an employee's computer. After investigating the email attachment file's hash, the attachment has already been verified malicious. Now that you have this information, you must follow your organization's process to complete your investigation and resolve the alert.

## Evaluation
* Alert Severity: Medium - there is a risk of compromise as the user that received the email may have opened the attachment.
* Sender Details: The sender's name on the email is "Def Communications," however the email address itself looks significantly different from this name ("76tguyhh6tgftrt7tg.su"). This may indicate that the sender is attempting to impersonate Def Communications to pose as a trusted entity.
* Message Body: Contains grammatical errors are littered throughout the message body, thus pointing to this email being less legitimate and more likely to be a phishing email. Additionally, the sender also had typos in the subject line as well.
* Attachments: There are no links in the email but there is a password protected attachment included as part of the email. The email claims that the attachment is a resume and cover letter. The hash of the attached file (54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b) has been marked as malicious by 57 vendors as malicious on <a href = "https://www.virustotal.com/gui/file/54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b/summary">VirusTotal</a> indicating this attachment is malicious.

## Nature of the Incident
* Cause: The sender impersonating Def Communications; likey a malicious actor
* What occurred: The malicious actor sent a phishing email to the HR department masquerading as a job applicant. The malicious actor also attached a malicious file that they claimed was their resume and cover letter. In reality, this was a malicious file and appears to be a Trojan of some kind.
* When: This email was received on July 20, 2022 at 9:30 AM. 

## Conclusion
Since the malicious file was likely opened on a company computer on the company network, it would be prudent to escalate this ticket to a level-two SOC analyst to take further action. The infected system may need to be quarantined and re-imaged, and further scans may need to occur to better understand the scope of compromise to the sytems and network at Inergy.
