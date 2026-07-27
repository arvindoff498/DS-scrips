# PvP Achievement Script for cleric

A lightweight background script that automates PvP battles on **DemonicScans** to help complete PvP-related achievements.

> **Note:** This script is **not** designed to improve your win rate. It simply automates battles for achievement progression.

---

## Features

- Runs entirely in the background.
- No HUD or on-screen interface.
- Automatically uses **Slash** and **Power Slash**.
- Stops automatically when the configured number of PvP tokens remains.
- Designed for achievement farming only.

---

## Requirements

Before starting the script:

- Open the PvP page:
  ```
  https://demonicscans.org/pvp.php
  ```
- Make sure you have **more than 5 PvP tokens**.

---

## Installation

1. Install a userscript manager:
   - **Tampermonkey** (recommended)
   - **Violentmonkey**
   - **Greasemonkey** (Firefox)

2. Create a new userscript.

3. Copy and paste the contents of this script into the editor.

4. Save the script.

5. Open:
   ```
   https://demonicscans.org/pvp.php
   ```

6. Ensure you have more than **5 PvP tokens**.

7. The script will start automatically.

---

## If the Script Doesn't Work

If the script does not run, check the following:

1. Verify that the URL is exactly:
   ```
   https://demonicscans.org/pvp.php
   ```
   There should be **nothing** after `pvp.php` (no extra path or query parameters).

2. Check your PvP tokens.
   - The script only starts if you have **more than 5 PvP tokens**.

3. Make sure your userscript manager is enabled and the script is turned on.

---

## Default Behaviour

By default, the script:

- Uses **Slash** and **Power Slash** during battles.
- Continues battling until only **5 PvP tokens** remain.
- Stops automatically when 5 tokens are left.

---

## Changing the Stop Limit

To change the number of PvP tokens the script leaves unused, edit this line:

```javascript
if (pvpTokens > 5)
```

Replace `5` with your preferred value.

For example:

```javascript
if (pvpTokens > 10)
```

The script will now stop when **10 PvP tokens** remain.

---

## Notes

- This script runs completely in the background.
- There is no graphical interface or HUD.
- The script is intended **only** to automate PvP battles for achievement completion.
- It does **not** improve your chances of winning battles or optimize combat strategy.

---

## Disclaimer

This project is provided **as is**, without any warranty or guarantee of any kind.

- Use this script **at your own risk**.
- The author is **not responsible** for account warnings, suspensions, bans, data loss, or any other consequences resulting from its use.
- Ensure that using this script complies with the rules and terms of service of the website or game before using it.

If you choose to use this script, you accept full responsibility for any consequences.
