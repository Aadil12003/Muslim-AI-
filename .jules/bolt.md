## 2026-06-14 - Optimize Deployment Size
**Learning:** The `opencv-python-headless` package does not require X11 dependencies like `libgl1-mesa-glx`. Including such dependencies unnecessarily inflates the deployment package size.
**Action:** Always ensure that X11 dependencies are excluded from `packages.txt` when using headless OpenCV.
