## 2026-05-28 - Unnecessary System Dependencies with OpenCV Headless

**Learning:** When using `opencv-python-headless`, X11 system dependencies like `libgl1-mesa-glx` are not required. Including them unnecessarily inflates the deployment package size and build time.

**Action:** Ensure `libgl1-mesa-glx` (and similar GUI-related system dependencies) are excluded from `packages.txt` or equivalent system package manifests when using the headless version of OpenCV.