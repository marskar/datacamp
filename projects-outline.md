# Creating Robust Python Projects
## Chapter 1: Python project principles
* Lesson 1.1 - Python modules
    * Learning objective: Understand modularization, i.e. why split up code into modules?
    - A **module** is a Python file with that contains function or class definitions. This enables code reusability and encourages separating code into multiple files instead of large monolith programs, e.g. a single [Jupyter notebook](https://jupyterlab.readthedocs.io/en/stable/user/notebook.html) with all code and documentation.
* Lesson 1.2 - Python imports
    * Learning objective: Understand how to import code from various sources
    - Python `import` statement
    - Some fun imports: `import this`, `import antigravity`, `import __hello__`, `from __future__ import braces`
    - Sources: standard library, third party libraries, and user-defined modules
    - Following [PEP8 style guidelines regarding imports](http://pep8.org/#imports)
    - Importing all functions from a module and using it as a name space, e.g. `import pandas`
    - Aliasing, e.g. `import pandas as pd`
    - Importing multiple individual functions at once, e.g. `from os import listdir, system`
* Lesson 1.3 - Python packages
    * Learning objective: Understand packaging, i.e. why distribute data science projects in the form of packages? Sharing code, reproducibility, projects will not gain traction unless the code is easily available and well documented, popular projects can inspire others to contribute.
    - Data science projects can easily be turned into packages.
    - Imports in the context of packages, absolute versus relative imports
    - The `__init__.py` file to 1) enable `from pkg import *` by defining `__all__` and 2) make top-level imports easier.
## Chapter 2: Beyond `.py` and `.ipynb`: Python projects are more than just code files!
* Lesson 2.1 - Directed Acyclic Graphs (DAGs)
	* Learning objective: Conceptualize and visualize a data analysis in the form of a [directed acyclic graph (DAG)](https://en.wikipedia.org/wiki/Directed_acyclic_graph). For example, use `networkx` to create a plot of [data cleaning](https://github.com/marskar/nhanes/blob/4022bd25b4baa82af56f25f6b02fd7759b1ee88a/img/nhanes-data-cleaning.png) and [analysis](https://github.com/marskar/nhanes/blob/4022bd25b4baa82af56f25f6b02fd7759b1ee88a/img/nhanes-data-analysis.png). A data analysis flows from start to finish, otherwise it would never end!
* Lesson 2.2 - Documentation
	* Learning objective - Understand that importance of good documentation.
    - Write in Markdown and optionally convert into ReStructuredText (rst) to generate HTML pages using [sphinx](http://www.sphinx-doc.org/en/master/) and take advantage of the free hosting provided by [readthedocs](readthedocs.org).
    - Include the DAG created earlier in the documentation to help communicate the data analysis.
* Lesson 2.3 - Reporting with pandoc and pypandoc
	* Learning objective - Learn to generate reports and slideshows from files used for documentation
    - Learn how the pypandoc Python package can convert files to various output formats, e.g. HTML and PDF.
    - Use the markdown from the previous lesson to create an HTML report.
    - Instead of pypandoc in a python environment, we can use pandoc at the command line.
    - Use pandoc to create slides that explain the goals, methods, and results of our analysis.
## Chapter 3 - Shell superpowers
- Lesson 3.1 - The shell environment
    - Learning objective: Understand that differences between shell and python environments.
    - Python and shell scripting can be done interactively in the terminal.
    - The Python interpreter prompt is `>>>`, while the default shell prompt is `$`. For comparison, the R prompt is `>`
    - Installation of Python packages is typically done in a shell environment, in contrast to the `install.packages()` function in R.
    - While installation can be done using a graphical user interface (GUI), e.g. Anaconda Navigator or PyCharm, the shell can do many things GUIs can't.
- Lesson 3.2 - Package installation
    * Learning objective: Understand the Python packaging ecosystem, i.e. how can my code fit into the grander scheme of things?
    - Two main ways to install packages: `conda` and `pip`
    - The best explanation is by Jake VanderPlas: `pip` installs Python packages in any environment, `conda` installs any package in `conda` environments.
    -  [PyPI](https://pypi.org/) and `pip` versus [conda-forge](https://conda-forge.org/) and `conda`
    - Introduce the capstone: deploy a data science project as a package to PyPI.
* Lesson 3.3 - Automation
    * Learning objective - Plan out a data analysis and avoid repetitive tasks by using an automation tool called [GNU Make](https://www.gnu.org/software/make/).
    - Building on the concept of DAGs, data analyses can be turned in pipelines.
    - All of the steps in a pipeline can be executed with a single command.
    - GNU Make also skips source files that have not been updated since the last time `make` was invoked, thus avoiding needless computation.
    - Edit a `Makefile` for the project and then invoke `make` to generate the report and slides from the previous chapter.
    - The syntax of GNU Make is different than that of Python. Makefiles are similar to shell scripts.
* Lesson 3.4 - Python project templates
    * Learning objective: Understand the structure and individual components of a typical Python project.
    - Instead of creating projects from scratch, it is better to use a [cookiecutter](https://cookiecutter.readthedocs.io/en/latest/) template.
    - Their are many existing templates, e.g. for web development there is [cookiecutter-django](https://github.com/pydanny/cookiecutter-django). We will use the [cookiecutter for data science template](https://drivendata.github.io/cookiecutter-data-science/).
    - Explore the structure below.
```
├── LICENSE
├── Makefile           <- Makefile with commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default Sphinx project; see sphinx-doc.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.py           <- Make this project pip installable with `pip install -e`
├── src                <- Source code for use in this project.
│   ├── __init__.py    <- Makes src a Python module
│   │
│   ├── data           <- Scripts to download or generate data
│   │   └── make_dataset.py
│   │
│   ├── features       <- Scripts to turn raw data into features for modeling
│   │   └── build_features.py
│   │
│   ├── models         <- Scripts to train models and then use trained models to make
│   │   │                 predictions
│   │   ├── predict_model.py
│   │   └── train_model.py
│   │
│   └── visualization  <- Scripts to create exploratory and results oriented visualizations
│       └── visualize.py
```

## Chapter 4 - Deploying to PyPI
* Lesson 4.1 - Installing a local project
    * Learning objective: Become proficient in the steps needed to pip install a local project
    - The `setup.py` file allows us to do many things, such as install our project so that we can use the code everywhere.
    - Replace the fields in the `setup.py` template and then run `pip install -e .` (or `python setup.py install`) at the command line.
    - Now we can use our code everywhere on our computer, including outside the project.
    - This is useful to test the project before deploying to PyPI.
- Lesson 4.2 - Making scripts command line executable
    * Learning objective: Understand the advantages of scripts that can be used in both Python and shell environments
    - The `argparse` module from the standard library
    - The shebang (`#!`) and `usr/bin/env python`
    - The `chmod` command
    - The `if __name__ == '__main__':` statement
    - The `entry_points` dictionary in `setup.py`
* Lesson 4.3 - Deployment to PyPI
	* Learning objective - Become proficient in the steps required to publish a project to the Python Package Index (PyPI).
    - `pip` install necessary packages
    - create source archive and built distribution files
    - upload to TestPyPI
    - install the project from TestPyPI
    - confirm that the project code works as expected
    - uninstall the project
    - upload to PyPI
    - install the project from PyPI and test again
    - Now anyone with an internet connection and a computer can `pip` install our code!
