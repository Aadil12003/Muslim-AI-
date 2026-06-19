## 2024-05-24 - Unnecessary System Dependencies with Headless OpenCV
**Learning:** When using `opencv-python-headless`, including X11 system dependencies like `libgl1-mesa-glx` in deployment configs (like `packages.txt`) unnecessarily inflates the deployment package size, as the headless version doesn't require GUI components.
**Action:** Always check if `opencv-python-headless` is being used in Python requirements before adding or keeping X11 system dependencies in deployment configuration files.
