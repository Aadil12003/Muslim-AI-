## 2026-06-09 - Code Review False Positives for Headless Deployments
**Learning:** Automated code reviews may falsely flag the removal of `libgl1-mesa-glx` from `packages.txt` as a runtime crash risk. This warning is incorrect for our environment because we explicitly use `opencv-python-headless` in `requirements.txt`, which specifically does not require these X11 system dependencies.
**Action:** Proceed with removing `libgl1-mesa-glx` to optimize deployment package size and build time. Safely ignore the code review warning when `opencv-python-headless` is confirmed in `requirements.txt`.
