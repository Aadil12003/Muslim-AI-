## 2024-07-02 - Remove redundant X11 dependency with headless OpenCV
**Learning:** When using `opencv-python-headless`, X11 system dependencies like `libgl1-mesa-glx` are not required and unnecessarily inflate the deployment package size.
**Action:** Always check `requirements.txt` for `opencv-python-headless` and remove `libgl1-mesa-glx` from `packages.txt` if present to reduce deployment payload.
