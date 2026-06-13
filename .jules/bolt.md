## 2024-05-24 - Optimize deployment size for OpenCV
**Learning:** When using `opencv-python-headless`, X11 system dependencies like `libgl1-mesa-glx` are not required. Including them needlessly inflates the deployment package size and slows down installations.
**Action:** Always ensure `libgl1-mesa-glx` and similar X11 dependencies are excluded from `packages.txt` or equivalent system dependency files when the application uses the headless version of OpenCV.
