## 2024-05-24 - OpenCV Headless Dependencies
**Learning:** When using `opencv-python-headless`, X11 system dependencies like `libgl1-mesa-glx` are not required. Including them unnecessarily inflates the deployment package size and increases environment setup time.
**Action:** Exclude `libgl1-mesa-glx` and similar X11 dependencies from system packages when `opencv-python-headless` is already specified in Python dependencies.
