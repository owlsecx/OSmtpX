# 🦉 OSmtpX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-ONetwork-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
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

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OSmtpX --help   # watch every network call
firejail --net=none ./OSmtpX --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
