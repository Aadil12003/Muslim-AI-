## 2026-06-23 - Exclude X11 system dependencies with headless OpenCV
**Learning:** Using `opencv-python-headless` instead of the standard OpenCV package eliminates the need for X11 system dependencies like `libgl1-mesa-glx`, which needlessly bloat deployment environments.
**Action:** Always remove `libgl1-mesa-glx` from `packages.txt` when `opencv-python-headless` is in `requirements.txt` to optimize application deployment package sizes.
