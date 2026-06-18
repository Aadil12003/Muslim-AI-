## 2026-06-18 - Unnecessary X11 Dependencies with OpenCV Headless
**Learning:** When using `opencv-python-headless`, X11 system dependencies like `libgl1-mesa-glx` are not required. Including them in `packages.txt` unnecessarily inflates the deployment package size and increases installation time.
**Action:** Always check `requirements.txt` for headless versions of packages (like OpenCV) before adding system-level UI/rendering dependencies to `packages.txt`.
