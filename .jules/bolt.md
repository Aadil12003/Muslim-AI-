## 2024-10-27 - Unnecessary system dependencies with OpenCV Headless
**Learning:** The project uses `opencv-python-headless`, which does not require X11 dependencies like `libgl1-mesa-glx`. Having `libgl1-mesa-glx` in `packages.txt` needlessly inflates the deployment environment size and slows down builds.
**Action:** Always check `packages.txt` for unnecessary system libraries when headless Python equivalents are used in `requirements.txt`.
