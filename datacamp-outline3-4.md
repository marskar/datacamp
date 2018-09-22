## Chapter 3 - Project best practices: Version control, reproducibility, virtual environments, and pickles
* Lesson 3.1 - Version control with git
	* Learning objective - How to use git to version control project files.
* Lesson 3.2 - Dependency management for reproducibility
	* Learning objective - How to install specific versions of packages, freeze versions of dependencies, upgrade dependencies using `pip` or `conda`.
- Lesson 2.3 - Package dependencies
    - Reproducibility
    - Standardizing dependencies with `requirements.txt` and `pip`, or `environment.yml` in the case of `conda`.
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
