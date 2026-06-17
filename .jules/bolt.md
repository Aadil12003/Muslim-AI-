## 2024-05-24 - OpenCV Headless Dependency Optimization
**Learning:** When using `opencv-python-headless`, X11 system dependencies like `libgl1-mesa-glx` are completely unnecessary. Including them in deployment configuration (`packages.txt` or Dockerfiles) only unnecessarily inflates the deployment package size and build time without providing any functionality.
**Action:** Always verify if X11 dependencies are actually needed when encountering `opencv-python-headless`. If they are present alongside it, remove them to optimize deployment sizes.
