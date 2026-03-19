# 🔐 Phishing Email Detection & Awareness System

**Cyber Security Task 2 (2026)** · By Hudi Juma Sendoro

A practical analysis of phishing email detection techniques, combining visual inspection with technical email header analysis.

---

## 📌 Overview

Phishing attacks use **social engineering** rather than complex code — tricking users into handing over credentials by impersonating trusted entities (banks, services, employers). This project documents how to identify, classify, and respond to such threats.

---

## 🔍 What's Covered

- **Header Analysis** — Interpreting raw email headers using an analyzer tool to expose spoofed senders and failed authentication checks
- **Phishing Indicator Identification** — Spotting red flags such as mismatched sender domains, urgency tactics, spelling errors, and suspicious URLs
- **Risk Classification** — Assigning a threat level based on SPF, DKIM, and DMARC results
- **Visual Analysis** — Reviewing the email body for social engineering cues (generic greetings, fear-based language, insecure HTTP links)
- **Prevention Guidelines** — Practical Do's and Don'ts for users and employees

---

## 🚩 Key Red Flags Identified (Sample Email)

| Indicator | Finding |
|---|---|
| Mismatched Identity | Claimed `trustedbank.com`, originated from `auth-secure-mail.top` |
| Authentication | SPF, DKIM, and DMARC all **failed** |
| Urgency Tactic | *"Your Account Will Be Locked"* |
| Spelling Errors | "recieved", "discrepency" |
| Insecure URL | `http://` instead of `https://` |
| Generic Greeting | *"Dear valued customer"* instead of user's real name |

---

## ⚠️ Risk Level

> **CRITICAL — Confirmed Phishing Attempt**

---

## 🛡️ Quick Prevention Tips

- **Do** hover over links before clicking to check the real destination
- **Do** navigate to your bank manually by typing the URL yourself
- **Don't** click links in emails demanding urgent action or verification
- **Don't** trust an email just because it displays a familiar logo
- **Don't** reply to suspicious emails — it confirms your address is active

---

## 📄 License

This project was submitted as an academic cybersecurity task. For educational use only.
