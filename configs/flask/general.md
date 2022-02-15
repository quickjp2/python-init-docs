# Common flask stuffs

## Helpful link

- [Tutorial](https://flask.palletsprojects.com/en/2.0.x/tutorial/)
- [Packaging](https://packaging.python.org/en/latest/tutorials/packaging-projects/)
- [Testing flask projects](https://flask.palletsprojects.com/en/2.0.x/tutorial/tests/)

## Install Flask

`pipenv install flask`

## Flask Repo config

NOTE: `__init__.py` replaces `driver.py`, as it will define the app object and other files will build on that

```bash
repo_root
├─ setup.py
├─ MANIFEST.in # used to package additional data
└─ app_name/
   ├─ __init__.py
   ├─ templates/ # Where HTML templates are stored
   |  └─ base.html/ # base html for other templates to extend
   └─ static/ # Where static JS or CSS files are stored
      └─ style.css
```

## Usage patterns

- Use [blueprints, views](https://flask.palletsprojects.com/en/2.0.x/tutorial/views/), and [templates](https://flask.palletsprojects.com/en/2.0.x/tutorial/templates/)

## Running in prod

- Run using [waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/)
  - `pipenv install waitress`
  - `waitress-serve --call 'app_name:create_app'`
