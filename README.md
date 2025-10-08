
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
  - [📝 Licence](#-licence)
  - [Using `UV`](#using-uv)
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


## 📝 Licence
MIT Licence, see `LICENSE`


## Using `UV`

 If `UV` is not already installed, then use these steps to install it

 * First, install `UV`. Up to date documentation regarding the installation and use of `UV` can be found here: [UV docs link](https://docs.astral.sh/uv/) (`pip install UV` into your base environment is not best practice but works quite well)
 * There is an additional step which allows UV to use the SSL certificates for your system. An environmental variable has to be added: `UV_NATIVE_TLS=true`
   * **Option 1:** To do this in a Powershell terminal type:
     ```powershell
     [Environment]::SetEnvironmentVariable("UV_NATIVE_TLS", "true", "User")
     ```
   * **Option 2:** This can also be added in Windows:
     * search for 'environment variables' in the Windows search bar and then click on 'Edit the environmental variables for your account'.
     * Click 'New' and use `UV_NATIVE_TLS` in the 'Variable name' field and `true` in the 'Variable value' field
     * Click 'OK'
 * Disable automatic python downloads:
     * By default, UV will download versions of python as required. We want to prevent this behaviour so that it only uses python installations that have been installed through a secure software system.
     * These lines have been added to the `pyproject.toml`, but make sure they are present:
         ```toml
         [tool.uv]
         python-downloads = "never"
         pyton-preference = "only-system"
         ```
 * Force UV to install packages through an internal PyPI repository (e.g. ONS Artifactory):
     * Option 1: To achieve this system wide, add an environmental variable containing the url to the PyPI repository (for ONS Artifactory this includes your username and password). To do this for ONS Artifactory, type this into a powershell terminal:
         ```powershell
         [Environment]::SetEnvironmentVariable("UV_INDEX_URL", "https://<Windows-username>:<hashed-Artifactory-password>@onsart-01/artifactory/api/pypi/yr-python/simple", "User")
         ```
         provide your personal windows-username and hashed-Artifactory-password. These can be found in the pip.ini file on your system. Documentation for finding your hashed password can also be found [here](https://gitlab-app-l-01/ASAP/coding-getting-started-guide/-/wikis/Artifactory)
    * Option 2: To set this up in your repository only, add this to the `pyproject.toml` file (this is another ONS Artifactory example):
        ```toml
        # Point UV to the internal PyPI repository
        [[tool.uv.index]]
        url = "https://<Windows-username>:<hashed-Artifactory-password>@onsart-01/artifactory/api/pypi/yr-python/simple"
        default = true

        # ignore SSL checks when using artifactory.
        # this is a temporary fix as an issue arose when using UV and pointing it towards artifactory
        [tool.uv]
        allow-insecure-host = ["https://onsart-01/artifactory/api/pypi/yr-python/simple"]

        ```    


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


