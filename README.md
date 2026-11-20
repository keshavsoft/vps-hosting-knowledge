# VPS Cloud Hosting Knowledge Base

[![GitHub Pages](https://img.shields.io/badge/docs-GitHub_Pages-blue?style=flat-square)](https://keshavsoft.github.io/vps-hosting-knowledge/)
[![KeshavSoft](https://img.shields.io/badge/org-KeshavSoft-purple?style=flat-square)](https://github.com/keshavsoft)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg?style=flat-square)](LICENSE)

> **The Master Unified VPS Cloud Hosting Handbook for the KeshavSoft Fleet:**  
> Connecting GoDaddy DNS, Caddy Front-Door Ingress Gateway, and native Ubuntu Systemd Backend Daemons.

---

## 📖 Live Master Handbook

Read the full interactive visual handbook with search, dark/light theme, and scroll-spy navigation:  
👉 **[https://keshavsoft.github.io/vps-hosting-knowledge/](https://keshavsoft.github.io/vps-hosting-knowledge/)**

---

## 🌓 The Two Halves of Cloud Hosting

```
[ Inbound HTTPS Requests :443 ]
               │
               ▼
┌──────────────────────────────┐
│     THE FRONT-DOOR GATEWAY   │  Managed by: caddy-cli, caddy-subdomain, caddy-fileserver
│      Caddy Reverse Proxy     │  Handbook: https://keshavsoft.github.io/caddy-knowledge/
│    (SSL Termination & TLS)   │
└──────────────┬───────────────┘
               │  Internal Ports (:3000..:9328)
               ▼
┌──────────────────────────────┐
│     THE BACKEND ENGINE       │  Managed by: ubuntu-service-cli
│   Native Systemd Daemons     │  Handbook: https://keshavsoft.github.io/ubuntu-knowledge/
│   (Auto-restart, Boot, Logs) │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│       Node.js Applications   │  Working Directory: /root/KeshavSoft/<app>
│  (appointment, quotation...) │
└──────────────────────────────┘
```

---

## 🧭 The 3-Stage VPS Subdomain Maturity Model

1. **Stage 1: Flight Check (Zero Disk / Zero Code)**
   ```bash
   npx caddy-subdomain probe call.keshavsoft.com
   ```
2. **Stage 2: Static File Server (Real Disk I/O)**
   ```bash
   npx caddy-fileserver init call.keshavsoft.com
   ```
3. **Stage 3: Full Dynamic Application (Process Supervisor + Reverse Proxy)**
   ```bash
   # Manage systemd service:
   npx ubuntu-service-cli check appointment.keshavsoft.com
   # Promote Caddy route:
   npx caddy-subdomain add appointment.keshavsoft.com 3000
   ```

---

## 📚 Sister Knowledge Bases

- **[Caddy Knowledge Base](https://keshavsoft.github.io/caddy-knowledge/)**: Deep-dive on Caddy JSON AST blueprints, reverse proxying, subdomains, static routes, and TLS automation.
- **[Ubuntu Knowledge Base](https://keshavsoft.github.io/ubuntu-knowledge/)**: Master reference for native Linux systemd daemons, internal port ranges, crash recovery, and `ubuntu-service-cli`.

---

## 📄 License

ISC &copy; KeshavSoft
