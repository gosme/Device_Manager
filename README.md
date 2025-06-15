# Device Manager

This repository contains a PySide6-based GUI application that provides a custom interface for managing and executing system commands in a multi-tab environment. The application integrates a functional toolbar and supports creating, managing, and switching between command prompt tabs.

## Features

### Core Functionality
- **Dynamic Multi-Tab Environment:** Supports creating, managing, and switching between multiple custom command prompt tabs.
- **XML-Driven UI:** Dashboards, toolbars, and configurations are dynamically loaded from XML files.
- **Centralized Command Execution:** Asynchronous execution of system commands with real-time `stdout` and `stderr` capturing.

### Additional Features
- **Multi-OS ADB Setup:** Dynamic ADB setup and auto-migration utilities across different operating systems.
- **In-App Auto Updater:** Seamless application updates via `pipx` using GitHub release tags.
- **Process Management:** Centralized process tracker to monitor running threads, and active process listing with clickable dashboard stats.
- **Firmware Management:** Dedicated firmware module for downloading, extracting, and flashing builds with concurrency limits.
- **Logging & Monitoring:** Journal logs tab, parsed logs tab, and a centralized logging framework across all modules.
- **Device Discovery:** Device finder module for automated discovery.
- **Help Integration:** Built-in Help tab with direct GitHub issue submission integration.
- **Desktop Integration:** Automated desktop shortcut creation, custom UI icons, and OS-specific behavior (e.g., hiding terminal popups on Windows).
- **Cross-Platform Compatibility:** Enhanced Linux cross-compatibility for UI dialogs, VPN checks, and UI rendering (Wayland/XCB).
- **Jira Integration:** Interactive Jira dashboard UI, secure auth manager, and issue transition controls.
- **Automated Reporting:** Automated mail and report compilers for streamlined communication.
- **Enhanced Terminal UI:** Cross-platform terminal logic, dynamic OS shell button hiding, and integrated GitBash support.
- **Architectural Enhancements:** Decoupled UI controllers, core helpers, and logging backends for improved maintainability.
- **PySide6 Migration:** Fully transitioned to PySide6 for enhanced UI rendering and modern Qt6 support.
- **Settings Management:** Dedicated Settings tab for configuring UI appearance and application preferences.

## Requirements

- **Operating System:** Windows, macOS, Linux (Ubuntu/Debian-based)
- **Python:** Version 3.7 or higher
- **Package Managers:** `pip` and `pipx`

## Installation

### 1. Install Python and pip
- **Windows:** Download the installer from the [Python official website](https://www.python.org/downloads/). Ensure you check the box **"Add Python to PATH"** during installation. `pip` is included by default.
- **Linux (Ubuntu):**
  ```bash
  sudo apt update
  sudo apt install python3 python3-pip python3-venv
  ```
- **macOS:** Install via [Homebrew](https://brew.sh/):
  ```bash
  brew install python
  ```


### 2. Install pipx
`pipx` is used to install and run Python applications in isolated environments.
- **Windows & Linux (via pip):**
  ```bash
  python -m pip install --user pipx
  python -m pipx ensurepath
  ```
- **Linux (Ubuntu via apt):**
  ```bash
  sudo apt update
  sudo apt install pipx
  pipx ensurepath
  ```
- **macOS (via Homebrew):**
  ```bash
  brew install pipx
  pipx ensurepath
  ```

Restart your terminal or open a new one for the `pipx` path changes to take effect.

### 3. Install Device Manager
To install the application securely in an isolated environment, use `pipx`. This method bypasses executable warnings and correctly sets up dependencies.

```bash
pipx install git+https://github.com/gosme/Device_Manager.git@v[TAG]
```
> **Note:** Replace `[TAG]` with a specific release tag (e.g., `1.9.5`) to avoid pulling unstable development versions.
>
> For the latest changes from the main branch:
>
> ```bash
> pipx install git+https://github.com/gosme/Device_Manager.git
> ```
> 
> Forced reinstall:
>
> ```bash
> pipx install --force git+https://github.com/gosme/Device_Manager.git
> ```

#### Linux (Ubuntu) Dependencies
If you encounter an error starting the application on Ubuntu regarding the Qt platform plugin (e.g., `qt.qpa.plugin: Could not load the Qt platform plugin "xcb"` or warnings about `XDG_SESSION_TYPE=wayland`), you are missing required system libraries for PySide6. 

You can install them via `apt`:
```bash
sudo apt-get update
sudo apt-get install libxcb-cursor0 libxcb-xinerama0 libxkbcommon-x11-0 qtwayland5
```

## How to Run
After installation, you can launch the application from anywhere using:
```bash
device-manager
```

## Usage
1. **Home Tab:**
   - The default dashboard loaded on application start. Displays active process listings and clickable stats.
2. **Command Prompt (CMD) Tabs:**
   - Click the "New CMD window" button on the toolbar to create a new command prompt tab.
   - Enter system commands into the input field and press `Enter` to execute asynchronously.
   - View real-time `stdout` and `stderr` directly in the terminal view.
3. **Device Management:**
   - Automatically discover connected devices using the Device Finder module.
   - Manage multi-OS ADB setups seamlessly within the application.
4. **Firmware Operations:**
   - Navigate to the Firmware tab to download, extract, and flash device builds.
   - Monitor progress logs in real-time.
5. **Logs & Monitoring:**
   - **Journal Logs Tab:** Track and analyze low-level application and device journal logs.
   - **Parsed Logs Tab:** View structured log outputs for easier debugging.
6. **Help & Issue Reporting:**
   - Use the Help tab to submit bugs or feature requests directly to the GitHub repository.
7. **Tab & Session Management:**
   - Switch between active tabs using the dynamically updated toolbar.
   - Close tabs via the close button; associated resources and toolbar items are automatically cleaned up.
8. **Jira & Reporting:**
   - Access the interactive Jira dashboard to manage issues and transitions.
   - Utilize automated mail and report compilers to streamline task updates.
9. **Settings & Customization:**
   - Access the Settings tab to customize appearance and application-specific configurations.

## Licensing and Third-Party Notices
This project is licensed under the MIT License. See the LICENSE file for details.

This application is proprietary and its custom source code is private. 

However, this application utilizes **PySide6** (the official Python bindings for the Qt Management Framework), which is licensed under the **GNU Lesser General Public License version 3 (LGPLv3)**. 

In compliance with the LGPLv3:
1. The PySide6 library is used dynamically and unaltered within this application's environment.
2. Users can independently upgrade or replace the PySide6 package within their Python/pipx environment.
3. The full text of the LGPLv3 can be found at: https://www.gnu.org/licenses/lgpl-3.0.html

---

Contributions and feedback are welcome! Open an issue or submit a pull request if you have suggestions or improvements.

