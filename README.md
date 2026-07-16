<div align="center">

# FTT Optimization and App Installer

*A lightweight desktop utility that installs your apps and optimizes Windows with a single click.*

[![Privacy](https://img.shields.io/badge/Privacy-Policy-blue)](privacy.md)
[![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-lightgrey)](license.md)
![Platform](https://img.shields.io/badge/platform-Windows%2010%20%2F%2011-informational)
![PowerShell](https://img.shields.io/badge/PowerShell-5.1%2B-5391FE)

</div>

---

## 📸 See it in Action
<img width="593" height="647" alt="image" src="https://github.com/user-attachments/assets/b21f6850-f289-4f95-90c5-8e511e4b5042" />


---

## Overview

FTT Optimization and App Installer replaces the repetitive process of manually installing apps and debloating Windows after a fresh install. Instead of running the same `winget` commands and registry edits every time, you check the boxes you want and generate a portable script that does it all in one run.

## Features

- **50+ Application Library** — Common apps (browsers, dev tools, utilities, media, communication) installed via `winget`
- **Windows Optimization Suite** — Disable telemetry, Copilot, Game Bar, search bloat, startup entries, and more
- **Self-Elevating Script** — Generated `.bat` automatically requests Administrator privileges
- **Fault-Tolerant Installs** — A failed app install logs a warning and continues rather than halting the script
- **Auto-Named Output** — Generated scripts are automatically timestamped for easy tracking
- **No Bundled Dependencies** — Pure PowerShell + WinForms, no Electron, no third-party runtime

## Requirements

| Requirement | Details |
|---|---|
| OS | Windows 10 (2004+) or Windows 11 |
| PowerShell | 5.1 or later (built into Windows) |
| winget | Included on modern Windows, or install "App Installer" from the Microsoft Store |
| Privileges | Administrator (the generated script elevates itself automatically) |
| Internet | Required for `winget` to download selected applications |

## Usage

1. Download `FTT-Installer.ps1` from this repository.
2. Right-click the file and select **Run with PowerShell** (or run it from an elevated PowerShell prompt).
3. Check the applications and optimizations you want.
4. Click **Generate Install Script**.
5. Save the generated `.bat` file, then run it as Administrator.

> **Tip:** If PowerShell blocks the script due to execution policy, run:
> ```powershell
> powershell -ExecutionPolicy Bypass -File .\FTT-Installer.ps1
> ```

## Version Support

| Version | Status | Notes |
|---|---|---|
| Windows 11 | ✅ Fully supported | Primary test environment |
| Windows 10 (2004+) | ✅ Fully supported | Requires `winget` installed manually if not present |
| Linux | ⚠️Testing Stage | Currently Testing with 2.0 Beta 1, Install at your own risk |
| Windows 10 (pre-2004) | ⚠️ Not supported | `winget` is unavailable on older builds |
| Windows Server | ⚠️ Untested | May work but is not officially supported |
| Windows 8 | ⚠️ Not Supported | This will NOT work on Windows 8|
| Windows 7 | ⚠️ Not Supported | This will NOT work on Windows 7|

## Important Notes / Disclaimer

- Some optimization tweaks (e.g., **Disable Startup Bloat**) make changes that are not trivially reversible. **Creating a System Restore Point before running any tweaks is strongly recommended.**
- This tool modifies the Windows Registry and system configuration. Use at your own risk. The author is not responsible for any data loss, system instability, or other damage resulting from use of this tool.
- Application IDs are sourced from the public [winget-pkgs](https://github.com/microsoft/winget-pkgs) repository and may change or be delisted over time. If an install fails, check whether the package ID is still valid.

## Privacy

See [PRIVACY.md](PRIVACY.md) — in short, this tool collects nothing and sends nothing anywhere.

## License

See [LICENSE](LICENSE) — All Rights Reserved. Viewing and personal use is permitted; redistribution, modification, and commercial use require written permission.

## Contributing

This project is not currently open to external contributions or pull requests. Bug reports and suggestions are welcome via the Issues tab.
