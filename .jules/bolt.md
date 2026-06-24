## 2024-05-24 - Exclude X11 dependencies with headless OpenCV
**Learning:** Using `opencv-python-headless` instead of the standard OpenCV package eliminates the need for X11 system dependencies like `libgl1-mesa-glx`, which unnecessarily inflate the deployment package size and build time.
**Action:** Always check `packages.txt` or equivalent system dependency files for `libgl1-mesa-glx` when `opencv-python-headless` is used in `requirements.txt`, and remove it to optimize container/package sizes.
