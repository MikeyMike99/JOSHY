# Accessible Audio Playback Suite (JOSHY)

A high-performance, fully accessible Windows audio playback and Spotify controller designed from the ground up for blind and visually impaired users. Features native screen-reader speech synchronization (NVDA, JAWS, Narrator via SAPI5), acoustic audio earcons, and comprehensive keyboard-only navigation.

---

## Quick Start

### 1. Launch the Application
Double-click `run_suite.bat` or run from PowerShell / Command Prompt:
```cmd
run_suite.bat
```
*(Or directly with Python: `py -3.13 t.py`)*

### 2. Run the Automated Test Suites
Verify all unit tests pass:
```cmd
py -3.13 test_suite_redesign.py
py -3.13 test_demo_license.py
```

### 3. Compile Standalone Windows Executable & Installer
To compile the secure native C machine-code binary (`JOSHY.exe` / `t.exe`) and NSIS installer (`JOSHY-Setup.exe`):
```cmd
compile_joshy.bat
```
Output binaries are automatically placed in the `dist\` folder (`dist\JOSHY.exe`, `dist\t.exe`, and `dist\JOSHY-Setup.exe`).

---

## Directory Organization

```text
Audio_pllayback_suite/
│
├── run_suite.bat               # Primary one-click launcher for the Accessible Audio Playback Suite
├── compile_joshy.bat           # Nuitka compilation and setup script (outputs to dist\)
├── t.py                        # Core GUI Application (JOSHY Audio Playback Suite)
├── demo_license.py             # Hardware-bound demo licensing and anti-reinstallation engine
├── screenreader_speak.py       # Screen-reader voice speech output bridge (NVDA, JAWS, SAPI)
├── nvda_client_data.py         # NVDA controller client data definitions
├── test_suite_redesign.py      # Automated Application Test Suite (27 tests)
├── test_demo_license.py        # Automated Demo License Test Suite (7 tests)
│
├── user_library.json           # User Library database (favorites, playlists, tracks)
├── credentials.json            # Configuration / credentials
├── .spotify_token_cache        # Spotify token session cache
│
├── accessible_output2/         # Screen-reader driver package
├── bin_sp/                     # Spotify headless binary daemon
│
├── dist/                       # Standalone compiled binaries
│   ├── JOSHY.exe               # Compiled native standalone executable (99MB)
│   ├── t.exe                   # Prototype executable (alias of JOSHY.exe)
│   └── JOSHY-Setup.exe         # Windows user installer (35MB)
│
├── demos/                      # Interactive simulation & demo scripts
│   ├── live_accessibility_demo.py
│   └── audible_blind_user_session.py
│
├── legacy/                     # Experimental / prototype editions
│   ├── t_api.py                # Web API edition
│   ├── run_api.bat             # Runner for API edition
│   ├── t_headless.py           # Headless Spotify daemon edition
│   └── run_headless.bat        # Runner for headless edition
│
├── archive/                    # Historical backups
│   ├── t.py.bak
│   └── t_backup.py
│
└── docs/                       # Project documentation
    └── README.md
```

---

## Core Hotkeys & Accessibility Reference

| Action | Shortcut |
| :--- | :--- |
| **Play / Pause** | <kbd>Space</kbd> *(or <kbd>Ctrl+Alt+Shift+Up</kbd> globally)* |
| **Volume Up (+5%)** | <kbd>]</kbd> (Right Bracket) *(or <kbd>Ctrl+Alt+]</kbd>)* |
| **Volume Down (-5%)** | <kbd>[</kbd> (Left Bracket) *(or <kbd>Ctrl+Alt+[</kbd>)* |
| **Next Track** | <kbd>Ctrl+Alt+Shift+Right</kbd> |
| **Previous Track** | <kbd>Ctrl+Alt+Shift+Left</kbd> |
| **Jump to Search** | <kbd>E</kbd> *(or <kbd>Ctrl+F</kbd>)* |
| **Cycle Buttons** | <kbd>B</kbd> (forward) / <kbd>Shift+B</kbd> (backward) |
| **Show Song Lyrics** | <kbd>Ctrl+Y</kbd> *(or <kbd>Y</kbd>)* |
| **Setup Wizard** | <kbd>Ctrl+W</kbd> |
| **F1 Help & Orientation** | <kbd>F1</kbd> |
