# Python Flask CRUD App

This is a straight-forward CRUD application that contains authentication, and adding, deleting, and editing articles.
The backend code is in Python with Flask as the web framework. The database is using MySQL.

The purpose of this project is to learn Flask by creating a full-stack application and practice Python along the way.

## Dependencies

Check if `pip` is stalled (Python package manager):

`python -m pip --version`, then install flask using:
`pip install Flask`

## Boilerplate Setup

```sh
from flask import Flask

app = Flask(__name__)


if __name__ == '__main__':
    app.run(host="localhost", port=8000, debug=True)
```

- I tried to run app with `python app.py`, but kept getting error: `OSError: [Errno 48] Address already in use`
- Used command `ps -fA | grep python` to check ports being used, but after using `kill` command, and no other ports being used, error remained
- Specified `port=8000` to resolve issue

## Routes

Creating routes follows this flow:

```sh
@app.route('/')
def index():
    return render_template('home.html')
```

HTML use Jinja syntax to render pages like this:

```sh
{% extends 'layout.html' %}

{% block body %}
<div class="jumbotron text-center">
	<h1>Welcome to FlaskApp</h1>
	<p class="lead">This application is built on the Python Flask framework.</p>
</div>

{% endblock %}
```
