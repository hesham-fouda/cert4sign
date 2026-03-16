# Reporting Issues

## Before Reporting

1. Check [[Troubleshooting]] for common errors and fixes
2. Check [[FAQ]] for frequently asked questions
3. Ensure you're using the correct environment and OTP

## How to Report a Bug

Open an issue at: **[https://github.com/hesham-fouda/cert4sign/issues](https://github.com/hesham-fouda/cert4sign/issues)**

Please include:

### Required Information
- **Environment**: Sandbox / Simulation / Production
- **Date & Time** of the issue
- **Browser** and version (e.g., Chrome 120)
- **Exact error message** from the results page or ZATCA response

### Attach Report (sanitized)
1. Download the **Report.txt** from the results page
2. **Remove sensitive data** before sharing:
   - Remove or mask the OTP
   - Remove the Private Key section entirely
   - Remove the Secret Key values
3. Attach the sanitized report to your issue

### Bug Report Template

```
**Description**
Brief description of what went wrong.

**Environment**
- Environment: [Sandbox / Simulation / Production]
- Browser: [e.g., Chrome 120]
- Date/Time: [when the issue occurred]

**Steps to reproduce**
1. Opened cert4sign.com
2. Entered [describe fields]
3. Clicked Generate CSR
4. Got error: [paste error]

**Expected result**
What should have happened.

**Report.txt**
[Attach sanitized report]
```

## Feature Requests

For feature requests, open an issue with the title prefixed by `[Feature]`:

```
**Feature description**
What you'd like to see added.

**Use case**
Why this would be useful.
```

## Security Issues

For security vulnerabilities, email **security@cert4sign.com** directly. Do not create public issues for security concerns.

## Contact

- **Email**: support@cert4sign.com
- **GitHub Issues**: [https://github.com/hesham-fouda/cert4sign/issues](https://github.com/hesham-fouda/cert4sign/issues)
