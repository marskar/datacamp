
After Twine is installed, we can open the Terminal (Alt+F12) and run twine register dist/pad-on-left-1.0.0.tar.gz -r testpypi and then twine upload dist/* -r testpypi. If these commands executed correctly, you should be able to find your package on testpypi.

If everything looks good on testpypi, you can run the same commands without -r testpypi:

twine register dist/pad-on-left-1.0.0.tar.gz
twine upload dist/*

And after those commands completed successfully, you’ve uploaded your package to PyPI! Congratulations!
