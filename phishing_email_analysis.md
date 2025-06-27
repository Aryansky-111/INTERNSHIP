
# Phishing Email Analysis: “TrustWallet APP <mailsender@beteltecnologia.com>”

**Executive Summary:** This email is a sophisticated phishing attempt masquerading as a TrustWallet alert. The headers show that **SPF, DKIM, and DMARC all pass** for the domain *beteltecnologia.com*, meaning the message was legitimately sent by that domain (as defined by RFC 7208). However, *beteltecnologia.com* is not TrustWallet’s official domain, and the content uses urgent, threatening language and mismatched URLs to trick users. The body warns that the user’s wallet will be “frozen” unless they **“Verify Your Wallet”** via suspicious links. Third-party analysis flags the tracking URL as malicious. The attack likely aims to steal credentials (seed phrases or private keys) by redirecting victims to a fake site. TrustWallet’s own guidance warns that phishing emails often create urgency or threats and will never ask for private keys or login info via email. In short, this is a credential-phishing scam that leverages a display name spoof, fear tactics, and obfuscated links.

## 1. Email Headers (SPF/DKIM/DMARC)

The raw headers show **Authentication-Results** with `spf=pass`, `dkim=pass`, and `dmarc=pass` for `beteltecnologia.com`. SPF (as defined in RFC 7208) confirms the sending IP was authorized by the domain’s SPF record. DKIM passed with header.d=beteltecnologia.com, and DMARC passed with policy *p=none*. Because *all* checks passed, the receiving server treated the message as legitimately from *beteltecnologia.com*. **However,** this only confirms the source domain is authentic – not that it’s a legitimate or trustworthy sender.

## 2. Email Content (Plaintext and HTML)

The email body warns the user: **“If you don't complete the wallet verification, your wallet will be restricted, and your assets will be frozen.”** It urges immediate action with a suspicious URL. The Reply-To is a Hotmail address, not corporate. The HTML content includes broken formatting, mixed language templates, and irrelevant links — all hallmarks of phishing.

## 3. Malicious Intent Indicators

- **Impersonation:** Uses the name “TrustWallet APP” but sends from beteltecnologia.com.
- **Urgency/Threats:** Pressure to act quickly or risk losing funds.
- **Suspicious Links:** Uses a redirector (link.beteltecnologia.com) and another suspicious domain (catalog.yampi.io).
- **Credential Theft:** Likely attempts to trick users into entering wallet seed phrases.

## 4. URL Inspection

- `http://link.beteltecnologia.com/...` — flagged by security tools as malicious.
- `https://trustwallet-apps.catalog.yampi.io/` — not a TrustWallet domain, likely used for phishing.

## 5. Attack Scenario Summary

This email is a phishing scam intended to collect TrustWallet user credentials by mimicking a compliance alert. By using real domains under the attacker’s control (with valid SPF/DKIM), it bypasses spam filters. Users are pressured to click links and share sensitive info.

## 6. Standards & References

- RFC 7208 (SPF): https://datatracker.ietf.org/doc/html/rfc7208
- RFC 7489 (DMARC): https://datatracker.ietf.org/doc/html/rfc7489
- TrustWallet security: https://trustwallet.com/blog/phishing-attacks
- Microsoft security tips: https://support.microsoft.com/en-us/windows/how-to-protect-yourself-from-phishing-0c7ea947-ba98-3bd8-8710-73288dfd6b0b
- ANY.RUN threat report: https://analyzer.sublime.security/?id=b79d6d1d-c5f1-4dfa-b423-8176c48f2d12

## 7. Recommendations

- **Do not click** suspicious links or verify wallets via email.
- **Report and delete** the email.
- **Verify URLs** by hovering before clicking.
- **Never share** wallet seed phrases via email.
- **Educate users** on phishing red flags.
- **Use MFA** and trusted wallets with offline key storage.

---

*Prepared by: [Your Name or Team] – IT Security Intern | Date: June 2025*
