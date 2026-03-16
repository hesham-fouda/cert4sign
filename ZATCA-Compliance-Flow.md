# ZATCA Compliance Flow

## Overview

ZATCA (Zakat, Tax and Customs Authority) requires all businesses in Saudi Arabia to implement Phase 2 e-invoicing. This involves a multi-step onboarding process to register your Electronic Generation Solution (EGS) device.

## The 6-Step Process

```
Step 1: Generate CSR + Cryptographic Keys
         |
Step 2: Submit CSR to ZATCA --> Compliance Certificate Issued
         |
Step 3: Build Authorization Credentials
         |
Step 4: Submit 6 Test Invoices for Compliance Validation
         |
Step 5: Request Production Certificate (CSID)
         |
Step 6: Ready for Live Invoice Reporting/Clearance
```

## Step 1: CSR Generation

A Certificate Signing Request (CSR) is generated with your business details including:
- Organization name and branch
- VAT registration number (15 digits, starts/ends with 3)
- Invoice types your device will issue
- Device serial number

**Key type**: ECDSA with secp256k1 curve (ZATCA requirement)

## Step 2: Compliance Certificate

The CSR is submitted to ZATCA's compliance API. On success, ZATCA returns:
- **Compliance Certificate** (binarySecurityToken) - X.509 certificate for signing
- **Secret Key** - API authentication secret
- **Request ID** - Used later for production certificate

## Step 3: Authorization

The compliance certificate and secret are combined into an authorization token used for subsequent API calls.

## Step 4: Compliance Invoice Testing

ZATCA requires 6 test invoices to be signed and submitted:

| # | Invoice Type | Description |
|---|---|---|
| 1 | Standard Invoice | Regular tax invoice (B2B) |
| 2 | Standard Debit Note | Adjustment increasing amount |
| 3 | Standard Credit Note | Return/refund adjustment |
| 4 | Simplified Invoice | Simplified tax invoice (B2C) |
| 5 | Simplified Debit Note | Simplified adjustment |
| 6 | Simplified Credit Note | Simplified return/refund |

Each invoice is digitally signed with XAdES enveloped signatures and includes a QR code.

## Step 5: Production Certificate

After compliance testing passes, the compliance Request ID is exchanged for a **Production Certificate** - the permanent credential for live invoice reporting.

## Step 6: Live Operations

With the production certificate, your EGS can:
- **Clear** standard invoices via `/invoices/clearance/single`
- **Report** simplified invoices via `/invoices/reporting/single`

## ZATCA API Environments

| Environment | Base URL | Purpose |
|---|---|---|
| Sandbox | `gw-fatoora.zatca.gov.sa/e-invoicing/developer-portal` | Development testing |
| Simulation | `gw-fatoora.zatca.gov.sa/e-invoicing/simulation` | Pre-production |
| Production | `gw-fatoora.zatca.gov.sa/e-invoicing/core` | Live invoicing |

## ZATCA Resources

- **Official Guidelines**: https://zatca.gov.sa/en/E-Invoicing/Introduction/Guidelines
- See [[Getting Started]] for portal links and OTP details
