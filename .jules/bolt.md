## 2024-05-24 - Remove X11 dependency with opencv-python-headless
**Learning:** `libgl1-mesa-glx` is not required as a system dependency when using `opencv-python-headless`, as the headless version doesn't require GUI/X11 libraries. Removing it reduces deployment size and speeds up installations.
**Action:** Always verify if `libgl1-mesa-glx` is present in `packages.txt` when `opencv-python-headless` is used, and remove it to optimize deployments.
