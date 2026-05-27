## 2024-05-28 - Unnecessary System Dependencies with Headless OpenCV
**Learning:** The `opencv-python-headless` package does not require X11 system dependencies like `libgl1-mesa-glx`. Including them unnecessarily inflates the deployment package size, increasing memory footprint and slowing down deployments.
**Action:** Always verify system dependencies when using headless variants of libraries to ensure only strictly required packages are included.
