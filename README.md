# 🦉 ONextcloudX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OWeb-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **ONextcloudX** — Nextcloud / ownCloud Configuration Hardening Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

ONextcloudX is an offline, read-only Nextcloud / ownCloud configuration hardening auditor. It safely tokenizes `config.php` (never executes PHP), imports `occ config:list` / `occ app:list` outputs, and reviews trusted domains, secrets, data-dir placement, sharing policy, 2FA, and risky apps. Scope is application config only; reports export to TXT, Markdown, JSON, CSV, or SARIF.

---

## ✨ Features

- Safe PHP array-literal parser for config.php / *.config.php (never executed or included)
- Import of `occ config:list --private` JSON and `occ app:list` (JSON or text)
- Core checks: debug, trusted_domains, overwriteprotocol, trusted_proxies, brute-force, SSRF, integrity, updater, EOL
- Secrets strength (masked): secret, passwordsalt, dbpassword, mail_smtppassword, redis password
- Data-directory placement/permissions, sharing policy, 2FA enforcement, risky apps (files_external, workflow_script, impersonate)
- Multi-format export, templates, `--demo` self-test, and CI severity gates

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./ONextcloudX -i /var/www/nextcloud --scan
./ONextcloudX -c config.php --occ-config occ.json -f sarif -o nc.sarif
./ONextcloudX --demo --fail-on high
./ONextcloudX --help
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
sudo strace -f -e trace=network ./ONextcloudX --help   # watch every network call
firejail --net=none ./ONextcloudX --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
