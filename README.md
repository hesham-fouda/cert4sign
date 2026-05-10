# Cert4Sign

An **open-source reference implementation** of the ZATCA Phase 2 e-invoicing onboarding flow for Saudi Arabia &mdash; PKCS#10 CSR generation, Compliance CSID, six required test invoices, and Production CSID.

- **Source**: [github.com/hesham-fouda/cert4sign](https://github.com/hesham-fouda/cert4sign)
- **Documentation site**: [https://cert4sign.com](https://cert4sign.com) *(documentation only &mdash; no hosted tool is offered)*
- **Wiki**: [github.com/hesham-fouda/cert4sign/wiki](https://github.com/hesham-fouda/cert4sign/wiki)

> **Disclaimer**: Cert4Sign is **not affiliated with or authorized by ZATCA**. It is an open-source reference implementation for testing and simulation purposes only. **No hosted service is offered** &mdash; clone the source from GitHub to run the tool locally.

## What It Implements

The codebase covers the complete ZATCA Phase 2 e-invoicing onboarding process:

1. **CSR generation** &mdash; from organization, Tax ID, and EGS device inputs
2. **Compliance Certificate (CCSID) acquisition** &mdash; submitted to ZATCA's compliance API
3. **Compliance testing** &mdash; six test invoices (standard + simplified, plus debit and credit notes) signed and submitted
4. **Production Certificate (PCSID) exchange** &mdash; ready for live invoice reporting and clearance

All cryptographic operations (ECDSA secp256k1, XAdES enveloped signatures, QR codes) are implemented in the codebase.

## Running Locally

Clone the repository and follow the setup instructions in the [Getting Started wiki page](https://github.com/hesham-fouda/cert4sign/wiki/Getting-Started). The codebase is designed to run on Cloudflare Workers, but the core logic is portable.

```sh
git clone https://github.com/hesham-fouda/cert4sign.git
cd cert4sign
# follow Getting Started in the wiki for setup
```

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

- **General**: support@cert4sign.com
- **Security / Responsible Disclosure**: security@cert4sign.com
- **Issues**: [GitHub Issues](https://github.com/hesham-fouda/cert4sign/issues)

## Roadmap

Reference integration helpers (CSR-generation snippets) for **JavaScript / Node**, **PHP**, and **.NET / C#** are on the way. Email [support@cert4sign.com](mailto:support@cert4sign.com) to request a specific stack be prioritized.

## Security &amp; Data Handling (when self-hosted)

The codebase, when run, behaves as follows:

- **Private keys** are generated per request, returned only to the caller, and never written to any database, log, or persistent storage.
- **OTPs** are forwarded directly to ZATCA's official endpoints in the same request and never persisted.
- **ZATCA traffic** goes only to ZATCA's official gateway (`gw-fatoora.zatca.gov.sa`). No third-party intermediaries.
- For security vulnerabilities or responsible disclosure, email [security@cert4sign.com](mailto:security@cert4sign.com).
- For abuse reports, email [support@cert4sign.com](mailto:support@cert4sign.com).

## Disclaimer

Cert4Sign is **not affiliated with or authorized by ZATCA**. It is an open-source reference implementation for testing and simulation purposes only. **No hosted service is offered.** See [Terms of Service](https://github.com/hesham-fouda/cert4sign/wiki/Terms-of-Service) for details.
