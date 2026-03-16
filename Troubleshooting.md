# Troubleshooting

## ZATCA API Errors

### `Invalid Request`
**Cause**: The sandbox (developer-portal) endpoint may be temporarily unavailable.
**Fix**: Try again later. ZATCA's sandbox has intermittent availability issues.

### `Invalid-CSR` / "The provided Certificate Signing Request (CSR) is invalid."
**Possible causes**:
- **Invalid OTP**: Simulation and production require a real OTP from the ZATCA Fatoora portal. Test OTPs only work for sandbox.
- **Expired OTP**: OTPs have a limited validity period. Generate a new one from the portal.
- **Wrong environment**: Ensure you selected the correct environment matching your OTP source.

### `invalid-invoice-hash`
**Cause**: The invoice hash sent to ZATCA doesn't match what ZATCA computes from the XML.
**Fix**: Please report this via [GitHub Issues](https://github.com/hesham-fouda/cert4sign/issues) with your Report.txt (remove sensitive data).

### `QRCODE_INVALID`
**Cause**: QR code validation failed for simplified invoices.
**Fix**: Report via [GitHub Issues](https://github.com/hesham-fouda/cert4sign/issues).

### `BR-KSA-15` - Missing supply date
**Cause**: Standard invoices require a delivery/supply date.
**Fix**: This is handled automatically. If you see this error, report it.

### `BR-KSA-17` - Missing reason for debit/credit note
**Cause**: Debit and credit notes require a reason and billing reference.
**Fix**: Handled automatically. Report if you see this error.

### `BR-KSA-EN16931-06` - Charge indicator error
**Cause**: Price-level charge indicator must be `false`.
**Fix**: Handled automatically. Report if you see this error.

## OTP Issues

| OTP Value | Sandbox Result |
|---|---|
| `123345` | Valid (success) |
| `111111` | Invalid |
| `222222` | Expired |

**Simulation/Production**: OTPs must be obtained from the ZATCA Fatoora portal. See [[Getting Started]] for links.

## Form Issues

### "Fill Sample Data" button not working
Ensure you're not in production mode. The button is hidden when production is selected.

### Tax ID validation fails
Tax ID must be exactly 15 digits, starting and ending with `3`. Example: `399999999900003`.

## Still Having Issues?

1. Download the **Report.txt** from the results page
2. Remove any sensitive data (OTP, private keys)
3. Open an issue at [https://github.com/hesham-fouda/cert4sign/issues](https://github.com/hesham-fouda/cert4sign/issues)
4. Attach the sanitized report
