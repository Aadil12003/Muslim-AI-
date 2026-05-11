## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2026-05-11 - Missing Security Policy and Dependency Scanner
**Vulnerability:** Missing `SECURITY.md` and automated dependency vulnerability scanning (`dependabot.yml`).
**Learning:** Without a `SECURITY.md`, vulnerabilities might be disclosed publicly, and without a dependency scanner, outdated packages with known CVEs might go unnoticed.
**Prevention:** Create a `SECURITY.md` file to instruct researchers on safe vulnerability disclosure and add `.github/dependabot.yml` to automatically catch vulnerable dependencies.
