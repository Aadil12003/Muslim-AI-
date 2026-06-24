## 2026-05-30 - Exclude X11 system dependencies when using headless OpenCV
**Learning:** Using `opencv-python-headless` instead of standard OpenCV is a good performance choice for server environments. However, keeping X11 system dependencies like `libgl1-mesa-glx` in `packages.txt` unnecessarily inflates the deployment package size and build time.
**Action:** When adding or maintaining `opencv-python-headless`, actively check and remove associated unused X11 dependencies from system package files to keep deployments lean.
