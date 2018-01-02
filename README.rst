==================
Cookiecutter PyLib
==================

Cookiecutter_ template for a Python PyPI ready package library, extends upon `audreyr/cookiecutter-pypackage`_

Instead of hacking boilerplate setup you can jump to coding immediately. All the check are already in place and a your package can be nicely released to pypi.


* GitHub repo: https://github.com/wooyek/cookiecutter-pylib/
* Documentation: https://cookiecutter-pylib.readthedocs.io/
* Free software: BSD license

.. image:: https://travis-ci.org/wooyek/cookiecutter-pylib.svg
    :target: https://travis-ci.org/wooyek/cookiecutter-pylib
    :alt: Linux build status on Travis CI

.. image:: https://ci.appveyor.com/api/projects/status/github/wooyek/cookiecutter-pylib?svg=true
    :target: https://ci.appveyor.com/project/wooyek/cookiecutter-pylib/
    :alt: Windows build status on Appveyor

.. image:: https://readthedocs.org/projects/cookiecutter-pylib/badge/?version=latest
    :target: http://cookiecutter-pylib.readthedocs.io/en/latest/
    :alt: Documentation build status

.. image:: https://api.codeclimate.com/v1/badges/907a4f5f3e624e0a9cd8/maintainability
   :target: https://codeclimate.com/github/wooyek/cookiecutter-pylib/maintainability
   :alt: Maintainability

.. image:: https://img.shields.io/github/license/wooyek/cookiecutter-pylib.svg
    :target: https://github.com/wooyek/cookiecutter-pylib/
    :alt: License

.. image:: https://img.shields.io/twitter/url/https/github.com/wooyek/cookiecutter-pylib.svg?style=social
    :target: https://twitter.com/intent/tweet?text=Wow:&url=https%3A%2F%2Fgithub.com%2Fwooyek%2Fcookiecutter-pylib
    :alt: Tweet about this project

.. image:: https://img.shields.io/badge/Say%20Thanks-!-1EAEDB.svg
    :target: https://saythanks.io/to/wooyek


Features
--------

* Testing setup with ``unittest`` and ``python setup.py test`` or ``py.test``
* Travis-CI_: Ready for Travis Continuous Integration testing
* Tox_ testing: Setup to easily test for multiple Python versions
* Sphinx_ docs: Documentation ready for generation with, for example, ReadTheDocs_
* Bumpversion_: Pre-configured version bumping with a single command
* Auto-release to PyPI_ when you push a new tag to master (optional)
* Split file requirements_ management with inheritance and support for private locally installed packages
* Command line interface using Click (optional)
* `Initialization of Git`_ repo, github origin remote and git-flow
* Python `virtual environment bootstrapping`_
* Git master/develop local/origin sync with a single command
* Release_ (sync, test, bump, publish) with a single command

.. _Cookiecutter: https://github.com/audreyr/cookiecutter
.. _requirements: https://github.com/wooyek/cookiecutter-pylib/tree/master/%7B%7Bcookiecutter.project_slug%7D%7D/requirements
.. _Initialization of Git: https://github.com/wooyek/cookiecutter-pylib/blob/master/hooks/post_gen_project.py
.. _virtual environment bootstrapping: https://github.com/wooyek/cookiecutter-pylib/blob/master/hooks/post_gen_project.py
.. _Release: https://github.com/wooyek/cookiecutter-pylib/blob/master/%7B%7Bcookiecutter.project_slug%7D%7D/Makefile

Quickstart
----------

Before we start we need some tooling::

    curl https://raw.githubusercontent.com/mitsuhiko/pipsi/master/get-pipsi.py | python
    pipsi install cookiecutter
    pipsi install detox
    pipsi install pew
    pipsi install vex
    pipsi install pipenv
    pip install "backports.shutil_which ; python_version < '3.4'"

Now we can generate and initialize a Django app package project::

    cookiecutter https://github.com/wooyek/cookiecutter-pylib.git

You'll be prompted for some infomation, based on your choices cookiecutter create a directory that is your new package.

This directory should contain fully initialized project. Empty but passing tests and ready to be pushed and released.

Post generation provisioning
----------------------------

* Activate virtual environemnt and run tests with ``tox``
* Create a repo on Github (or Bitbucket)
* Add the repo to your Travis-CI_ account.
* Add the repo to your ReadTheDocs_ account + turn on the ReadTheDocs service hook.
* Update `requirements/base.txt` file that specifies the packages you will need for
  your project and their versions. For more info see the `pip docs for requirements files`_.

For more details, see the `cookiecutter-pylib tutorial`_.

Running Tests
~~~~~~~~~~~~~

Code has been written, but does it actually work? Let's find out!

::

    source .pyvenv/bin/activate
    (pyvenv) $ pip install -r requirements/development.txt
    (pyvenv) $ pytest
    (pyvenv) $ python setup.py test
    (pyvenv) $ tox


Register releasing on PyPI
~~~~~~~~~~~~~~~~~~~~~~~~~~

First make sure you have newest setuptools installed::

    pip install pip setuptools -U

Once you've got at least a prototype working and tests running,
it's time to register the app on PyPI::

    python setup.py register


Time to release a new version and upload it to PyPi? Bam!

    $ make publish

It will sync your local and origin repo, test, increment version number, setup and release package then push to origin master.

.. _Travis-CI: http://travis-ci.org/
.. _Tox: http://testrun.org/tox/
.. _Sphinx: http://sphinx-doc.org/
.. _ReadTheDocs: https://readthedocs.io/
.. _`pyup.io`: https://pyup.io/
.. _Bumpversion: https://github.com/peritus/bumpversion
.. _PyPi: https://pypi.python.org/pypi

.. _`available cookiecutters`: http://cookiecutter.readthedocs.io/en/latest/readme.html#available-cookiecutters
.. _`audreyr/cookiecutter-pypackage`: https://github.com/audreyr/cookiecutter-pypackage/
.. _`ardydedase/cookiecutter-pylib`: https://github.com/ardydedase/cookiecutter-pylib
.. _github comparison view: https://github.com/tony/cookiecutter-pylib-pythonic/compare/audreyr:master...master
.. _`network`: https://github.com/wooyek/cookiecutter-pylib/network
.. _`family tree`: https://github.com/wooyek/cookiecutter-pylib/network/members
.. _`pip docs for requirements files`: https://pip.pypa.io/en/stable/user_guide/#requirements-files
.. _`cookiecutter-pylib tutorial`: https://cookiecutter-pylib.readthedocs.io/en/latest/tutorial.html
