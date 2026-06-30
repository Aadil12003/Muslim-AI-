## 2024-10-24 - OpenCV Headless Dependencies
**Learning:** When using `opencv-python-headless` instead of `opencv-python`, X11 system dependencies like `libgl1-mesa-glx` are not required.
**Action:** Exclude `libgl1-mesa-glx` from system packages (e.g., `packages.txt`) when `opencv-python-headless` is used to avoid unnecessarily inflating the deployment package size.
