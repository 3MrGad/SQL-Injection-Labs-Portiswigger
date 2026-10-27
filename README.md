# PortSwigger SQL Injection Labs — Solution Scripts

Python solution scripts for the [PortSwigger Web Security Academy](https://portswigger.net/web-security/sql-injection)
blind SQL injection labs. Each script automates data extraction from a lab's
injection point so I didn't have to walk the characters by hand.

> These target PortSwigger's intentionally vulnerable lab instances. The lab
> URLs and cookies in the scripts are per-session and expire — replace them with
> your own when you launch the lab.

## Scripts

| File | Lab | Technique |
|------|-----|-----------|
| `Blind SQL injection with conditional responses` | [Conditional responses](https://portswigger.net/web-security/sql-injection/blind/lab-conditional-responses) | Boolean-based; detects success by a marker string in the response. |
| `Blind SQL injection with conditional errors` | [Conditional errors](https://portswigger.net/web-security/sql-injection/blind/lab-conditional-errors) | Error-based (Oracle); triggers a divide-by-zero on a true condition. |

Both extract the `administrator` password one character at a time via
`SUBSTRING`/`SUBSTR`.

## Usage

1. Launch the lab and copy your `session` cookie and `TrackingId` prefix into the script.
2. Run it:

```bash
python3 "Blind SQL injection with conditional responses"
```

## Where this went next

These one-off scripts are what the generalised blind-SQLi extractor
[blindsqli](https://github.com/3MrGad/blindsqli) grew out of — same idea, but
with binary search, multiple DBMS dialects and an auto-calibrating oracle.
