# Third-party software

Camera Vision Studio installs and uses the following third-party components.
They are not relicensed by this project.

| Component | Purpose | License |
| --- | --- | --- |
| Qt 6 | Native C++ desktop interface | LGPL-3.0-only, GPL-2.0-only, GPL-3.0-only, or commercial, depending on the Qt distribution and modules |
| OpenCV | Camera input and image rendering | Apache-2.0 |
| MediaPipe | Hand and face landmarks | Apache-2.0 |
| NumPy | Numeric operations | BSD-3-Clause |

The Python setup script downloads these packages from their normal package
repositories. The source ZIP does not include their binary files.

When distributing a compiled version, keep the applicable dependency license
texts and notices with that distribution. Qt must be distributed according to
the license option you use and the requirements of the selected Qt modules.
