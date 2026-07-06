## 2024-05-24 - Optimize Deployment Package Size with Headless OpenCV
**Learning:** Using `opencv-python-headless` eliminates the need for X11 system dependencies like `libgl1-mesa-glx`. Including these dependencies unnecessarily inflates the deployment package size and increases build times.
**Action:** Always exclude `libgl1-mesa-glx` from system packages (e.g., `packages.txt`) when `opencv-python-headless` is already specified in `requirements.txt`.
