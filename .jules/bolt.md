## 2024-05-18 - Avoid X11 dependencies with headless OpenCV
**Learning:** Using `opencv-python-headless` instead of standard `opencv-python` eliminates the need for X11 system dependencies like `libgl1-mesa-glx`, which unnecessarily inflate deployment package sizes and increase container spin-up time.
**Action:** When working in headless environments, remove X11 dependencies from system packages and rely on `opencv-python-headless` in requirements.
