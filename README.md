
<p align="center">
	<img src="https://img.shields.io/badge/python-3.10%2B-blue.svg" alt="Python Version">
	<img src="https://img.shields.io/badge/license-MIT-green.svg" alt="License">
	<img src="https://img.shields.io/badge/linting-ruff-blueviolet" alt="Ruff">
	<img src="https://img.shields.io/badge/sql-SQLFluff-ff69b4" alt="SQLFluff">
</p>

# 🐍 Python Template Repository


<p align="center">
<b>This repository provides a modular Python project structure with utilities, notebook prototyping, and pre-commit hooks for code quality. It is designed for rapid development, experimentation, and easy extension. 🚀</b>
</p>

- [🐍 Python Template Repository](#-python-template-repository)
  - [📦 Using This Repository as a Template](#-using-this-repository-as-a-template)
    - [Option 1: Use the GitHub Template Button](#option-1-use-the-github-template-button)
    - [Option 2: Manual .zip download](#option-2-manual-zip-download)
    - [Option 3: Manual Clone and Rename](#option-3-manual-clone-and-rename)
      - [Unix/Mac:](#unixmac)
      - [Windows (PowerShell):](#windows-powershell)
    - [Next Steps](#next-steps)
  - [🗂️ Project Structure](#️-project-structure)
  - [⚡ Getting Started](#-getting-started)
    - [1️⃣ Install Pre-commit Hooks (Required)](#1️⃣-install-pre-commit-hooks-required)
    - [2️⃣ Install Dependencies](#2️⃣-install-dependencies)
    - [3️⃣ Using Notebooks](#3️⃣-using-notebooks)
    - [4️⃣ Adding Modules](#4️⃣-adding-modules)
    - [5️⃣ Testing](#5️⃣-testing)
  - [📚 External Dependencies](#-external-dependencies)
  - [📝 License](#-license)
  - [✨ Code Quality: Using Ruff](#-code-quality-using-ruff)
    - [How to Run Ruff](#how-to-run-ruff)
  - [🛢️ SQL Linting: Using SQLFluff](#️-sql-linting-using-sqlfluff)
    - [How to Run SQLFluff](#how-to-run-sqlfluff)
  - [💻 VS Code Workspace Configuration (`.vscode` folder)](#-vs-code-workspace-configuration-vscode-folder)



## 📦 Using This Repository as a Template

You can use this repository as a starting point for your own Python projects. **Do not push changes to this template repository.**

### Option 1: Use the GitHub Template Button
1. Click the "Use this template" button on GitHub.
2. Create a new repository under your own GitHub account.
3. Clone your new repository locally:
	```shell
	git clone https://github.com/<your-username>/<your-new-repo>.git
	cd <your-new-repo>
	```

### Option 2: Manual .zip download
1. Navigate to the repository: 
 ```
 https://github.com/samuel-speller/python_template.git
 ```
2. Click on `<> Code`, and Download ZIP.
3. Unzip the repository in your desired location.
4. Initialise git:
```shell
git init
```

### Option 3: Manual Clone and Rename
#### Unix/Mac:
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

#### Windows (PowerShell):
1. Clone the template repository (do not push back to the template):
	```powershell
	git clone https://github.com/samuel-speller/python_template.git <your-new-repo>
	cd <your-new-repo>
	```
2. Remove the existing git history:
	```powershell
	Remove-Item -Recurse -Force .git
	git init
	git add .
	git commit -m "Initial commit from template"
	git remote add origin https://github.com/<your-username>/<your-new-repo>.git
	git push -u origin main
	```

### Next Steps
1. Update the project name and metadata in `pyproject.toml` and `README.md`.
2. Replace or remove example code and utilities as needed.
3. Follow the setup instructions below to initialize your new project.



## 🗂️ Project Structure

- `src/` — Main source code
- `notebooks/` — Jupyter notebooks for prototyping and experimentation
- `tests/` — Test suite (add pytest tests here)
- `.pre-commit-config.yaml` — Pre-commit hook configuration
- `pyproject.toml` — Project/package configuration
- `uv.lock` — Dependency lock file


## ⚡ Getting Started

### 1️⃣ Install Pre-commit Hooks (Required)
Pre-commit hooks enforce code quality on every commit. Install them after cloning:
```shell
pre-commit install
```

### 2️⃣ Install Dependencies
Use your preferred tool (`uv` or `pip`) to install dependencies:
```shell
uv sync
# or
pip install -r pyproject.toml
```

### 3️⃣ Using Notebooks
- Place notebooks in the `notebooks/` directory.
- To import project modules in a notebook, add the project root to `sys.path` at the top:
	```python
	import os, sys
	sys.path.append(os.path.abspath(os.path.join(os.getcwd(), "..")))
	from src.utils import data_manipulation
	```
- Notebooks are for prototyping only. Move reusable code to `src/`.

### 4️⃣ Adding Modules
- Add modules to `src/` (e.g., `utils/data_manipulation.py`).
- Use relative imports within `src/` (e.g., `from src.utils import data_manipulation`).

### 5️⃣ Testing
- Place tests in the `tests/` directory.
- Use `pytest` to run tests (not yet configured, but standard for Python projects):
	```shell
	pytest tests/
	```

## 📚 External Dependencies
- Managed via `pyproject.toml` and `uv.lock`.
- Use `uv` or `pip` for installation.


## 📝 License
MIT License, see `LICENSE`


## ✨ Code Quality: Using Ruff

This project uses [Ruff](https://docs.astral.sh/ruff/) for linting and code formatting. Ruff is a fast Python linter and formatter that helps enforce code style and catch common errors.

Ruff is run automatically as part of the pre-commit hooks, so you do not need to run it manually unless you want to check or fix issues before committing. Details on how to run it manually are below:

### How to Run Ruff

- To check your code for linting issues:
	```shell
	ruff check
	```
- To automatically fix simple issues:
	```shell
	ruff check --fix
	```
- To format your code:
	```shell
	ruff format
	```

This repo template comes with basic Ruff linting rules set in the `pyproject.toml` file. For more details and configuration options, see the [official Ruff documentation](https://docs.astral.sh/ruff/).


## 🛢️ SQL Linting: Using SQLFluff

This project uses [SQLFluff](https://docs.sqlfluff.com/) for linting SQL files. SQLFluff helps ensure your SQL code is clean, consistent, and follows best practices.

SQLFluff is also run automatically as part of the pre-commit hooks, so you do not need to run it manually unless you want to check or fix issues before committing. Details on how to run it manually are below:

### How to Run SQLFluff

- To lint all SQL files in the project:
	```shell
	sqlfluff lint
	```
- To automatically fix simple issues:
	```shell
	sqlfluff fix
	```

SQLFluff can be configured via the `pyproject.toml` file if you need to customize rules or dialects.

For more details and configuration options, see the [official SQLFluff documentation](https://docs.sqlfluff.com/).


## 💻 VS Code Workspace Configuration (`.vscode` folder)

This repository includes a `.vscode` folder with settings and extension recommendations to streamline development in Visual Studio Code:

- **settings.json**: Configures Python analysis, testing, and environment settings for the workspace. Notable settings:
	- Adds `src/` to the Python import path for easier imports and syntax highlighting.
	- Enables and configures `pytest` for testing.
	- Sets up the default Python interpreter and environment activation.
- **extensions.json**: Recommends useful VS Code extensions. When you open the project, VS Code will prompt you to install these for an optimal experience. This is optional.

You do not need to manually edit these files unless you want to customize your development environment. They help ensure a consistent setup for all contributors.


