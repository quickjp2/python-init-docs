# Common Flask Files

## root __init__.py

```python
import os

from flask import Flask

def create_app(test_config=None):
    # create and configure the app
    app = Flask(__name__, instance_relative_config=True)
    app.config.from_mapping(
        SECRET_KEY='dev',
    )

    if test_config is None:
        # load the instance config, if it exists, when not testing
        app.config.from_pyfile('config.py', silent=True)
    else:
        # load the test config if passed in
        app.config.from_mapping(test_config)

    # ensure the instance folder exists
    try:
        os.makedirs(app.instance_path)
    except OSError:
        pass

    # a simple page that says hello
    @app.route('/hello')
    def hello():
        return 'Hello, World!'

    # pull in blueprints
    # from . import auth, blog
    # app.register_blueprint(auth.bp) # This has a url_prefix
    # app.register_blueprint(blog.bp) # This will be mapped to '/'
    # app.add_url_rule('/', endpoint='index')

    return app
```

## Sample blueprint (auth.py)

```python
import functools

from flask import (
    Blueprint, flash, g, redirect, render_template, request, session, url_for
)

from flaskr.db import get_db

bp = Blueprint('auth', __name__, url_prefix='/auth')

@bp.route('/register', methods=('GET', 'POST')) # will resolve at /auth/register
def register():
    if request.method == 'POST':
        pass # Do something cool for POSTs

    return render_template('auth/register.html') # Reads from the templates folder

@bp.before_app_request
def load_logged_in_user():
    """Get's the user ID if present and passes it to the actual request

    The `before_app_request` annotation tells flask to run this function before processing a request.
    This is for ALL routes registered to the APP, not just the blueprint's routes.
    """
    user_id = session.get('user_id')

    if user_id is None:
        g.user = None
    else:
        g.user = get_db().execute(
            'SELECT * FROM user WHERE id = ?', (user_id,)
        ).fetchone()
```

## Example MANIFEST.in

```python
include flaskr/schema.sql
graft flaskr/static
graft flaskr/templates
global-exclude *.pyc
```
