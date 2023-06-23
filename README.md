# gen-ai-apps
Generating applications using generative AI.


## Setting up repository in local

This repository uses [Poetry](https://python-poetry.org/docs/) for managing package dependencies and publishing packages.

- cd to this repository directory

- `pip install poetry`

- To ensure that virtual env. folder is created in the project folder itself, run `poetry config virtualenvs.in-project true` in your terminal

- `poetry shell` to activate the virtual environment in your project directory

- `poetry install --with dev` to install all the package dependencies along with the `dev` group dependencies

- `poetry run python -m ipykernel install --user --name=gen_ai_apps_kernel` to create a Jupyter kernel


## Adding new dependencies

Run `poetry add <library name>`. This will add the dependency to the `pyproject.toml` file, download the dependency and update the lock file. Please commit both the `pyproject.toml` and `poetry.lock` files after adding a new dependency.

By default, poetry will try to find the most up-to-date version compatible with other dependencies. If you need a specific version, you can request it. e.g. `poetry add numpy=1.24.1`. See this [page](https://python-poetry.org/docs/basic-usage/#version-constraints) for documentation on supported version constraints.


## Pre-commit hooks

The repository relies on pre-commit hooks to enable few automated checks like:

- formatting and linting using `black`

- trailing-whitespace

- and many others


These pre-commit hooks are automatically triggered every time before you commit any changes to the repository. If you want to manually run these pre-commit hooks, you can try these commands:

- `pre-commit run --all-files` to run these hooks on all the files in your repository

- `pre-commit run --files file1.py file2.py etc.py` to run on specific files

