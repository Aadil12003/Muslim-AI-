## 2026-05-31 - Headless OpenCV Dependency Optimization
**Learning:** Using `opencv-python-headless` instead of `opencv-python` allows us to remove X11 system dependencies (like `libgl1-mesa-glx`) from `packages.txt`. This significantly reduces the deployment package size and Docker build time, especially for headless server environments.
**Action:** When working on computer vision tasks on backend/headless servers, always use `opencv-python-headless` and ensure system-level GUI dependencies are excluded from the environment setup.
