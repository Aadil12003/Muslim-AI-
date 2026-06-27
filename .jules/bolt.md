## 2024-06-28 - Unnecessary X11 dependency with OpenCV Headless
**Learning:** When using `opencv-python-headless` (which is compiled without GUI dependencies), system libraries like `libgl1-mesa-glx` (X11) are unnecessary and only inflate the package size and deployment time.
**Action:** Always ensure that `libgl1-mesa-glx` is not included in `packages.txt` when `opencv-python-headless` is used in `requirements.txt`.
