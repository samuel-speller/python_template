
# Python Template Repository
## Using This Repository as a Template


You can use this repository as a starting point for your own Python projects. **Do not push changes to this template repository.**

### Option 1: Use the GitHub Template Button
1. Click the "Use this template" button on GitHub.
2. Create a new repository under your own GitHub account.
3. Clone your new repository locally:
	```shell
	git clone https://github.com/<your-username>/<your-new-repo>.git
	cd <your-new-repo>
	```

### Option 2: Manual Clone and Rename
1. Clone the template repository (do not push back to the template):
	```shell
	git clone https://github.com/samuel-speller/python_template.git <your-new-repo>
	cd <your-new-repo>
	```
2. Remove the existing git history:
	```shell
	rm -rf .git
	git init
	git add .
	git commit -m "Initial commit from template"
	git remote add origin https://github.com/<your-username>/<your-new-repo>.git
	git push -u origin main
	```

### Next Steps
1. Update the project name and metadata in `pyproject.toml`.
2. Replace or remove example code and utilities as needed.
3. Follow the setup instructions below to initialize your new project.


This repository provides a modular Python project structure with utilities, notebook prototyping, and pre-commit hooks for code quality. It is designed for rapid development, experimentation, and easy extension.

## Project Structure

- `src/` — Main source code
- `notebooks/` — Jupyter notebooks for prototyping and experimentation
- `tests/` — Test suite (add pytest tests here)
- `.pre-commit-config.yaml` — Pre-commit hook configuration
- `pyproject.toml` — Project/package configuration
- `uv.lock` — Dependency lock file

## Getting Started

### 1. Install Pre-commit Hooks (Required)
Pre-commit hooks enforce code quality on every commit. Install them after cloning:
```shell
pre-commit install
```

### 2. Install Dependencies
Use your preferred tool (`uv` or `pip`) to install dependencies:
```shell
uv sync
# or
pip install -r pyproject.toml
```

### 3. Using Notebooks
- Place notebooks in the `notebooks/` directory.
- To import project modules in a notebook, add the project root to `sys.path` at the top:
	```python
	import os, sys
	sys.path.append(os.path.abspath(os.path.join(os.getcwd(), "..")))
	from src.utils import data_manipulation
	```
- Notebooks are for prototyping only. Move reusable code to `src/`.

### 4. Adding Modules
- Add utility functions to `src/utils/` (e.g., `data_manipulation.py`).
- Use relative imports within `src/` (e.g., `from .utils import data_manipulation`).

### 5. Testing
- Place tests in the `tests/` directory.
- Use `pytest` to run tests (not yet configured, but standard for Python projects):
	```shell
	pytest tests/
	```

## Conventions & Best Practices
- All reusable code should be in `src/`.
- Use pre-commit hooks to maintain code quality.

## Example: Adding a Utility Function
1. Add your function to `src/utils/data_manipulation.py`.
2. Import and use it in notebooks or other modules as shown above.
3. Add tests in `tests/` if needed.

## External Dependencies
- Managed via `pyproject.toml` and `uv.lock`.
- Use `uv` or `pip` for installation.

## License
MIT licence. See `LICENSE` for details.

