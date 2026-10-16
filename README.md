# 🦉 ONextcloudX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OWeb-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **ONextcloudX** — Nextcloud / ownCloud Configuration Hardening Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

Nextcloud / ownCloud configuration hardening auditor (offline, read-only)

---

## ✨ Features

- Safe PHP array-literal tokenizer / parser for config/config.php and config/*.config.php — the PHP file is NEVER executed or included
- occ config:list --private JSON (secrets masked) and occ app:list (JSON or text) import
- Core — debug, trusted_domains, overwriteprotocol, trusted_proxies, brute-force / rate-limit protection, SSRF (allow_local_remote_servers), integrity check, app store source, web updater, maintenance, EOL
- Secrets — secret / passwordsalt / dbpassword / mail_smtppassword / redis password strength (masked)
- Data directory placement inside webroot, permissions, .ocdata, deny .htaccess; config.php 0640 check
- Sharing policy — link passwords, expiry, public upload, share-by-mail, enumeration; 2FA enforcement
- Risky apps — files_external local storage, workflow_script, impersonate, missing admin_audit
- Export TXT / Markdown / JSON / CSV / SARIF 2.1.0
- Self-test --demo, CI gates --fail-on / --min-severity

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./ONextcloudX
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
