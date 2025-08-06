# Task 2 – Phishing Email Analysis (Cyber Security Internship)

## 🎯 Objective:
Identify phishing characteristics in a suspicious email sample and analyze the email header to detect signs of spoofing or social engineering.

---

## 🛠 Tools Used:
- MXToolbox Email Header Analyzer
- Text editor for .eml file
- Browser (to inspect URLs)

---

## 📩 Sample Email Details:

| *Indicator* | *Description* |
|---------------|------------------|
| *Spoofed Email Address* | amaz0n-support.com looks similar to amazon.com but uses a "0" instead of an "o". |
| *Suspicious URL* | Link text shows amazon but redirects to verify-account-secure.com, a fake domain. |
| *Urgent Language* | Phrases like "Immediate Action Required", "Account Locked", "Respond within 24 hours" used to create urgency. |
| *Attachment Type* | .docm file (can contain malicious macros). |
| *Generic Greeting* | Uses "Dear Customer" instead of the user's actual name. |
| *Grammar & Tone* | Awkward grammar and sentence structure designed to cause panic. |

---

## 🧪 Email Header Analysis:

- *Return-Path*: <alert@amaz0n-support.com>
- *Received From*: mail.fakehosting.ru (185.244.25.92)
- *Authentication-Results*: dkim=fail, spf=fail, dmarc=fail

### Key Findings:

| *Header Check* | *Result* | *Explanation* |
|------------------|------------|------------------|
| *SPF* | ❌ Fail | IP 185.244.25.92 is *not authorized* to send mail on behalf of amaz0n-support.com. |
| *DKIM* | ❌ Fail | DKIM signature *not verified*, common in spoofed emails. |
| *DMARC* | ❌ Fail | Fails *domain policy* check. |
| *Return Path Mismatch* | ✅ | Return path doesn't match sender domain – *red flag*. |
| *Origin Server IP* | 185.244.25.92 | Not owned by Amazon – linked to *known spam host*. |

---

## 🧾 Conclusion:

This email is a clear *phishing attempt* that uses:

- A *spoofed domain*
- *Social engineering techniques* (urgency & fear)
- *Malicious attachment*
- And *technical red flags* from header analysis

The email fails *SPF, **DKIM, and **DMARC* checks and originates from a *suspicious IP address*.  
Users are advised *not to click any links or open attachments, and report the email **immediately*.

---

### ✅ Performed By:  
*Rushikesh Mahendra Girase*  
Cyber Security Intern – Elevate Labs
