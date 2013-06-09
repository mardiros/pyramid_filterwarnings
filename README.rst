pyramid_filterwarnings
======================

Getting Started
---------------

The aim of this project is to provide a generic way to configure python
`warnings.filterwarnings_`.
Python warnings can be configured via Environment variable, Python interpreter
argument, or directly in the code. This plugin provides to Pyramid application
a clean way to configure the warning level via its configuration file.


Configuration
-------------

Set the pyramid_filterwarnings plugin from in the Pyramid ini file then configure
the level.

::

    pyramid.includes =
        ... your other plugins ...
        pyramid_filterwarnings

    # configure the warning level, default is ignore
    filterwarnings.level = ignore


It is also possible to set category_, module and message, and do many rules.

::

    # Other optionals configurations keys
    # filterwarnings.category = DeprecationWarning
    # filterwarnings.module = pyramid\..*

    # Add other rules
    filterwarnings.1.category = DeprecationWarning
    filterwarnings.1.module = sqlalchemy\..*
    filterwarnings.1.level = notice

    filterwarnings.2.category = Warning
    filterwarnings.2.module = pyramid\..*
    filterwarnings.2.level = ignore

    # and more if necessary...


.. _warnings.filterwarnings: _http://docs.python.org/2/library/warnings.html#warnings.filterwarnings
.. _category: _http://docs.python.org/2/library/warnings.html#warning-categories

