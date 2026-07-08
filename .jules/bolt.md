## 2024-05-24 - Headless OpenCV Optimization
**Learning:** Using `opencv-python-headless` instead of the standard OpenCV package eliminates the need for X11 system dependencies like `libgl1-mesa-glx`. Including these graphical libraries unnecessarily inflates the deployment package size and increases build time.
**Action:** Always verify if GUI capabilities are actually needed. If using the headless version, ensure system-level graphical dependencies are excluded from environment configurations (like `packages.txt`).
