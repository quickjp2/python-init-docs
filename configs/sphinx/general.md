# Common Sphinx stuffs

## Helpful links

- [Sphinx Homepage](https://www.sphinx-doc.org/en/master/)
- [Sphinx RTD tutorial](https://sphinx-rtd-tutorial.readthedocs.io/en/latest/sphinx-quickstart.html)

## Install Sphinx

`pipenv install --dev sphinx, sphinx-rtd-theme, sphinxcontrib-napoleon`

## Building the docs

- Build the base docs: `pipenv run sphinx-apidoc -o ./source ../scripts`
- Clean the build: `pipenv run make clean`
- Build the HTML: `pipenv run make html` OR `pipenv run sphinx-build -b html source build`
