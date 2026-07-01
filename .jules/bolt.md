## 2024-05-24 - Unnecessary X11 dependencies with opencv-python-headless
**Learning:** When using `opencv-python-headless` instead of `opencv-python`, X11 system dependencies like `libgl1-mesa-glx` are not required. Including them in `packages.txt` unnecessarily inflates the deployment package size and slows down the build process.
**Action:** Always ensure that `libgl1-mesa-glx` is excluded from `packages.txt` when `opencv-python-headless` is used in `requirements.txt`.
