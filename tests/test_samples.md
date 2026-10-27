# Test Results

Python version used: 3.13 | Operating system: Windows 11 | Date: 28 October 2026

| # | Input | Expected result | Actual result | Pass/Fail |
|---|-------|-----------------|---------------|-----------|
| 1 | https://www.example.com/login | No listed warning signs | No listed warning signs found. This does NOT prove safety. | PASS |
| 2 | http://192.0.2.10/account | IP address + HTTP | Uses an IP address; Uses HTTP | PASS |
| 3 | http://example.com@sample.invalid/login | @ symbol + HTTP | Contains an @ symbol; Uses HTTP | PASS |
| 4 | https://a.b.c.d.e.example.invalid/path | Many hostname segments | Contains many hostname segments/subdomains | PASS |
| 5 | `https://xn--example.invalid/` | Punycode-style hostname | Contains a punycode-style hostname | PASS |


## Notes

I learned that a phishing link can look normal but give itself away through small clues, like an @ symbol, an IP address instead of a name, or a strange xn-- hostname.
I was surprised that a link with no warning signs can still be dangerous, so "no warnings" does not mean "safe".
My tool only reads the URL text and never opens the link, which keeps testing safe.