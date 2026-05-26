## 2026-05-26 - OpenCV Headless Dependencies
**Learning:** When using `opencv-python-headless`, X11 system dependencies like `libgl1-mesa-glx` are not needed and unnecessarily inflate the deployment package size.
**Action:** Remove `libgl1-mesa-glx` from system packages (e.g., `packages.txt`) when `opencv-python-headless` is used in Python requirements.
