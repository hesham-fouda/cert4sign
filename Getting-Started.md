# Getting Started

## What is Cert4Sign?

Cert4Sign is a hosted web tool that helps businesses generate ZATCA-compliant Certificate Signing Requests (CSRs) and complete the full e-invoicing compliance onboarding process required by Saudi Arabia's ZATCA authority.

**Access the tool at**: [https://cert4sign.com](https://cert4sign.com)

## How to Use

### Step 1 - Subject Information
Enter your organization details:
- **Country**: `SA` (Saudi Arabia)
- **Organization**: Your company legal name
- **Organizational Unit**: Branch name or department

### Step 2 - ZATCA Taxpayer Details
- **Tax ID (UID)**: Your 15-digit VAT registration number (must start and end with `3`)
- **Invoice Type**: Choose which invoice types your EGS device will issue
- **Registered Address**: Your business address
- **Business Category**: Your industry sector

### Step 3 - EGS Device Details
- **Device Name**: Name of your e-invoicing solution
- **Device Model**: Model identifier
- Serial number and UUID are auto-generated

### Step 4 - Environment & OTP
- **Environment**: Select Sandbox, Simulation, or Production
- **OTP**: Enter the One-Time Password

### Step 5 - Review & Confirm
Review all entered information and confirm.

### Step 6 - Results
View and download:
- Certificate Signing Request (CSR)
- Private Key
- ZATCA Compliance Certificate
- Secret Key
- Full Report (matching ZATCA SDK report format)

## Environments & OTPs

| Environment | When to Use | OTP Source |
|---|---|---|
| **Sandbox** | Initial testing and development | `123345` (fixed test OTP) |
| **Simulation** | Pre-production testing | [ZATCA Simulation Portal](https://fatoora.zatca.gov.sa/simulation) |
| **Production** | Live e-invoicing | [ZATCA Production Portal](https://fatoora.zatca.gov.sa) |

## What Happens Behind the Scenes

When you click "Generate CSR", Cert4Sign:
1. Generates an ECDSA secp256k1 key pair
2. Builds a PKCS#10 CSR with ZATCA-required extensions
3. Submits to ZATCA's compliance API
4. Generates and submits 6 test invoices for compliance
5. Obtains your Production CSID
6. Provides a full report with all certificates and keys
