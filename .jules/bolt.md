## 2024-05-24 - Headless OpenCV Deployment
**Learning:** Using `opencv-python-headless` means we don't need X11 dependencies like `libgl1-mesa-glx` in system packages, reducing deployment size.
**Action:** Always check if headless versions of libraries are used to avoid unnecessarily inflating deployment environments.
