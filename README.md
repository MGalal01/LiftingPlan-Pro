# 🏗️ LiftPlan Pro — LEEA Lifting Operations Portal

> **A professional, LOLER-compliant lifting plan management system built for Appointed Persons, Riggers, and Lifting Engineers.**

![LEEA Compliant](https://img.shields.io/badge/LEEA-Compliant-F5C300?style=for-the-badge&labelColor=1B2A4A)
![LOLER 1998](https://img.shields.io/badge/LOLER_1998-Compliant-2ECC71?style=for-the-badge&labelColor=1B2A4A)
![BS 7121](https://img.shields.io/badge/BS_7121-Referenced-22d3ee?style=for-the-badge&labelColor=1B2A4A)
![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&labelColor=1B2A4A)
![Claude AI](https://img.shields.io/badge/Claude_AI-Powered-F5C300?style=for-the-badge&labelColor=1B2A4A)

---

## 📸 Overview

LiftPlan Pro is a full-stack React application that combines an 8-step lifting plan wizard with a LEEA technical reference library and an AI-powered crane data sheet analyser. Built to the standards that Appointed Persons and lifting engineers work to every day.

| Module | Description |
|--------|-------------|
| 📋 **Lifting Plan Wizard** | 8-step LOLER-compliant plan builder with digital sign-off |
| 🏗️ **Crane Database** | 7 crane models with interpolated load chart calculator |
| ⛓️ **Accessories Library** | LEEA SWL tables — wire rope, chain, webbing, shackles, eyebolts, hooks |
| 📐 **Load Calculator** | Real-time sling tension & utilisation with live SVG diagram |
| 🤖 **AI Crane Analyser** | Upload any crane data sheet (PDF/image) — Claude AI extracts all specs |

---

## ✨ Features

### Lifting Plan Wizard
- **Step 1 — Project & Site**: Name, date, client, weather monitoring with live wind-speed alerts (38 km/h threshold)
- **Step 2 — Personnel**: AP, Operator (CPCS), Riggers, Banksman with certification tracking
- **Step 3 — Load Details**: Weight, dimensions, CoG with SVG load diagram
- **Step 4 — Equipment**: Crane selection from database, interpolated load chart table, rigging gear selector
- **Step 5 — Lift Zone**: SVG site visualiser, exclusion zone, ground bearing, lift path
- **Step 6 — Risk Assessment**: 5×5 risk matrix, 8-hazard register with initial/residual scoring
- **Step 7 — Method Statement**: Sequenced lift steps, comms protocol, abort criteria
- **Step 8 — Sign-Off**: Collapsible review, digital signature blocks

### Live Sidebar Widgets (always visible)
- ⚖️ **Capacity Calculator** — slider-based radius vs SWL with % utilisation
- 🌤️ **Weather Status** — wind flag (OK / Monitor / SUSPEND)
- 📐 **Sling Angle Visualiser** — interactive de-rating diagram
- ✅ **Pre-Lift Checklist** — 14-point LEEA checklist with progress bar

### LEEA Accessories Library
Full SWL tables for:
- Wire Rope Slings — EN 13414-1 (6×19 IWRC, 6×36 IWRC, Grade 1770)
- Chain Slings — EN818-4 (Grade 8 & Grade 10)
- Webbing Slings — EN1492-1 Flat & EN1492-2 Round
- Shackles — EN13889 Bow & Dee (Grade S)
- Eye Bolts — BS4278 Collar & DIN580 Plain
- Lifting Hooks — EN1677-1 Swivel & Clevis (Grade 8)

### AI Crane Data Sheet Analyser
- Drag-and-drop PDF or image upload
- Powered by **Anthropic Claude claude-sonnet-4-20250514**
- Extracts: SWL, span, lift height, speeds, duty cycle, voltage, safety devices, certifications
- Renders SWL vs radius chart automatically

---

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- An [Anthropic API key](https://console.anthropic.com/) (for the AI crane analyser)

### Installation

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/liftplan-pro.git
cd liftplan-pro

# Install dependencies
npm install

# Add your Anthropic API key
cp .env.example .env
# Edit .env and add: VITE_ANTHROPIC_API_KEY=your_key_here

# Start the development server
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

### Build for Production

```bash
npm run build
npm run preview
```

---

## 🏗️ Crane Database

Currently loaded models:

| Crane | Type | Max SWL | Configs |
|-------|------|---------|---------|
| Liebherr LTM 1500-8.1 | Mobile | 500T | 3 |
| Liebherr LTM 1300-6.2 | Mobile | 300T | 2 |
| Liebherr LTM 1100-5.2 | Mobile | 100T | 2 |
| Liebherr LTM 1090-4.2 | Mobile | 90T  | 3 |
| Demag AC 50-1          | Mobile | 50T  | 3 |
| Demag AC 300-6         | Mobile | 300T | 2 |
| Demag AC 700-9         | Mobile | 700T | 1 |
| Liebherr LG 1750       | Lattice | 750T | 1 |

> **Note:** All load chart data is sourced from manufacturer published literature. Always verify against the actual crane's load chart on site before use.

---

## 📐 Standards Referenced

| Standard | Description |
|----------|-------------|
| **LOLER 1998** | Lifting Operations and Lifting Equipment Regulations |
| **BS 7121** | Code of Practice for Safe Use of Cranes |
| **EN 13414-1** | Wire Rope Sling Safety |
| **EN 818-2/4** | Short Link Chain & Chain Slings |
| **EN 1492-1/2** | Textile Slings (Flat Webbing & Round) |
| **EN 13889** | Forged Steel Shackles |
| **BS 4278** | Eyebolts for Lifting Purposes |
| **EN 1677-1** | Components for Slings — Forged Steel Hooks |
| **PUWER 1998** | Provision and Use of Work Equipment Regulations |

---

## 🗂️ Project Structure

```
liftplan-pro/
├── src/
│   └── LiftPlanPro_Merged.jsx   # Main application (single-file React)
├── index.html
├── vite.config.js
├── package.json
├── .env.example
└── README.md
```

---

## ⚙️ Tech Stack

- **Framework**: React 18 with hooks
- **Build Tool**: Vite
- **Styling**: Pure CSS-in-JS (no Tailwind dependency)
- **Fonts**: Barlow Condensed (display) · Barlow (body) · JetBrains Mono (data)
- **AI**: Anthropic Claude API (`claude-sonnet-4-20250514`)
- **Charts**: Custom SVG — no chart library dependency

---

## 🤝 Contributing

Contributions from the lifting engineering community are very welcome. Areas where help would be especially valuable:

- **Crane database expansion** — additional models with verified load chart data
- **Standards updates** — EN/BS standard revisions
- **PDF export** — generate a print-ready LOLER-compliant PDF from the plan preview
- **Multi-language support** — Arabic, French, German (for international sites)
- **Offline mode** — service worker / PWA for use on remote sites without connectivity

### How to contribute

```bash
# Fork the repo, then:
git checkout -b feature/your-feature-name
git commit -m "feat: add Liebherr LTM 1750 load chart"
git push origin feature/your-feature-name
# Open a Pull Request
```

Please ensure any load chart data you add includes the manufacturer source.

---

## ⚠️ Disclaimer

This application is provided as a **technical reference and planning aid only**. All lifting operations must be:

- Planned by a **competent Appointed Person** in accordance with LOLER 1998
- Verified against the **actual crane manufacturer's load chart** on site
- Conducted under the supervision of qualified personnel
- Compliant with all applicable site-specific risk assessments and permits to work

Load chart data in this application is indicative only and must **never** be used as a substitute for the certified manufacturer documentation.

---

## 📄 Licence

MIT Licence — free to use, modify and distribute. Attribution appreciated.

---

## 👤 Author

**Mahmoud Elsayed** — Mechanical Engineer · Lifting Equipment Specialist  
LEEA-AP-04421 · CMIOSH · CFD / ANSYS Fluent  
[GitHub](https://github.com/YOUR_USERNAME) · [LinkedIn](https://linkedin.com/in/YOUR_PROFILE)

---

## 🌐 Community & Support

- 🏗️ [LEEA — Lifting Equipment Engineers Association](https://leea.org.uk)
- 📋 [HSE LOLER Guidance](https://www.hse.gov.uk/work-equipment-machinery/loler.htm)
- 💬 Open an [Issue](https://github.com/YOUR_USERNAME/liftplan-pro/issues) for bugs or feature requests
- ⭐ Star the repo if you find it useful — it helps other lifting engineers find it!
