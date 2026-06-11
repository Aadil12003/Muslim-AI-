## 2026-06-11 - Exclude X11 system dependencies when using opencv-python-headless
**Learning:** When using `opencv-python-headless`, X11 system dependencies like `libgl1-mesa-glx` can be excluded from `packages.txt` to avoid unnecessarily inflating the deployment package size.
**Action:** Remove `libgl1-mesa-glx` from `packages.txt` if `opencv-python-headless` is in `requirements.txt`.