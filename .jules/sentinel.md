## 2025-05-07 - [Prevent Secret Leakage via .gitignore]
**Vulnerability:** Missing `.gitignore` could lead to accidental commit of sensitive files (e.g., `.env`, `.streamlit/secrets.toml`, API keys).
**Learning:** In initial project setups, it's easy to forget to add `.gitignore`, leading to secrets being committed in the first few commits.
**Prevention:** Always add a `.gitignore` file at the start of a project, explicitly ignoring common secret files and environment directories.
