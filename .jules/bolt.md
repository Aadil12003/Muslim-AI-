## 2024-05-30 - Avoiding X11 dependencies with Headless OpenCV
**Learning:** Using `opencv-python-headless` means X11 system dependencies like `libgl1-mesa-glx` are not required. Including them needlessly inflates the deployment package size and increases installation time.
**Action:** When using `opencv-python-headless`, always ensure X11 system dependencies like `libgl1-mesa-glx` are excluded from `packages.txt` or other system dependency files.
