# PvP Achievement Script for cleric

A lightweight background script that automates PvP battles on **DemonicScans** to help complete PvP-related achievements.

> **Note:** This script is **not** designed to improve your win rate. It simply automates battles for achievement progression.

---

## 🚀 Key Features

* **3-Skill Strategy & Rotation Logic**:
  * **Skill Slots**: Select up to 3 skills simultaneously (Active & Heal skills supported). 
  * **Priority Mode**: Checks skills in designated order and fires the first available skill with sufficient tokens.
  * **Rotation Mode**: Cycles sequentially through your configured skill sequence.
  * **Slash Fallback**: Automatically falls back to basic Slash whenever skill tokens are insufficient or all active skills are on cooldown.
* **HP Health & Heal Threshold**: Automatically triggers healing skills when ally HP drops below your configured percentage (e.g. 50%).
* **Solo Token Threshold Guard**: Pauses matchmaking when solo tokens fall below your set minimum threshold (e.g., 2 tokens).
* **Draggable Floating HUD Overlay**: In-game control panel with live battle status logs, play/pause controls, mode switches, and token monitors.

---

## 📥 Installation Guide

1. **Install Tampermonkey**:
   * Install the [Tampermonkey Extension](https://www.tampermonkey.net/) in Chrome, Firefox, Edge, or Brave.

2. **Add the Script**:
   * Open the Tampermonkey Dashboard -> Click the **`+` (Add Script)** tab.
   * Copy the complete script code generated in this app (or from `src/tampermonkeyScript.ts`).
   * Paste the code into the Tampermonkey editor and press **`Ctrl + S`** (or `Cmd + S`) to save.

3. **Target URLs**:
   The script automatically matches and runs on:
   * `https://demonicscans.org/pvp.php*`
   * `https://demonicscans.org/pvp_battle.php*`

---

## ⚙️ How It Works & Configuration

| Feature | Description | Default Value |
| :--- | :--- | :--- |
| **Automation Toggle** | Start/Pause the automated combat engine | Enabled |
| **Strategy Mode** | Choose between `Priority` or `Rotation` | Priority |
| **Skill Order** | Configure up to 3 active skill names | Custom Skills |
| **Heal Skill** | Name of your healing skill & trigger HP % | Heal @ 50% HP |
| **Min Solo Tokens** | Minimum tokens required to queue new matches | 2 Tokens |

---

## If the Script Doesn't Work

If the script does not run, check the following:

1. Verify that the URL is exactly:
   ```
   https://demonicscans.org/pvp.php
   ```
   There should be **nothing** after `pvp.php` (no extra path or query parameters).

2. Check your PvP tokens.
   - The script only starts if you have token more than value in **PAUSE WHEN TOKEN REMAIN**.

3. Make sure your userscript manager is enabled and the script is turned on.


---

## Changing the Stop Limit

Change the Value in **PAUSE WHEN TOKEN REMAIN** field in HUD
```javascript
PAUSE WHEN TOKEN REMAIN =  10
```

The script will now stop when **10 PvP tokens** remain.

---


## Adding new skill

Navigate to Line 29 of script
```javascript
// Known Skill Reference Database
    const KNOWN_SKILLS = [
        { id: '0', name: 'Slash', type: 'active', cost: 0, graceCost: 0, tokenGain: 3 },
        { id: '-1', name: 'Power Slash', type: 'active', cost: 9, graceCost: 0 },
        { id: '9', name: 'Judgment Seal', type: 'active', cost: 3, graceCost: 0 },
        { id: '18', name: 'Sanctified Breach', type: 'active', cost: 3, graceCost: 0 },
        { id: 'adv:30', name: 'Divine Barrier', type: 'active', cost: 12, graceCost: 0 },
        { id: 'adv:32', name: 'Heaven Mercy', type: 'active', cost: 15, graceCost: 100 },
        { id: '8', name: 'Heal', type: 'heal', cost: 5, graceCost: 0 }
    ];
```

Add your skills in the same format
 ```javascript
id: 'id of your skill', name: 'name of your skill', type: 'heal/active', cost: 'Token Cost', graceCost: 'Advance Resource cost' }

//Type - Most skill are active skills. check the id of your skill.
//id="healGrid" [type:heal].
//id="skillsGrid" [type:active].
<div class="skillsGrid" id="healGrid">

//gracecost - Advance Resource Cost. For cleric - Grace
```

---

## Disclaimer

This project is provided **as is**, without any warranty or guarantee of any kind.

- Use this script **at your own risk**.
- The author is **not responsible** for account warnings, suspensions, bans, data loss, or any other consequences resulting from its use.
- Ensure that using this script complies with the rules and terms of service of the website or game before using it.

If you choose to use this script, you accept full responsibility for any consequences.
