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

Offline SMTP/MTA configuration auditor (Postfix, Exim, OpenSMTPD, Sendmail)

---

## ✨ Features

- Offline, read-only audit of mail transfer agent configuration files — nothing is sent on the wire
- Postfix main.cf parser (continuations, $param expansion, documented defaults) + master.cf service parser with per-service "-o" override awareness
- Exim parser — main options, macros, host/domain lists, ACL statement engine, authenticators; plus Debian update-exim4.conf.conf (dc_*) and conf.d trees
- OpenSMTPD smtpd.conf parser — macros, tables, pki, listen directives, actions and match rules (new and legacy accept/reject syntax)
- Sendmail .mc (m4 FEATURE/define) and .cf (O options) excerpt parser + access-map relay review
- Open-relay engine: mynetworks / relay_from_hosts / dc_relay_nets CIDR breadth, restriction-list order, unconditional ACL accepts, "match from any for any"
- VRFY/EXPN, STARTTLS, protocol & cipher strength, plaintext AUTH, HELO/sender policy, soft_bounce, permit_mx_backup, banner disclosure, limits
- Credential sweep — world-readable sasl_passwd maps, sasldb2, OpenSMTPD secrets, Exim passwd.client, referenced TLS private keys, hardcoded passwords
- 70+ rules mapped to CWE + MITRE ATT&CK with severity and concrete remediation
- Score + grade, severity filter, CI gate (--fail-on)
- Export TXT / Markdown / JSON / CSV / SARIF 2.1.0
- Hardened reference snippets per MTA
- Built-in self-test (--demo) with weak + hardened sets
- Interactive menu and full CLI mode

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OSmtpX
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
