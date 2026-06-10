## 2026-06-10 - Remove unnecessary system dependencies when using headless libraries
**Learning:** System dependencies for GUI components (like `libgl1-mesa-glx`) are often unnecessarily included even when their corresponding Python packages are headless (like `opencv-python-headless`), leading to larger package sizes and slower deployment.
**Action:** Always verify if system GUI dependencies are actually required when a headless version of a package is used.
