# EWB Phishing URL Awareness Checker

## Overview
Phishing is a social engineering attack where malicious actors use deceptive links to trick victims into disclosing sensitive credentials, session tokens, or personal data. The EWB Phishing URL Awareness Checker is a Python security utility designed to inspect the visible plaintext structure of a URL for common structural anomalies without ever connecting to or resolving the web address.

## Features
- Detects the presence of an `@` symbol (often used to disguise the true destination domain).
- Flags long URLs (exceeding 100 characters).
- Flags hostnames formatted as raw IP addresses rather than registered domain names.
- Identifies deeply nested subdomains (5 or more hostname labels).
- Identifies Punycode notation (`xn--`) used in IDN homograph attacks.
- Flags unencrypted HTTP connections.
- **Improvement A:** Interactive command-line loop enabling continuous analysis without program restarts.
- **Improvement B:** Summary banner highlighting the exact count of flagged indicators.
- **Improvement C:** Exception handling for malformed bracketed URL inputs preventing system crashes.

## Requirements
Python 3.10 or later. Built with standard libraries (`re`, `urllib.parse`). No third-party packages required.

## How to Run
```bash
python3 phishing_checker.py