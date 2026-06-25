## 2024-10-24 - Exclude X11 system dependencies when using opencv-python-headless
**Learning:** When using `opencv-python-headless` instead of `opencv-python`, X11 system dependencies like `libgl1-mesa-glx` are not required. Including them in deployment configuration (like `packages.txt`) unnecessarily inflates the deployment package size and increases deployment time.
**Action:** Always check if `opencv-python-headless` is used and remove `libgl1-mesa-glx` or similar X11 dependencies from system packages lists to optimize deployment sizes.
