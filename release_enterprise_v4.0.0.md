# Release Notes: Device Manager v4.0.0

**Release Date:** July 02, 2025
**Version:** 4.0.0 (Major Release)
**Full Changelog**: https://github.com/gosme/DeviceManager/compare/v3.1.4...v4.0.0

## Executive Summary
Version 4.0.0 marks a massive paradigm shift in the Device Manager architecture. We are introducing the highly anticipated **Workflow Automation Engine**, allowing users to visually build, save, and execute sequential test pipelines. Under the hood, this release brings a complete overhaul to the asynchronous execution backend using `QThreadPool` and introduces a scalable, global CSS-like styling matrix (`config/style.qss`) that decouples all UI aesthetics from core logic.

---

## ✨ New Features
* **Workflow Dashboard (`config/tabs/workflow.xml`)**: A brand new dedicated tab to serve as the hub for workflow automation, accessible via the new primary dock icon (`config/icons/workflow.png`).
* **Visual Workflow Builder (`modules/UI/workflow_widgets.py`)**: Assemble custom macros using a visual sequence builder utilizing the newly updated OS command dictionary matrix (`commands/`).
* **Persistent Workflows (`config/saved_workflows.xml`)**: Save your most complex workflow sequences directly to the local machine for instant loading upon startup.

---

## 🛠️ Architecture Refactoring & Enhancements
* **Global QSS Migration (`config/style.qss`)**: Completely migrated all inline UI styles to a global QSS stylesheet, utilizing `setObjectName` tags (`SettingsCard`, `FieldLabel`) for a true MVC styling pattern.
* **Native PySide6 Threading (`modules/core/process_tracker.py`)**: Ripped out legacy background task patterns in favor of robust, native asynchronous tracking using `QThreadPool.globalInstance().activeThreadCount()` and `runnable_helper.py`.
* **Dynamic Command Parsing (`modules/core/command_parser.py`)**: Introduced an intelligent command parser capable of normalizing shell arguments across Android, FireOS, and VegaOS targets.
* **App Data Controller (`modules/UI/app_data_controller.py`)**: Decoupled local App Data configuration management away from the primary Settings controller for improved scalability.
* **Geometry Adjustments (`device_manager/main.py`)**: Improved application boot logic to automatically scale to the active screen's available height using `QGuiApplication.primaryScreen().availableGeometry()`.
