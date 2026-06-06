## 2026-06-06 - Remove X11 dependencies when using headless OpenCV
**Learning:** The `opencv-python-headless` package does not require X11 system dependencies like `libgl1-mesa-glx`. Including it in deployment configurations like `packages.txt` unnecessarily inflates the deployment package size and increases build time.
**Action:** When using `opencv-python-headless`, ensure X11 system dependencies are excluded from deployment requirements to optimize performance and package size.
