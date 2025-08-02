# Email-Header-Analysis
Analyzing an email header to identify potential security threats, specifically phishing attempts

# Email Header Analysis Project
This project serves as a practical example and a guide for analyzing an email header to identify potential security threats, specifically phishing attempts. By examining key fields within the header, we can determine the email's authenticity, its origin, and any inconsistencies that may indicate malicious intent.

The analysis is based on a real email header provided for a training registration.

The Analysis: A Case Study
The following points summarize the investigation of the provided email header.

1. Sender and Recipient Information
From: Olubunmi Alabi <Info.cyber@cyberasquare.com>

To: Bunmi .Alabi <bunmialabi77@gmail.com>

Bcc: kechacarl@gmail.com

Observation: The email was BCC'd to the user's email address. While this isn't a direct sign of phishing, it can sometimes be a red flag in targeted attacks. In this case, it appears to be part of a legitimate mailing list.

2. Technical Authentication Records
The email was evaluated using standard email authentication protocols to verify its legitimacy.

DKIM (DomainKeys Identified Mail):

Status: Pass

Finding: The DKIM signature passed validation, confirming that the email's content and headers were not altered in transit and originated from the specified domain (cyberasquare-com.20230601.gappssmtp.com). This is a strong indicator of legitimacy.

SPF (Sender Policy Framework):

Status: Neutral

Finding: The SPF record for the sending domain returned a "neutral" result. This means the server receiving the email could not definitively permit or deny the sending IP address. While a "Pass" is ideal, "Neutral" is not an outright "Fail" and is often seen in legitimate mailing setups.

DMARC (Domain-based Message Authentication, Reporting, and Conformance):

Status: Pass

Finding: The DMARC check passed, which aligns with the DKIM pass. This indicates the email conforms to the sender's security policy.

3. URL and Content
The email's content includes a registration link and a training ID.

Registration URL: https://attendee.gototraining.com/r/7735109830231082240

Observation: The domain gototraining.com is a known and legitimate service for online training. The URL itself does not appear to be malicious after analyzing with VirusTotal and Scamalytics.

Conclusion and Project Context
Based on the comprehensive header analysis, the email is likely not a phishing attempt. The passing DKIM and DMARC records provide strong evidence of the email's authenticity, and the associated URL points to a legitimate service. The SPF's "Neutral" status is a minor detail that does not override the other positive authentication results in this context.

This project can be used to demonstrate how to perform such an analysis. Future additions could include:

A user interface to paste email headers for automated analysis.

More detailed explanations of DKIM, SPF, and DMARC.

A collection of example headers from both legitimate and phishing emails for comparison.

Disclaimer
This analysis provides a basic overview of email header security. For a professional or in-depth security audit, more sophisticated tools and expertise are required. Always exercise caution and verify unexpected requests through trusted channels.