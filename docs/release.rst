Release Guidelines
~~~~~~~~~~~~~~~~~~

This document explains how to release an app
maintained on https://github.com/yourlabs

Tests
=====

Ensure all tests pass on all platforms, use travis-ci for
that purpose.

Version bump
============

Update the version number in ``docs/(source/)?conf.py``
and setup.py, eventually in ``module_root/__init__.py``
if it defines a ``VERSION`` string.

Add new authors to ``AUTHORS``, in alphabetical order.

Update ``CHANGELOG``.

Build the package::

    python setup.py sdist

Check that the package looks ok, it should be in ``build/``.

Upload the package on PyPi::

    python setup.py sdist upload

Tag the release with git tag, upload the tag, ie.::

    git tag 2.0.4
    git push origin 2.0.4

Thanks for your help !
