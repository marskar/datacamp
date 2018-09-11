# Capstone Exercise

## Exercise
You've come a long way on your path to Python project proficiency.

The final step in your journey is to deploy your project to the [Python Package Index `PyPI`](https://pypi.org/)!

First, we will do a practice run by publishing the project to [TestPyPI](https://packaging.python.org/guides/using-testpypi/).

By following the steps below, you can make your project code `pip` installable!

## Instructions
To proceed, we will first need to pip install `setuptools`, `wheel`, and `twine`.

Next, run `setup.py` in the terminal, passing it two arguments (`sdist` and `bdist_wheel`).

This created a new directory called `dist`. The `dist` directory contains two different flavors of installation files.
The `tar.gz` file is a source archive, whereas the `.whl` file is a built distribution of our project. You can make these files separately by running `setup.py` with only argument, `sdist` to make a `tar.gz` file or `bdist_wheel` for a `.whl` file.

We will make both of these files available on TestPyPI by running `twine upload` on `dist/*` with the `--repository-url https://test.pypi.org/legacy/` argument.

Now, test whether our project was successfully uploaded by trying to `pip` install the project. This will be a normal pip installation followed by `--index-url https://test.pypi.org/simple/`

If the project installed correctly, you can now publish to PyPI and test that it worked by running `twine upload` and `pip install` as above, but without specifying a url (the default url is PyPI!).

Congratulations! You’ve uploaded your project to PyPI!

## `pypi.sh`

```python
# install necessary packages
pip install ______
# create source archive and built distribution files
python setup.py ______
# upload to TestPyPI
twine upload ______
# install the project from TestPyPI
pip install ______
# upload to PyPI
twine upload ______
# uninstall the project
pip uninstall ______
# install the project from PyPI
pip install ______
print('Congratulations! You deployed your project to PyPI!')
```
