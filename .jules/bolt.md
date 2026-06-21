## 2024-05-24 - Remove X11 dependencies when using headless OpenCV
**Learning:** `opencv-python-headless` does not require X11 UI dependencies. Including packages like `libgl1-mesa-glx` in `packages.txt` unnecessarily inflates deployment size and increases startup time.
**Action:** Always check if `opencv-python-headless` is used, and if so, remove X11 system dependencies from `packages.txt`.
