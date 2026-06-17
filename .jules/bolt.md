## 2024-05-24 - Remove X11 dependency for headless OpenCV
**Learning:** Using `opencv-python-headless` means we don't need X11 system dependencies like `libgl1-mesa-glx`. Including it unnecessarily inflates the deployment package size and increases startup time in serverless/container environments.
**Action:** When `opencv-python-headless` is used, ensure `libgl1-mesa-glx` is removed from system packages lists (like `packages.txt`).
