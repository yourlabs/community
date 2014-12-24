Release Guidelines
~~~~~~~~~~~~~~~~~~

This document explains how to release an app
maintained on https://github.com/yourlabs

``[ci skip]`` in commit messages to save Travis-ci
==================================================

Travis-ci gratefully runs our tests. If a commit doesn't change
any code, it should contain ``[ci skip]`` in the commit message so
that it doesn't trigger travis-ci build which takes quite a while
- let's be good neighbours.

``tests/`` needs new tests for new bugfix and feature
=====================================================

``tests/`` should contain new unit tests for new features and regression tests
for bugfixes

Ensure all tests pass on all platforms, use travis-ci for
that purpose.

``docs/`` needs love
====================

Ensure all supported feature is documented in the ``docs/source/``
directory.

``CHANGELOG`` should describe the release changes
=================================================

Ensure that the ``CHANGELOG`` file is up to date, use ``git log``
to double check the consistency between ``CHANGELOG`` and git.

``AUTHORS`` should be legally valid
===================================

Welcome to ``AUTHORS``, contributors are listed in alphabetical
order, use ``git log`` to double check the author list since last
version bump.

Version bump: update the version number in the following files
==============================================================

``docs/(source/)?conf.py``
--------------------------

Update the version number in ``docs/(source/)?conf.py``.

``setup.py``
------------

Update the version number in ``setup.py``.

``cities_light/__init__.py``
----------------------------

If releasing ``django-cities-light``, update the ``VERSION``
variable in ``cities_light/__init__.py``.

``python setup.py sdist``
-------------------------

Build the package::

    python setup.py sdist

Check resulting ``build/``
--------------------------

Check that the package looks ok, it should be in ``build/``.

Upload on PyPi ``python setup.py sdist upload``
-----------------------------------------------

Upload the package on PyPi::

    python setup.py sdist upload

``git tag``
-----------

Tag the release with git tag, ie.::

    git tag 2.0.4

``git push origin <version>``
-----------------------------

Upload the tag, ie::

    git push origin 2.0.4

Thanks for your help !
