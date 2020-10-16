# Cookiecutter template for starting new modern Python projects

This template allows you to easily setup new Python projects with the most important libraries and configuration files for managing dependencies and virtualenv, code formatting, debugging, testing, static code analysis and creating command-line interfaces.

You can use it as-is or fork and modify according to your preferences.

## What is included in the template

The template will:

- create `pyproject.toml` configuration file for managing project dependencies and virtualenv using [Poetry](https://python-poetry.org/)
- install [typer](https://pypi.org/project/typer/) and [rich](https://pypi.org/project/rich/) packages for creating command-line interfaces which are useful in many types of projects
- install [pysnooper](https://pypi.org/project/PySnooper/) and [stackprinter](https://pypi.org/project/stackprinter/) for better debugging
- install [Pytest](https://docs.pytest.org/en/stable/) and create `pytest.ini` configuration file to point Pytest to `tests/` folder
- install [Pytest-sugar](https://pypi.org/project/pytest-sugar/) plugin for nicer Pytest output
- install [Black](https://black.readthedocs.io/en/stable/) for code formatting
- install [Flake8](https://flake8.pycqa.org/en/latest/) for finding bugs
- install [MyPy](http://mypy-lang.org/) for static type checking and create `mypy.ini` configuration file
- install [pre-commit](https://pre-commit.com/) to run Black, Flake8 checks before every commit
- install [bandit](https://bandit.readthedocs.io/) for security-related checks
- create `README.md` README file
- create `.gitignore` file
- initialize new Git repository


## How to use the template

This is a [cookiecutter](https://cookiecutter.readthedocs.io) template.

To use it, make sure you have at least Python 3.7 and git installed. 

Then install `cookiecutter` and `poetry` via `pip`:

```
pip install poetry --user
pip install cookiecutter --user
```

Then you can create a new Python project by running:

```
cookiecutter https://github.com/stribny/python-new-project
```

This will take you to a project setup asking for:
- `project_name`, the Python package name and name of the project folder
- `project_description`, the Python package description
- `human_name`, the name that will be used in generated README file
- `author`, the author of the package
- `python_version`, the Python version that should be set for the project

The generated structure looks like this:

```
project_name/ 
└────   project_name/ 
   └────   __init__.py  
├────   .flake8  
├────   .git/ 
├────   .gitignore  
├────   mypy.ini  
├────   poetry.lock  
├────   .pre-commit-config.yaml  
├────   pyproject.toml  
├────   pytest.ini  
├────   README.md  
└────   tests/ 
   ├────   __init__.py  
   └────   test_project.py
```

## Configuring MyPy

By default, MyPy will be installed in the project, but not added as a pre-commit hook. This is because
pre-commit would run MyPy in a different virtualenv which will make MyPy unable to pick up your installed 
dependencies. If you want to add MyPy to your pre-commit hook, [read the instructions here](https://github.com/pre-commit/mirrors-mypy).

## Additional resources

- Read the blog post [Starting new modern Python projects](https://github.com/stribny/python-new-project) about this cookiecutter template
- Read [Building command line interfaces in Python](https://stribny.name/blog/2020/01/building-command-line-interfaces-in-python) to see Typer and rich packages in action
- Read [Debugging Python programs](https://stribny.name/blog/2019/06/debugging-python-programs) to see how to use pysnooper and stackprinter for better debugging