# Camera Vision Studio

Camera Vision Studio is a local Python + C++ webcam project for Windows 11.
The modern menu is written in C++ with Qt 6. Each experiment starts as its
own Python/OpenCV process and has its own **Start** button.

No camera image is uploaded. All processing runs locally on the computer.

## The six buttons

1. **Finger Shapes** — stretch a rectangle, ellipse, or triangle with thumb
   and index finger. The shape animates back to its normal size after release.
2. **Finger Counter** — detects up to two hands, marks raised fingertips, and
   shows the total.
3. **3D Face Points** — split view with the live camera on the left and a
   depth-projected face point cloud on the right.
4. **Face Expression** — estimates happy, sad, surprised, or neutral from
   facial landmark geometry.
5. **3D Ball** — moves a shaded, animated ball with the palm. Moving closer to
   the camera changes its apparent depth and size.
6. **Air Canvas** — paint with the index finger, choose colors, erase, or clear.

Close a camera window with `Q` or `Esc`. The C++ menu also has a **Stop** button.

> Expression detection is a playful geometric estimate, not a reliable reading
> of somebody's feelings and not suitable for medical, safety, school, or
> employment decisions.

## Requirements

- Windows 11 x64
- Webcam
- Python 3.11 x64
- Qt 6.5 or newer (Qt 6.8 LTS is a good choice)
- CMake 3.21+
- A C++17 compiler matching the installed Qt kit

When installing Qt, select a desktop kit such as `Qt 6.x MinGW 64-bit`, plus
CMake and Ninja. If you use MSVC Qt, install the matching Visual Studio C++
workload.

## Quick start

1. Run `setup_windows.bat`. It creates `.venv` and installs OpenCV, MediaPipe,
   and NumPy.
2. Run `build_windows.bat`. It finds a normal `C:\Qt\...` installation or uses
   the `QTDIR` environment variable.
3. Start `dist\CameraVisionStudio.exe`.
4. Open **Settings**, choose the camera index and `Deutsch` or `English`.

If the wrong camera opens, try Camera 1, then Camera 2. Windows camera indexes
do not always match the order shown in other apps.

### Test Python without compiling C++

Run:

```bat
test_python_mode.bat 1 0
```

The first number is the mode (1–6), and the second is the camera index.

## Repository link

The menu currently opens:

`https://github.com/Starcode-AI/Python-AI-Software`

If your repository uses another address, change `repositoryUrl` near the top of
`src/MainWindow.cpp` before compiling.

## Project layout

```text
CameraVisionStudio/
├── assets/                 Logo
├── python/vision_studio/   Six OpenCV/MediaPipe modes
├── resources/              Qt resource bundle
├── src/                    C++/Qt menu
├── CMakeLists.txt
├── setup_windows.bat
└── build_windows.bat
```

## Deutsch

Das Projekt verarbeitet die Kamera vollständig lokal. Jeder der sechs Modi hat
im C++-Menü einen eigenen Startknopf. Mit `Q`, `Esc` oder dem Stoppen-Knopf wird
der aktive Modus beendet. Die Kamera und Sprache lassen sich unter
**Einstellungen** ändern.

## License

Copyright © 2026 Starcode-AI.

Licensed under the GNU General Public License v3.0 only. See `LICENSE`.
Dependency licenses are summarized in `THIRD_PARTY_NOTICES.md`.

`SPDX-License-Identifier: GPL-3.0-only`
