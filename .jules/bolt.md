## 2026-06-09 - Exclude X11 system dependencies when using headless OpenCV
**Learning:** When using `opencv-python-headless` instead of `opencv-python`, X11 system dependencies like `libgl1-mesa-glx` are not required. Including them unnecessarily inflates the deployment package size and slows down the build process.
**Action:** Always check if system dependencies are strictly necessary. Remove `libgl1-mesa-glx` and similar GUI-related packages from system dependencies (like `packages.txt`) when the project specifically relies on headless versions of libraries.
