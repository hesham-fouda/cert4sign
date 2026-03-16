# Cert4Sign

Generate ZATCA-compliant Certificate Signing Requests (CSRs) and complete the full e-invoicing compliance onboarding — directly from your browser.

**Live App**: [https://cert4sign.com](https://cert4sign.com)

## What It Does

Cert4Sign walks you through the complete ZATCA Phase 2 e-invoicing onboarding process:

1. **Generate CSR** — with your organization, Tax ID, and EGS device details
2. **Obtain Compliance Certificate** — submitted automatically to ZATCA's API
3. **Run Compliance Tests** — 6 test invoices (standard + simplified) signed and submitted
4. **Get Production Certificate** — ready for live invoice reporting and clearance

All cryptographic operations (ECDSA secp256k1, XAdES signing, QR codes) are handled for you.

## Environments

| Environment | OTP | Portal |
|---|---|---|
| Sandbox | `123345` (fixed) | Developer testing |
| Simulation | [ZATCA Simulation Portal](https://fatoora.zatca.gov.sa/simulation) | Pre-production |
| Production | [ZATCA Production Portal](https://fatoora.zatca.gov.sa) | Live invoicing |

## Documentation

Full documentation is available in the [Wiki](https://github.com/hesham-fouda/cert4sign/wiki):

- [Getting Started](https://github.com/hesham-fouda/cert4sign/wiki/Getting-Started)
- [ZATCA Compliance Flow](https://github.com/hesham-fouda/cert4sign/wiki/ZATCA-Compliance-Flow)
- [ZATCA Field Reference](https://github.com/hesham-fouda/cert4sign/wiki/ZATCA-Field-Reference)
- [Troubleshooting](https://github.com/hesham-fouda/cert4sign/wiki/Troubleshooting)
- [FAQ](https://github.com/hesham-fouda/cert4sign/wiki/FAQ)

## Support

- **Email**: support@cert4sign.com
- **Issues**: [GitHub Issues](https://github.com/hesham-fouda/cert4sign/issues)
- **Security**: security@cert4sign.com

## Disclaimer

Cert4Sign is **not authorized by ZATCA**. It is an independent tool for testing, simulation, and compliance onboarding. See [Terms of Service](https://github.com/hesham-fouda/cert4sign/wiki/Terms-of-Service) for details.
