## 2024-05-28 - Deployment size optimization with OpenCV Headless
**Learning:** When using `opencv-python-headless`, X11 system dependencies like `libgl1-mesa-glx` are not required. Including them unnecessarily inflates the deployment package size.
**Action:** Always ensure that `libgl1-mesa-glx` is excluded from system packages when `opencv-python-headless` is used in Python requirements.
