## 2024-07-03 - Optimizing Deployment Size for OpenCV
**Learning:** When using `opencv-python-headless`, X11 system dependencies like `libgl1-mesa-glx` are not required. Including them in `packages.txt` unnecessarily inflates the deployment package size.
**Action:** Exclude `libgl1-mesa-glx` and similar X11 libraries from system packages when `opencv-python-headless` is used to optimize the deployment image size.
