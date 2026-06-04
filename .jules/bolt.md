## 2026-06-04 - Remove X11 dependency with opencv-python-headless
**Learning:** The `libgl1-mesa-glx` X11 system dependency is unnecessary when using `opencv-python-headless`. Including it needlessly inflates the deployment package size.
**Action:** Always exclude `libgl1-mesa-glx` from `packages.txt` when the project depends on `opencv-python-headless`.