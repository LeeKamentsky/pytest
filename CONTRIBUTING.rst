============
Contributing
============

Contributions are highly welcomed and appreciated.  Every little help counts,
so do not hesitate!


Types of contributions
======================

Report bugs
-----------

Report bugs at https://bitbucket.org/hpk42/pytest/issues.

If you are reporting a bug, please include:

* Your operating system name and version.
* Any details about your local setup that might be helpful in troubleshooting,
  specifically Python interpreter version,
  installed libraries and pytest version.
* Detailed steps to reproduce the bug.

Submit feedback for developers
------------------------------

Do you like pytest?  Share some love on Twitter or in your blog posts!

We'd also like to hear about your propositions and suggestions.  Feel free to
`submit them as issues <https://bitbucket.org/hpk42/pytest/issues>`__ and:

* Set the "kind" to "enhancement" or "proposal" so that we can quickly find
  about them.
* Explain in detail how they should work.
* Keep the scope as narrow as possible.  This will make it easier to implement.
* If you have required skills and/or knowledge, we are very happy for
  pull requests (see below).


Fix bugs
--------

Look through the BitBucket issues for bugs.  Here is sample filter you can use:
https://bitbucket.org/hpk42/pytest/issues?status=new&status=open&kind=bug

:ref:`Talk <contact>` to developers to find out how you can fix specific bugs.

Implement features
------------------

Look through the BitBucket issues for enhancements.  Here is sample filter you
can use:
https://bitbucket.org/hpk42/pytest/issues?status=new&status=open&kind=enhancement

:ref:`Talk <contact>` to developers to find out how you can implement specific
features.

Write documentation
-------------------

pytest could always use more documentation.  What exactly is needed?

* More complementary documentation.  Have you perhaps found something unclear?
* Documentation translations.  We currently have English and Japanese versions.
* Docstrings.  There's never too much of them.
* Blog posts, articles and such -- they're all very appreciated.

Preparing Pull Requests on Bitbucket
=====================================

The primary development platform for pytest is BitBucket.  You can find all
the issues there and submit pull requests.  There is, however,
a `GitHub mirror <https://github.com/hpk42/pytest/>`__ available, too,
although it only allows for submitting pull requests.  For a GitHub
contribution guide look :ref:`below <contribution-on-github>`.

1. Fork the `pytest bitbucket repository <https://bitbucket.org/hpk42/pytest>`__. It's fine to
  use ``pytest`` as your fork repository name because it will live
  under your user.

.. _virtualenvactivate:

2. Create and activate a fork-specific virtualenv
   (http://www.virtualenv.org/en/latest/)::

    $ virtualenv pytest-venv
    $ source pytest-venv/bin/activate

.. _checkout:

3. Clone your fork locally and create a branch::

    $ hg clone ssh://hg@bitbucket.org/YOUR_BITBUCKET_USERNAME/pytest
    $ cd pytest
    $ hg branch <yourbranchname>

.. _testing-pytest:

4. You can now edit your local working copy.  To test you need to
   install the "tox" tool into your virtualenv::

    $ pip install tox

  You need to have Python 2.7 and 3.3 available in your system.  Now
  running tests is as simple as issuing this command::

    $ python runtox.py -e py27,py33,flakes

  This command will run tests via the "tox" tool against Python 2.7 and 3.3
  and also perform "flakes" coding-style checks.  ``runtox.py`` is
  a thin wrapper around ``tox`` which installs from a development package
  index where newer (not yet released to pypi) versions of dependencies
  (especially ``py``) might be present.

  To run tests on py27 and pass options (e.g. enter pdb on failure)
  to pytest you can do::

    $ python runtox.py -e py27 -- --pdb

  or to only run tests in a particular test module on py33::

    $ python runtox.py -e py33 -- testing/test_config.py

5. Commit and push once your tests pass and you are happy with your change(s)::

    $ hg commit -m"<commit message>"
    $ hg push -b .

6. Finally, submit a pull request through the BitBucket website::

    source: <your user>/pytest
    branch: <yourbranchname>

    target: hpk42/pytest
    branch: default


.. _contribution-using-git:
What about git (and so GitHub)?
-------------------------------

There used to be the pytest github mirror. It was removed in favor of this mercurial one, to remove confusion of people
not knowing where it's better to put their issues and pull requests. Also it wasn't easilily possible to automate
mirroring process.
However, it's still possible to use git to contribute to pytest using tools like https://github.com/buchuki/gitifyhg
which allow you to clone and work mercurial repo still using git.

.. warning::
  Remember that git is **not** a default version control system py.test and you need to be careful using git
  to work with it.

Please read the manual carefully, and then use same contribution manual as for BitBucket.