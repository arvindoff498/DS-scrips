# ⚡ vfa automate — Userscript Guide (`vfa_automate.user.js`)

A lightweight, high-performance event battle automation script engine designed for **DemonicScans RPG**.

---

## 🛠️ 1. How to Install in Tampermonkey / Violentmonkey

### Requirements
- A browser with a userscript extension installed:
  - **Chrome / Edge / Brave / Opera**: [Tampermonkey](https://www.tampermonkey.net/) or [Violentmonkey](https://violentmonkey.github.io/)
  - **Firefox**: [Violentmonkey](https://violentmonkey.github.io/) or Tampermonkey
  - **Android (Mobile)**: Kiwi Browser or Firefox Nightly + Tampermonkey extension
  - **iOS / Safari**: Userscripts or Orion Browser

---

### Step-by-Step Installation

1. Open your extension dashboard (click the **Tampermonkey / Violentmonkey** icon in your browser toolbar -> **Create a new script**).
2. Clear any default placeholder code in the editor.
3. Copy the full generated script content from **vfa automate** (or copy from `vfa_automate.user.js`).
4. Paste the code into the script editor.
5. Save the script (`Ctrl + S` or `Cmd + S`).
6. Ensure the script is toggled **ON** in your extension dashboard.

---

## 📑 2. Userscript Metadata Header Structure

The generated script includes a standard compliant Userscript metadata block that browsers recognize:

```javascript
// ==UserScript==
// @name         vfa automate
// @namespace    http://tampermonkey.net/
// @version      1.1.0
// @description  Lightweight event battle automation engine for DemonicScans RPG with interactive HUD
// @author       Arvin
// @match        https://demonicscans.org/*
// @match        *://*.demonicscans.org/*
// @match        *://demonicscans.org/*
// @grant        none
// @run-at       document-end
// ==/UserScript==
```


---

## 🌟 3. Key Features

- **⚡ Lightweight Execution**: Minimal DOM queries and low-overhead timers for maximum speed.
- **💀 Dead Mob Detection & Auto-Skip**: Automatically detects mobs marked with `<span class="chip">DEAD</span>` or dead indicators and skips them to find live targets.
- **📊 Interactive On-Screen HUD Overlay**:
  - Live **K-Count Tracker** (Current K vs. Max K Target).
  - Live **Stamina Counter**.
  - Live **Status Step Log** (e.g. `Searching target...`, `Joining Battle...`, `Attacking (1,200,000 / 3,000,000)`).
  - Quick **Pause / Start** toggle button.
  - **Reset K-Count** button.
- **⚙️ Live Parameter Configuration**: Click the gear icon (`⚙️`) on the floating HUD to update parameters **directly on the game page** without editing the userscript source code!
  - Target Monster Name
  - Target Damage Goal
  - Minimum Stamina Threshold
  - Max K-Count Limit
  - Attack Delay (ms)
- **🧠 Persistent Storage**: Saved parameters and K-Count progress persist automatically in your browser's `localStorage` (`vfa_config_v1` and `vfa_kcount`).

---

## 🎮 4. How to change Damage Value

1. Find **// --- DEFAULT & STORED CONFIGURATION ---** at the start of script (18th line of code)
2. Change value of **slashDmg: 67152** to the damage value of single stamina.

---

## ❓ 5. Frequently Asked Questions & Troubleshooting

#### Q: The HUD is blocking part of the game page. Can I move or hide it?
- You can turn off the HUD in the **Script Customizer** tab in the web app generator (`showOverlay = false`) before copying the script.

#### Q: How do I change target damage or monster name while playing?
- Click the gear icon (`⚙️`) on the floating HUD at the bottom-right of your game screen.
- Enter your new values in the inputs and click **Save Parameters**. The script instantly applies them!

#### Q: The script is not running on my game page.
- Make sure your URL matches the `@match` rule in the header (e.g. `https://demonicscans.org/*`).
- Check your browser console (`F12` -> `Console`) for any blocked script warnings or Tampermonkey extension status.

#### Q: How do I reset my K-Count back to 0?
- Click the **Reset K** button on the floating HUD overlay, or execute `localStorage.setItem('vfa_kcount', '0')` in your browser console.

#### Q: The script is doing extra damage then required?
- Change the **Default Damage Value** in script. See, **How to change Damage Value**

