YourLabs Community Guidelines
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This document explains how to maximize your chances of success when interacting
with YourLabs community (and Open Source in general), particularely in the
context of https://github.com/yourlabs

The purpose of this document is to address the unexpected growth of
contributors (apparently we're almost a hundred now !) and to try to reduce the
time needed to provide effective support and development for our Open Source
apps.

Asking for help
===============

Read `StackOverflow's "How to ask"
<http://stackoverflow.com/help/how-to-ask>`_
guide.

Questions about YourLabs apps should be asked on StackOverflow and be tagged at
least with:

- django
- python
- [app-name], ie. django-autocomplete-light, django-cities-light, etc, etc ...

You may ping the yourlabs mailing list after posting your question.

GitHub issues and pull requests: keep it sharp !
================================================

Please, make only one issue per topic. If you want:

- some fix in some piece of code **and**,
- some fix in some other piece of code

Then please, make two distinct issues, one per topic. Else, chances are that it
will be hard to stay on topic and that appropriate actions are effectively
taken for any of the 2 issues.

Same goes for pull requests ... Which are even more dangerous. We're
benevolents, we work on our apps at night and usually we're tired after our day
of work. If you make it easy for us to make a mistake by merging a PR which
addresses several issues, chances that you're making it easy to make a wrong
release and affect all the community.

Reporting a bug
---------------

Read `How to report a bug effectively
<http://www.chiark.greenend.org.uk/~sgtatham/bugs.html>`_ by Simon
Tatham.

Open an issue on GitHub and feel free to use this template::

    OS Version:
    Python version: 
    Django version:
    App version:
    Database version (if appliable):
    Database driver version (if appliable):
    Browser version (if appliable):

    How to reproduce this bug:

    - 
    - 
    -

    Excepted result:

    Actual result:

Bugs are usually fixed quite fast and published in a maintenance release. But
it's faster with a pull request of course !

Bugfix pull request
-------------------

Bugfix pull requests should:

- be focused on the specific issue, and not include anything un-related to the
  topic,
- hopefully, not break backward compatibility, which means unit tests
  (travis-ci runs them),
- hopefully, not break PEP8 standards, which means pep8 tests (travis-ci again)

Bugfix pull requests, once merged, cause an immediate maintenance release on
PyPi and minor version bump.

Requesting a new feature
------------------------

Now, this is a really touchy subject. **In general**, YourLabs apps which reach
the 1.0.0 version have all the features which it was designed for and no new
feature shall be included in the trunk codebase because James is horrified by
the idea of having to deal with `feature creep
<http://en.wikipedia.org/wiki/Feature_creep>`_. And if you like the
"style" of YourLabs apps, it's probably because of that attitude which is
largely inspired by the `suckless community
<http://suckless.org>`_. So if you'd
like to contribute then you should try to get into that state of mind.

Pull requests for new feature
-----------------------------

**However**, as we firmly believe in Open Source, we believe that we should
share re-useable code. If it makes sense for a YourLabs app to carry your fine
code then it is of course welcome, if it:

- doesn't break backward compatibility,
- is completely optionnal,
- is held in the app's ``contrib`` module, ie.
  ``rules_light.contrib.your_awesome_feature``.

Do **not** assume that your feature will be accepted directly into the core
(outside ``contrib``) before it has been discussed and agreed on by a core developer.

You should **not** make a pull request for a new feature **before** it has been
discussed on a simple GitHub issue.

By *discussed*, I mean that:

- requirements have been clarified and agreed on,
- then, documentation, have been clarified and agreed on,
- then, unit tests, have been clarified and agreed on.

We try to invent only if necessary, for example: if you want an additionnal
interface for your feature to be able to plug in, then **try** to propose new
`django signals <https://docs.djangoproject.com/en/dev/topics/signals/>`_,
rather than an API that comes out of nowhere.

Coding style
============

Coding style is mostly `PEP8
<http://legacy.python.org/dev/peps/pep-0008/>`_ and
we require `PEP257 docstrings
<http://legacy.python.org/dev/peps/pep-0257/>`_
with sphinx. You can see examples all over our code ;)
