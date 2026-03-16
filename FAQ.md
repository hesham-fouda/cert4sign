# Frequently Asked Questions

## General

### What is Cert4Sign?
Cert4Sign is a hosted web tool for generating ZATCA-compliant Certificate Signing Requests (CSRs) and completing the e-invoicing compliance onboarding process.

### Is Cert4Sign authorized by ZATCA?
No. Cert4Sign is an independent tool intended for testing and compliance purposes. Always verify with ZATCA's official documentation.

### Do I need to install anything?
No. Cert4Sign is a web application accessible at [https://cert4sign.com](https://cert4sign.com).

## Security

### Are my private keys stored?
No. Private keys are generated server-side and returned to you in the response. They are not permanently stored. If KV caching is enabled, private keys are redacted from stored data.

### Is it safe to use?
All cryptographic operations use audited, industry-standard libraries. Communication with ZATCA uses HTTPS. No personal data is collected beyond form inputs.

## ZATCA

### What is a CSR?
A Certificate Signing Request (CSR) is a message sent to ZATCA to apply for a digital certificate. It contains your organization details and public key.

### What is a CSID?
A Compliance/Production Certificate Signing ID. It's the digital certificate ZATCA issues to your EGS device for signing invoices.

### What are the 6 test invoices?
ZATCA requires 6 invoice types to be tested for compliance: Standard Invoice, Standard Debit Note, Standard Credit Note, Simplified Invoice, Simplified Debit Note, and Simplified Credit Note.

### Where do I get an OTP?
- **Sandbox**: Use `123345`
- **Simulation**: [ZATCA Simulation Portal](https://fatoora.zatca.gov.sa/simulation)
- **Production**: [ZATCA Production Portal](https://fatoora.zatca.gov.sa)

### What is the difference between Standard and Simplified invoices?
- **Standard (B2B)**: Requires buyer details, cleared by ZATCA before issuance
- **Simplified (B2C)**: No buyer details required, reported to ZATCA after issuance

### What does the Report.txt contain?
The report shows each step of the compliance flow: CSR generation, ZATCA API responses, compliance invoice results, and production certificate details. It matches the format used by ZATCA's official SDKs.
