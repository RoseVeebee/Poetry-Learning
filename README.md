# PoetryLearning
Requirements:
* Python
* pip
* Poetry

# Purpose of project
Wanted to learn to use Poetry. Project contains a very simple dev pkg `mypkg` showing how an installed dev pkg uses the venv setup by Poetry. See [#Usage of Project](#usage-of-project).

I started down the venv rabbit-hole a few weeks ago with virtualenv, followed by Pipenv, and now Poetry.

My main reason for using Poetry over Pipenv & virtualenv: Poetry utilizes `pyproject.toml`, which is steadily becoming more mainstream because it groups global project settings into one file.

# Usage of project
1. Activate `poetry shell` in project root.
2. `poetry install`
3. Run `./main.py` > calls function in mypkg
> Run `poetry install` after Git pulls to ensure stable venv state.

# Structure of project
* src layout: pkg(s) to dev in `./src/`
* .venv using Poetry
* `pyproject.toml` w/ basic project setup. Additionally, `pyprojectTEST.toml` is a .toml I used to learn Poetry.
* .gitignore = [GitHub .gitignore template for Python](https://github.com/github/gitignore/blob/4488915eec0b3a45b5c63ead28f286819c0917de/Python.gitignore) w/ following change(s):
    * Changed `.venv` to `.venv/*` + `!.venv/.gitkeep`. With default behavior, this forces Pipenv to use `./.venv/` to house venv, instead of default venv location on user's system.
    * Commented out `dist\` in to allow whl & sdist to be included for demo purposes.
* ^ `./dist/`holds `mypkg` whl & sdist. Can be installed to show how src layout forces dev to use installed version of pkg: changing code in `./src/mypkg/` won't impact installed mypkg version.
