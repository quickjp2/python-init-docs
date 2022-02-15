# python-init-docs

Documentation about best practices for how to setup various python projects

Some of these are "best practices" for my own personal coding style or what I have found to be time-saving.

## General thoughts

- Use `pipenv` for module and virtual env management. This makes it easier for pushing code into a production env consistently
- Use typing! Yea, it's not enforced, but it's really helpful!

## General modules

These are modules to help develop a project, and should be installed via `--dev`

### Testing

- pylint
- pytest
- pytest-cov

### Documenting

For easy install see [install string](configs/sphinx/general.md#install-sphinx).\
[Preferred Docstring Style Example](https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html)

- sphinx
- sphinx-rtd-theme
- sphinxcontrib-napoleon

## Basic folder structure

```bash
repo_root
├─ docs/
│  ├─ build
│  ├─ make.bat
│  ├─ Makefile
│  └─ source
├─ LICENSE
├─ README.md
├─ Pipfile
├─ tests/
│  └─ tests.py
├─ app_name/
|  └── driver.py
└─ setup.py
```
