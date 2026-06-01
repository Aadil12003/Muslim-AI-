## 2026-06-01 - Avoid unnecessary X11 dependencies with opencv-python-headless
**Learning:** Using `opencv-python-headless` instead of `opencv-python` eliminates the need for X11 system dependencies like `libgl1-mesa-glx`, avoiding unnecessarily inflated package sizes.
**Action:** When `opencv-python-headless` is used in a project's `requirements.txt`, ensure that associated X11 system dependencies are removed from system packages configurations like `packages.txt` to minimize deployment build sizes.
