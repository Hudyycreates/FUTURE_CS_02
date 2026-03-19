# 📧 Phishing Email Detection & Awareness System — Full Analysis

**Cyber Security Task 2 (2026)** · By Hudi Juma Sendoro

---

## 📖 Overview

Phishing is a **digital trap** where a criminal pretends to be someone you trust — like your bank, Netflix, or even your boss — to trick you into giving up private information. Instead of "hacking" your computer with complex code, they use **social engineering** to hack your emotions.

By sending an urgent email or text claiming your "account is locked" or "money is missing," they hope you will panic and click a link. That link leads to a **fake website** that looks exactly like the real one. When you "log in" to fix the problem, you are actually typing your username and password directly into the criminal's hands.

> It is much easier for a thief to trick a person into handing over their keys than it is to break down a digital vault door.

---

## 🛠️ Header Analysis

The following raw email header was analysed using a Header Analyzer Tool:

```
Delivered-To: employee@company.com
Received: from mail-gateway.attacker-server.net (unknown [192.0.2.1])
        by mx.google.com with ESMTPS id z62si4321915wmb.22.2026.03.19.10.45.00
        for <employee@company.com>;
        Thu, 19 Mar 2026 10:45:00 -0700 (PDT)
Return-Path: <support-verification@auth-secure-mail.top>
From: "TrustedBank Security" <alerts@trustedbank.com>
Subject: Urgent: Your Account Will Be Locked
Date: Thu, 19 Mar 2026 10:44:55 -0700
Message-ID: <550e8400-e29b-41d4-a716-446655440000@mail.com>
Authentication-Results: mx.google.com;
        spf=fail (google.com: domain of support-verification@auth-secure-mail.top
             does not designate 192.0.2.1 as permitted sender)
        dkim=none;
        dmarc=fail (p=REJECT) action=none header.from=trustedbank.com
Content-Type: text/html; charset="UTF-8"
```

### Delivery Information

| Check | Result |
|---|---|
| DMARC Compliant | ❌ No DMARC Record Found |
| SPF Alignment | ❌ Failed |
| SPF Authenticated | ❌ Failed |
| DKIM Alignment | ❌ Failed |
| DKIM Authenticated | ❌ Failed |

---

##  Visual Analysis — The Phishing Email

The email visually impersonated **TrustedBank** with the following body:

> *Dear valued customer of TrustedBank,*
>
> *We have recieved notice that you have recently attempted to withdraw the following amount from your checking account while in another country: \$135.25.*
>
> *If this information is not correct, someone unknown may have access to your account. As a safety measure, please visit our website via the link below to verify your personal information:*
>
> `http://www.trustedbank.com/general/custverifyinfo.asp`
>
> *Once you have done this, our fraud department will work to resolve this discrepency. We are happy you have chosen us to do business with.*
>
> *Thank you,*
> *TrustedBank*

---

## 🚩 Phishing Indicators (Red Flags)

| Indicator | Specific Finding | Explanation |
|---|---|---|
| **Mismatched Identity** | Claims to be `trustedbank.com`, Return-Path is `auth-secure-mail.top` | The real sending server is hidden behind a fake display name |
| **Generic Greeting** | "Dear valued customer of TrustedBank" | Real banks address you by your legal name |
| **Spelling Errors** | "recieved", "discrepency" | Professional institutions use spell-checkers and editors |
| **Fear & Urgency** | "someone unknown may have access to your account" | Attackers use fear to make you act quickly without thinking |
| **Suspicious URL** | `http://` instead of `https://` | A real bank would never handle personal information over an unencrypted connection |
| **Authentication Failure** | SPF, DKIM, and DMARC all failed | Digital proof that the sender is an impostor |

---

## ⚠️ Risk Classification

| Field | Detail |
|---|---|
| **Risk Level** |  CRITICAL — Phishing |
| **Reasoning** | Failed all three major security protocols (SPF, DKIM, DMARC). Uses a deceptive link and generic greeting to steal credentials. |

---

## ⚙️ How the Attack Works

This attack uses **Social Engineering** to bypass technical security:

1. **The Hook** — The attacker creates a fake "problem" (a \$135.25 withdrawal) to cause panic
2. **The Bait** — They offer a "solution" (the link) that appears to go to the bank's website
3. **The Catch** — The user is sent to a fake site that mirrors the real bank; entering credentials hands them directly to the attacker in real-time

---

##  Prevention Guidelines

###  Do's
- **Inspect the Sender** — Check the actual email address behind the display name
- **Use the Hover Test** — Hover your mouse over any link to see its real destination in the browser's bottom-left corner
- **Go to the Source** — Open a new tab and type the bank's address manually (e.g. `www.yourbank.com`) or use their official app

### Don'ts
- **Don't Click** — Never click links in emails asking for "verification" of personal or financial data
- **Don't Reply** — Replying confirms your address is active, inviting more attacks
- **Don't Trust Logos** — Attackers can easily copy high-quality logos from the internet
- **Don't Download** — Never open attachments or enter passwords on pages linked from an email

---

## 📋 Final Assessment

This email is a **high-risk phishing attempt**. Even though the link text looks legitimate (`trustedbank.com`), the hidden destination in a real attack would typically be a look-alike domain (e.g. `trusted-bank-security.net`). The combination of spelling errors, failed authentication, fear tactics, and an insecure HTTP link makes this a textbook phishing case — easy to spot for a trained user, but dangerous for anyone unaware of the signs.

---

*Submitted as part of Cyber Security Task 2 · 2026*
This project was submitted as an academic cybersecurity task. For educational use only.
