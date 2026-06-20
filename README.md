# new

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python)](https://python.org)
[![AppVeyor](https://img.shields.io/badge/AppVeyor-CI-00BFFF?style=for-the-badge)](https://ci.appveyor.com)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Overview

Python test repository with AppVeyor CI/CD configuration. Contains initial setup and CI pipeline testing for Python projects on Windows.

## Project Structure

```
new/
├── .gitignore        # Git ignore rules
├── a.py              # Main Python script
├── appveyor.yml      # AppVeyor CI configuration
└── README.md
```

## CI/CD Pipeline

### AppVeyor Configuration

The project uses AppVeyor for continuous integration testing on Windows:

| Python Version | Architecture | Status |
|----------------|--------------|--------|
| 3.4.x | 64-bit | Testing |
| 3.6.x | 64-bit | Testing |

### Build Pipeline

1. **Install** — Environment setup with MSVC Express 2008
2. **Build** — `python farshidpirahansiah.py build`
3. **Test** — `python farshidpirahansiah.py nosetests --with-xunit`
4. **Package** — Wheel, Wininst, and MSI distributions

## 2025-2026 CI/CD Best Practices

### Modern CI/CD Stack

| Tool | Purpose | 2025 Status |
|------|---------|-------------|
| GitHub Actions | Free CI/CD for public repos | Industry standard |
| GitLab CI/CD | Integrated with GitLab | Enterprise ready |
| CircleCI | Fast parallel builds | Cloud-native |
| Jenkins | Self-hosted automation | Legacy but powerful |
| Dagger | CI/CD as code (Go) | Developer-focused |
| Earthly | Containerized builds | Reproducible CI |

### Python CI/CD in 2025-2026

```yaml
# Modern GitHub Actions example
name: CI
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        python-version: ['3.11', '3.12', '3.13']
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: ${{ matrix.python-version }}
      - run: pip install -r requirements.txt
      - run: pytest --cov=src tests/
```

### Package Distribution (2025-2026)

- **PyPI**: Standard Python package index
- **uv**: Ultra-fast Python package installer (Rust-based, replaces pip)
- **Poetry**: Dependency management and packaging
- **PDM**: PEP 621 compliant package manager
- **Hatch**: Modern project management

## Getting Started

```bash
# Clone repository
git clone https://github.com/pirahansiah/new.git
cd new

# Run the script
python a.py
```

## Resources

- [AppVeyor Documentation](https://www.appveyor.com/docs/)
- [GitHub Actions](https://docs.github.com/en/actions)
- [Python Packaging Guide](https://packaging.python.org)

## License

MIT License

---

**Maintainer:** [Farshid Pirahansiah](https://github.com/pirahansiah)