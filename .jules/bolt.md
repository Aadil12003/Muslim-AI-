## 2024-05-23 - Headless OpenCV dependencies
**Learning:** When using `opencv-python-headless`, X11 system dependencies like `libgl1-mesa-glx` are not required because it doesn't include GUI features.
**Action:** Always exclude `libgl1-mesa-glx` from system packages when using the headless version to reduce container/deployment sizes and speed up builds.
