# Test Results

- **Python version used:** 3.10+
- **Operating system:** Linux
- **Date:** 2026-11-07

| # | Input | Expected result | Actual result | Pass/Fail |
| :-: | :--- | :--- | :--- | :---: |
| 1 | https://www.example.com/login | No listed warning signs | - No listed warning signs found. This does NOT prove safety. | PASS |
| 2 | http://192.0.2.10/account | IP address + HTTP | - Uses an IP address instead of a familiar domain.<br>- Uses HTTP. HTTPS alone does not prove trust. | PASS |
| 3 | http://example.com@sample.invalid/login | @ symbol + HTTP | - Contains an @ symbol; inspect carefully.<br>- Uses HTTP. HTTPS alone does not prove trust. | PASS |
| 4 | https://a.b.c.d.e.example.invalid/path | Many hostname segments | - Contains many hostname segments/subdomains. | PASS |
| 5 | https://xn--example.invalid/ | Punycode-style hostname | - Contains a punycode-style hostname. | PASS |

## Notes
- Testing confirmed that a URL showing zero warnings is not inherently safe[cite: 8, 12].
- Input validation handled malformed strings cleanly without unhandled crashes[cite: 18, 20].
- The interactive loop allowed rapid verification of all test cases in a single session[cite: 19].