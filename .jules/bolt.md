## 2024-06-08 - Remove unnecessary X11 dependencies with headless OpenCV
**Learning:** When using `opencv-python-headless`, X11 system dependencies like `libgl1-mesa-glx` are not required. Including them unnecessarily inflates deployment package sizes.
**Action:** Exclude `libgl1-mesa-glx` (and similar X11 libraries) from `packages.txt` or Dockerfiles when `opencv-python-headless` is used.
