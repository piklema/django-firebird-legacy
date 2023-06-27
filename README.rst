===============
django-firebird-legacy
===============

Firebird SQL legacy (2.X) backend for django >= 4
-------------------------------

This is a **FORK** of django-firebird (https://github.com/maxirobaina/django-firebird) database backend that allows to work with old firebird versions (2.x) with newer versions of a django (4.x).

This version is based on this work https://github.com/maxirobaina/django-firebird/pull/134 but firebird driver is reverted to older version as newer firebird-driver does not support firebird 2.x.

This version of django-firebird-legacy is working with old *fbd* (https://pypi.org/project/fdb/) driver instead of newer *firebird-driver* (https://github.com/FirebirdSQL/python3-base), therefore it will work only with firebird 2.x.
The current master branch of this repository is being developed under django 4.x.


Requirements
------------
  * Python 3.x
  * Django 4.x
  * fdb (https://pypi.python.org/pypi/fdb/)

Installation
------------

**Using pip from git repository**

  pip install git+https://github.com/piklema/django-firebird-legacy

Configuration
-------------

Modify your setting.py ::

    DATABASES = {
        'default': {
            'ENGINE' : 'django.db.backends.firebird',
            'NAME' : '/var/lib/firebird/3.0/data/django_firebird.fdb', # Path to database or db alias
            'USER' : 'SYSDBA',           # Your db user
            'PASSWORD' : '*****',    # db user password
            'HOST' : '127.0.0.1',        # Your host machine
            'PORT' : '3050',             # If is empty, use default 3050
            'OPTIONS' : {'charset':'ISO8859_1'}
        }
    }

Known bugs and issues
---------------------

* Some database migrations doesn't work by default. Sometimes is better make intermediate migrations for solve problems.
* Some Query Expressions doesn't work by default. We need to make some workaround, ie: Use Cast().
* Combined duration expressions need more research. No all combination of expressions works.


Contributing
------------

Code and issues is in GitHub:

    https://github.com/piklema/django-firebird-legacy

