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

Pre-release mandatory tests with GitHub and Travis-ci
=====================================================

It is important that all tests jobs pass in Travis. If a job in the matrix
fails then read the logs of the job and eventually restart the job - you'll
need to login with your github account on travis for that.

For example, if a test job runs a test server + selenium in a thread then it'll
be a bit resource hungry, the job might fail because "Timed out while waiting
for window to load". This is a typical case where we'd like to restart a job on
travis.

``git tag``
-----------

Tag the release with git tag, ie.::

    git tag 2.0.4

``git push origin <version>``
-----------------------------

Upload the tag, ie::

    git push origin 2.0.4

Wait for Travis
---------------

Once all tests pass on travis then it's time to propagate on PyPi.

``python setup.py sdist``
-------------------------

Build the package::

    python setup.py sdist

Check resulting ``build/``
--------------------------

Check that the package looks ok, it should be in ``build/``.

Test it in a virtualenv in ``/tmp/testenv``
-------------------------------------------

Might help finding final bugs.

Upload on PyPi ``python setup.py sdist upload``
-----------------------------------------------

Upload the package on PyPi::

    python setup.py sdist upload

Thanks for your contribution !
==============================

It's beyond my control: "l'outil appartient à celui qui le travaille" means
"the tool belongs to whom works it".
