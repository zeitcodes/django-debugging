Django Debugging
================

Django debugging makes it easier to debug your app during development. Currently it contains the runserver_plus functionality from the project [django-extensions](https://github.com/django-extensions/django-extensions "Django Extensions").

Installation
------------

Run `pip install hg+https://bitbucket.org/nextscreenlabs/django-debugging`

If you are using the package from source you will need to install [Werkzeug](http://werkzeug.pocoo.org/) manually.

Add `django-debugging` to your `INSTALLED_APPS` setting:

```python
INSTALLED_APPS = (
    ...
    'django_debugging',
)
```

Getting Started
---------------

To get started use the `runserver_plus` command instead of `runserver`. All `runserver` options will work with `runserver_plus`.

```
$ python manage.py runserver_plus

* Running on http://127.0.0.1:8000/
* Restarting with reloader...

Validating models...
0 errors found

Django version 1.4.1, using settings 'mysite.conf.settings'
Development server is running at http://127.0.0.1:8000/
Using the Werkzeug debugger (http://werkzeug.pocoo.org/)
Quit the server with CONTROL-C.
```

Usage
-----

Werkzeug displays its own traceback page instead of Django's normal traceback page.

It has two options:

###View Source
You can expand and the view the source of each line in the traceback.

###Interactive Console Debugger
Lets you evaluate python expressions in the browser with the context being same as the line in the traceback. Use it to print values, assign variables, or run functions. (*Warning:* This is extremely insecure and should never be run and a production server.)