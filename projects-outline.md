# Creating Robust Python Projects
## Chapter 1: Python project principles
* Lesson 1.1 - Python modules
    * Learning objective: Understand modularization, i.e. why split up code into modules? Python `import` statement, code reusability, avoiding monolith programs, e.g. a single [Jupyter notebook](https://jupyterlab.readthedocs.io/en/stable/user/notebook.html) with all code and documentation.
* Lesson 1.2 - Python packages
    * Learning objective: Understand packaging, i.e. why distribute data science projects in the form of packages? Sharing code, reproducibility, projects will not gain traction unless the code is easily available and well documented, popular projects can inspire others to contribute.
* Lesson 1.3 - Python ecosystem
    * Learning objective: Understand the Python packaging ecosystem, i.e. how can my code fit into the grander scheme of things? [PyPI](https://pypi.org/) and `pip` (with a nod to [conda-forge](https://conda-forge.org/) and `conda`), installing packages with `pip`, standardizing dependencies with `requirements.txt`, or `environment.yml` in the case of `conda`.
## Chapter 2: Beyond `.py` and `.ipynb`: Python projects are more than just code files!
* Lesson 2.1 - Directed Acyclic Graphs (DAGs)
	* Learning objective: Conceptualize and visualize a data analysis in the form of a [directed acyclic graph (DAG)](https://en.wikipedia.org/wiki/Directed_acyclic_graph). For example, use `networkx` to create a plot of [data cleaning](https://github.com/marskar/nhanes/blob/4022bd25b4baa82af56f25f6b02fd7759b1ee88a/img/nhanes-data-cleaning.png) and [analysis](https://github.com/marskar/nhanes/blob/4022bd25b4baa82af56f25f6b02fd7759b1ee88a/img/nhanes-data-analysis.png). A data analysis flows from start to finish, otherwise it would never end!
* Lesson 2.2 - Automation
    * Learning objective - Plan out a data analysis and avoid repetitive tasks by using an automation tool called [GNU Make](https://www.gnu.org/software/make/). Building on the concept of DAGs, data analyses can be turned in pipelines. All of the steps in a pipeline can be executed with a single command. GNU Make also skips source files that have not been updated since the last time `make` was invoked, thus avoiding needless computation.
* Lesson 2.3 - Documentation
	* Learning objective - Understand that importance of good documentation. Write in Markdown and optionally convert into ReStructuredText (rst) to generate HTML pages using [sphinx](http://www.sphinx-doc.org/en/master/) and take advantage of the free hosting provided by [readthedocs](readthedocs.org).
* Lesson 2.4 - Python project templates
    * Learning objective: Understand the structure and individual components of a typical Python project. To get started quickly, use a [cookiecutter](https://cookiecutter.readthedocs.io/en/latest/) template such as the [cookiecutter for data science template](https://drivendata.github.io/cookiecutter-data-science/) below.
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
## Chapter 3 - Project best practices: Version control, reproducibility, virtual environments, and pickles
* Lesson 3.1 - Version control with git
	* Learning objective - How to use git to version control project files.
* Lesson 3.2 - Dependency management for reproducibility
	* Learning objective - How to install specific versions of packages, freeze versions of dependencies, upgrade dependencies using `pip` or `conda`.
* Lesson 3.3 - Virtual environments
	* Learning objective - Understand why we should use virtual environments and a dependency manager. There are (too) many options for virtual environments, including `virtualenv`, `pipenv`, `conda`, and `venv`. The [official Python tutorial](https://packaging.python.org/tutorials/installing-packages/#creating-virtual-environments) describes `venv` and `virtualenv`, but [recommends](https://packaging.python.org/tutorials/installing-packages/#creating-virtual-environments) `pipenv` as a "higher level tool that automatically manages a separate virtual environment for each project and application". Notably, `conda` is both an environment and dependency manager that integrates with the `pip` dependency manager. This lesson will show how dependencies can be standardized in each environment using a `requirements.txt` file, or `environment.yml` for `conda` environments.
* Lesson 3.4 - Pickles for serialization
	* Learning objective - Understand serialization, i.e. why `pickle` a Python object? After training a model, it can be serialized, stored as a stream of bytes, using `pickle`. In the `cookiecutter` for data science template, serialized models are stored in the `models` folder. Later, the model can be unpickled and use again without the need to retrain.
## Chapter 4 - Wrapping up - Reporting, testing and deployment
* Lesson 4.1 - Jupyter Notebooks
	* Learning objective - Create [Jupyter notebook](https://jupyterlab.readthedocs.io/en/stable/user/notebook.html) Notebooks from `.py` and `.md` files using `nbconvert` and `nbformat`. R Markdown can also support python code and be used to generate reports.
* Lesson 4.2 - Slideshows
	* Learning objective - Generate slideshows in various formats (e.g. HTML) using `pandoc`, the `rmarkdown` R package, and `jupyter nbconvert`.
* Lesson 4.3 - Testing
	* Learning objective - Learn to introduce tests using `unittest`, `doctest`, and `pytest` into the workflow of a Python data science project.
* Lesson 4.4 - Deployment to PyPI and continuous integration with Travis
	* Learning objective - Follow the steps required to publish a project to the Python Package Index (PyPI). Additionally, tools like Travis can be used to automate running tests and deploying projects.