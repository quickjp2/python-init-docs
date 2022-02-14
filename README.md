# python-init-docs

Documentation about best practices for how to setup various python projects

Some of these are "best practices" for my own personal coding style or what I have found to be time-saving.

## General thoughts

- Use `pipenv` for module and virtual env management. This makes it easier for pushing code into a production env consistently

## General modules

These are modules to help develop a project, and should be installed via `--dev`

- pylint
- pytest
- pytest-cov
- sphinx
- sphinx-rtd-theme
- sphinxcontrib-napoleon

## Basic folder structure

```bash
repo_root
├─ docs
│  ├─ build
│  ├─ make.bat
│  ├─ Makefile
│  └─ source
├─ LICENSE
├─ README.md
├─ Pipfile
├─ tests
│  └─ tests.py 
└─ src
   └── driver.py
```

## Helpful links
- [Sphinx Homepage](https://www.sphinx-doc.org/en/master/)
- [Sphinx RTD tutorial](https://sphinx-rtd-tutorial.readthedocs.io/en/latest/sphinx-quickstart.html)
- [Preferred Docstring Style Example](https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html)
- [Enabling Style for Sphinx](https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html)
