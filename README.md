<p align="center">
  <img src="assets/header.png" alt="Zafkiel Arcade Header" width="100%"/>
</p>

<h1 align="center">Zafkiel Arcade</h1>
<p align="center">
  <strong>Dark Gothic & Time-Manipulating Survival Game Engine</strong>
</p>

<p align="center">
  <a href="https://zafkiel-arcade.curzy.dev"><strong>🌐 Live Demo Website</strong></a>
</p>

<div align="center">

[![Stars](https://img.shields.io/github/stars/Curzyori/zafkiel-arcade?style=for-the-badge&color=crimson)](https://github.com/Curzyori/zafkiel-arcade/stargazers)
[![Forks](https://img.shields.io/github/forks/Curzyori/zafkiel-arcade?style=for-the-badge&color=crimson)](https://github.com/Curzyori/zafkiel-arcade/network/members)
[![License](https://img.shields.io/badge/License-MIT-gold?style=for-the-badge)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20Linux-black?style=for-the-badge)](#)

</div>

<p align="center">
  <a href="#-why-zafkiel-arcade">Why Zafkiel</a> ·
  <a href="#-key-features">Features</a> ·
  <a href="#%EF%B8%8F-architecture">Architecture</a> ·
  <a href="#-quick-start">Quick Start</a> ·
  <a href="#-security--logging">Security</a>
</p>

---

## 🕒 Why Zafkiel Arcade?

**Zafkiel Arcade** is a high-stakes, time-manipulating survival game inspired by the aesthetic of *Kurumi Tokisaki*. Unlike standard arcade clones, Zafkiel integrates a full **Modular Monolith** backend to track highscores, enforce zero-trust inputs, and stream real-time temporal state.

|                               |                                                              |
| ----------------------------- | ------------------------------------------------------------ |
| 🕒 **Time-Manipulating Play** | Use REWIND, FREEZE, ACCEL, and COLLECT skills to survive.     |
| 🔒 **Zero-Trust Logic**       | Every game event and payload is validated via Zod schemas.  |
| 📊 **Real-time Persistence**  | High-performance SQLite database tracks highscores & logs.    |
| 👹 **Aggressive Scaling**     | Dynamic difficulty algorithms increase anomaly spawn rates. |
| 🛡️ **Hardened Security**       | Rate-limiting, CORS locks, and secure session management.    |

---

## 🎯 Key Features

### Game Mechanics

| Skill / Mechanic | Status | Description |
| :--- | :---: | :--- |
| **HP Drain (-1/s)** | ✅ | Constant depletion of *Time Essence*. Collect stars to live. |
| **REWIND (🕒)** | ✅ | Reverse player trajectory to escape traps or reposition. |
| **FREEZE (❄️)** | ✅ | Freeze all enemies temporarily to plan strategic moves. |
| **ACCEL (⚡)** | ✅ | Speed up game-loop speed to harvest resource stars quickly. |
| **COLLECT (🌌)** | ✅ | Massive black-hole gravitational pull on nearby essence stars. |
| **Rift Scaling** | ✅ | Enemy speeds and spawn frequencies ramp up over survival time. |

### Technical Capabilities

| Capability | Status | Description |
| :--- | :---: | :--- |
| **Modular Monolith** | ✅ | express.js v5 modular routing keeping logic compartmentalized. |
| **Native DB Bindings** | ✅ | Native `better-sqlite3` bindings for lightning-fast IO execution. |
| **Winston Auditor** | ✅ | Audit-trail pipeline capturing every action to persistent JSON. |
| **Zod API Schema** | ✅ | Strict type-enforcement on incoming requests to prevent cheats. |
| **Docker Packaging** | ✅ | Multi-stage Docker config ready to run on any VPS. |

---

## 🏗️ Architecture

The codebase separates the layout engine (Frontend UI) from temporal persistence (Backend API) while sharing core validation utilities:

```text
zafkiel-arcade/
├── core/
│   └── engine.js          # Time-manipulation mathematical rulesets & tick rate
├── interface/
│   ├── api/               # Express backend controllers, security middleware
│   └── web/               # React SPA client bundle (Vite + Tailwind CSS)
├── utils/
│   ├── validation.js      # Zero-trust validation rule files
│   ├── logger.js          # Winston logger instance (Temporal log outputs)
│   └── errors.js          # Global HTTP exception interceptors
├── assets/                # Creative graphics, icons & theme audio files
├── arcade.db              # Active local SQLite binary database
└── vercel.json            # Vercel deployment instructions
```

---

## 🚀 Quick Start

### Option A: Local Development

```bash
# Clone the repository
git clone https://github.com/Curzyori/zafkiel-arcade.git
cd zafkiel-arcade

# Install production and development dependencies
npm install

# Rebuild native better-sqlite3 drivers (Crucial for Linux platform)
npm rebuild better-sqlite3

# Create environment variable lock
cp .env.example .env

# Run hot-reload backend + Vite client
npm run dev
```

### Option B: Docker Container

```bash
# Build and package app stack
docker build -t zafkiel-arcade .

# Start container instances mapping live ports
docker run -d -p 3000:3000 --name zafkiel-instance zafkiel-arcade
```

---

## 🔒 Security & Logging

### Temporal Audit Trails
Zafkiel records every major database change, highscore submission, and cheat anomaly detected directly to standard outputs and `/error.log` via the Winston engine:
```json
{"level":"info","message":"Temporal rewound executed successfully","timestamp":"2026-06-20T11:45:00Z"}
```

### Input Hardening
Any client attempting to tamper with coordinates or simulate score updates will be blocked at the network gate. The server enforces a strong schema matching client structure using the Zod engine.

---

## 📄 License
This project is released under the **MIT License** — free for educational, personal, and research purposes.

<sub>Built with passion as the 1st Project of the 50 Projects Challenge by **@curzyori**</sub>
