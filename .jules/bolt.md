## 2026-06-15 - Exclude X11 system dependencies with opencv-python-headless
**Learning:** When using `opencv-python-headless`, including X11 system dependencies like `libgl1-mesa-glx` in `packages.txt` unnecessarily inflates the deployment package size.
**Action:** Always check `requirements.txt` for `opencv-python-headless` and avoid adding `libgl1-mesa-glx` or similar X11 dependencies to `packages.txt`.
