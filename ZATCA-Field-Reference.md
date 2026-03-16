# ZATCA Field Reference

## CSR Fields

| Field | Description | Format | Example |
|---|---|---|---|
| Country (C) | ISO country code | 2 letters | `SA` |
| Organization (O) | Company legal name | Arabic or English | `Maximum Speed Tech Supply LTD` |
| Org Unit (OU) | Branch name or TIN | Text | `Riyadh Branch` |
| Common Name (CN) | Auto-set per environment | Template name | `TST-886431145-399999999900003` |
| Tax ID (UID) | VAT registration number | 15 digits, starts/ends with `3` | `399999999900003` |
| Invoice Type | EGS device capability | 4-digit code | `1100` |
| Serial Number (SN) | Device identifier | `1-name\|2-model\|3-uuid` | `1-TST\|2-TST\|3-ed22f1d8-...` |
| Registered Address | Business address | Text | `RRRD2929` |
| Business Category | Industry sector | Text | `Supply activities` |

## Invoice Type Codes

| Code | Description |
|---|---|
| `1100` | Standard + Simplified Invoices |
| `1000` | Standard Invoices Only |
| `0100` | Simplified Invoices Only |

## Tax ID (UID) Validation

- Must be exactly **15 digits**
- Must **start with 3**
- Must **end with 3**
- Example: `3XXXXXXXXXXXXX3`

## Invoice Document Types

| TypeCode | Name | Description |
|---|---|---|
| 388 | Invoice | Sales invoice |
| 383 | Debit Note | Additional charges |
| 381 | Credit Note | Returns/refunds |

## Invoice Type Name Format (7 digits: NNPNESB)

| Position | Meaning | Values |
|---|---|---|
| NN | Invoice category | `01`=Standard, `02`=Simplified |
| P | Third-party | `0`=No, `1`=Yes |
| N | Nominal | `0`=No, `1`=Yes |
| E | Export | `0`=No, `1`=Yes |
| S | Summary | `0`=No, `1`=Yes |
| B | Self-billed | `0`=No, `1`=Yes |

## Payment Methods

| Code | Method |
|---|---|
| 10 | Cash |
| 30 | Credit |
| 42 | Bank transfer |
| 48 | Bank card |
| 1 | Other |

## VAT Categories

| Code | Description | Rate |
|---|---|---|
| S | Standard | 15% |
| Z | Zero-rated | 0% |
| E | Exempt | 0% |
| O | Out of scope | 0% |
