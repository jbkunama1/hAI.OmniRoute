<div align="center">

[![Buy me a coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-ffdd00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://www.buymeacoffee.com/highfish)

# 🤖 hAI.OmniRoute

### AI Management Dashboard & Router — Portainer Stack

[![Version](https://img.shields.io/badge/version-1.0.0-blue?style=for-the-badge&logo=docker)](https://github.com/jbkunama1/hAI.OmniRoute)
[![Status](https://img.shields.io/badge/status-active-brightgreen?style=for-the-badge&logo=checkmarx)](https://github.com/jbkunama1/hAI.OmniRoute)
[![License](https://img.shields.io/badge/license-MIT-yellow?style=for-the-badge&logo=opensourceinitiative)](LICENSE)
[![Portainer](https://img.shields.io/badge/Portainer-Ready-13BEF9?style=for-the-bge&logo=portainer)](https://portainer.io)
[![OmniRoute](https://img.shields.io/badge/OmniRoute-Official-764ba2?style=for-the-badge&logo=docker)](https://github.com/diegosouzapw/OmniRoute)

---

```
 ██╗  ██╗ █████╗ ██╗    ██████╗ ██████╗  ██████╗ ██╗   ██╗████████╗███████╗██████╗
 ██║  ██║██╔══██╗██║    ██╔══██╗██╔══██╗██╔═══██╗██║   ██║╚══██╔══╝██╔════╝██╔══██╗
 ███████║███████║██║    ██████╔╝██████╔╝██║   ██║██║   ██║   ██║   █████╗  ██████╔╝
 ██╔══██║██╔══██║██║    ██╔══██╗██╔══██╗██║   ██║██║   ██║   ██║   ██╔══╝  ██╔══██╗
 ██║  ██║██║  ██║██║    ██║  ██║██║  ██║╚██████╔╝╚██████╔╝   ██║   ███████╗██║  ██║
 ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝    ╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝  ╚═════╝    ╚═╝   ╚══════╝╚═╝  ╚═╝
```

**OmniRoute: Zentrales AI-Gateway mit 300+ Providern — Web-UI & API**

[OmniRoute Repo](https://github.com/diegosouzapw/OmniRoute) • [OmniRoute Docs](https://github.com/diegosouzapw/OmniRoute#readme)

</div>

---

## 📋 Inhaltsverzeichnis

- [✨ Was ist OmniRoute?](#-was-ist-omniroute)
- [🎯 Features](#-features)
- [🚀 Schnellstart](#-schnellstart)
- [🐳 Portainer Stack Import](#-portainer-stack-import)
- [🌐 Web-Dashboard](#-web-dashboard)
- [🧪 Healthcheck](#-healthcheck)
- [⚙️ Umgebungsvariablen](#%EF%B8%8F-umgebungsvariablen)

---

## ✨ Was ist OmniRoute?

OmniRoute ist ein freies, MIT-lizenziertes AI-Gateway mit OpenAI-kompatibler API und Web-Dashboard, das dutzende AI-Provider hinter einem Endpoint bündelt.[web:2]

Diese hAI.OmniRoute-Variante verpackt OmniRoute als Portainer-Stack inklusive Healthcheck, Volumes und GHCR-Image-Tagging.

---

## 🎯 Features

- Ein einziger Endpoint für viele AI-Provider (z.B. Claude, GPT, Gemini, DeepSeek).[web:2]
- Web-Dashboard für Konfiguration, Logs und Provider-Status.
- Persistente Konfiguration in `./data` (wird in den Container nach `/app/data` gemountet).
- GHCR-Image `ghcr.io/jbkunama1/hai.omniroute:latest` für einfache Deployments.

---

## 🚀 Schnellstart

```bash
# 1. Repo klonen
 git clone https://github.com/jbkunama1/hAI.OmniRoute.git
 cd hAI.OmniRoute

# 2. Stack starten
 docker compose up -d

# 3. Dashboard öffnen
 http://localhost:20128
```

Standard-Port und Datenverzeichnis:

- Port: `20128` (Dashboard & API)
- Daten: `./data` → `/app/data`

---

## 🐳 Portainer Stack Import

1. Portainer öffnen → **Stacks** → **Add Stack**.
2. **Repository** wählen und URL setzen:
   - `https://github.com/jbkunama1/hAI.OmniRoute`
3. Optional: Umgebungsvariablen (z.B. `TZ`, `INITIAL_PASSWORD`) setzen.
4. Stack deployen.

---

## 🌐 Web-Dashboard

- Default: `http://<HOST-IP>:20128`
- Login / Auth hängt von deiner OmniRoute-Konfiguration ab (`INITIAL_PASSWORD`, JWT etc.).

Weitere OmniRoute-spezifische Einstellungen findest du in der offiziellen README.

---

## 🧪 Healthcheck

Der Container wird per Healthcheck überwacht:

- Prüft regelmäßig `http://localhost:20128`.
- Bei Fehlern versucht Docker automatisch einen Restart.

---

## ⚙️ Umgebungsvariablen

Die wichtigsten Variablen für diesen Stack:

- `ROUTER_PORT`: Externer Port für das Dashboard (Default: `20128`).
- `TZ`: Zeitzone (Default: `Europe/Berlin`).
- `INITIAL_PASSWORD`: Initiales Passwort für OmniRoute (abhängig von deiner OmniRoute-Konfiguration).

Weitere Variablen siehe originale `docker-compose.prod.yml` von OmniRoute.

