# 🦉 OSmtpX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-ONetwork-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OSmtpX** — Offline SMTP / MTA Config Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview


OSmtpX is an offline, read-only SMTP/MTA configuration auditor for Postfix, Exim, OpenSMTPD and Sendmail — nothing is ever sent on the wire. It parses main.cf/master.cf, Exim ACLs, smtpd.conf and sendmail .mc/.cf files, then evaluates open-relay exposure, TLS/AUTH policy, VRFY/EXPN, and world-readable credential maps. Over 70 rules mapped to CWE and MITRE ATT&CK feed a graded report exportable as TXT, Markdown, JSON, CSV or SARIF.

---

## ✨ Features


- Postfix main.cf/master.cf parsing with continuations, $param expansion and per-service -o overrides
- Exim ACL engine, OpenSMTPD smtpd.conf and Sendmail .mc/.cf plus access-map relay review
- Open-relay engine: mynetworks / relay_from_hosts CIDR breadth, restriction order, unconditional accepts
- VRFY/EXPN, STARTTLS, cipher strength, plaintext AUTH, HELO/sender policy and banner-disclosure checks
- Credential sweep for world-readable sasl_passwd, sasldb2, OpenSMTPD secrets and referenced TLS keys
- 70+ CWE/ATT&CK-mapped rules, score+grade, hardened templates and TXT/MD/JSON/CSV/SARIF export

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage


```bash
./OSmtpX --root / --format sarif -o smtp.sarif
./OSmtpX --main-cf /etc/postfix/main.cf --master-cf /etc/postfix/master.cf
./OSmtpX --scan --fail-on high --min-severity medium
./OSmtpX --demo
./OSmtpX --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
