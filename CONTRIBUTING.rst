Contribution guidelines
=======================

These guidelines instruct how to submit issues and contribute code or
documentation to the `RIDE project
<https://github.com/robotframework/RIDE>`_.
There are great ways to contribute include
answering questions and participating discussion on `robotframework-users
<https://groups.google.com/forum/#!forum/robotframework-users>`_ mailing list
and other forums, as well as spreading the word about the framework one way or
the other.

These guidelines expect readers to have a basic knowledge about open source
as well as why and how to contribute to open source projects. If you are
totally new to these topics, it may be a good idea to look at the generic
`Open Source Guides <https://opensource.guide/>`_ first.

.. contents::
   :depth: 2
   :local:

Submitting issues
-----------------

Before submitting a new issue, it is always a good idea to check is the
same bug or enhancement already reported. If it is, please add your comments
to the existing issue instead of creating a new one.

How to check for the issues that are already present ?

Answer: 

Reporting bugs
~~~~~~~~~~~~~~

Explain the bug you have encountered so that others can understand it
and preferably also reproduce it. Key things to have in good bug report:

1. Version information

   - Robot Framework version
   - Python interpreter type (Python, Jython, IronPython, PyPy) and version
   - Operating system and its version

2. Steps to reproduce the problem. With more complex problems it is often
   a good idea to create a `short, self contained, correct example (SSCCE)
   <http://sscce.org>`_.

3. Possible error message and traceback.

Notice that all information in the issue tracker is public. Do not include
any confidential information there.

How to find different logs in RIDE , that one can add to a RIDE issue? 

Answer:

Enhancement requests
~~~~~~~~~~~~~~~~~~~~

Describe the new feature and use cases for it in as much detail as possible.
Especially with larger enhancements, be prepared to contribute the code
in the form of a pull request as explained below or to pay someone for the work.
Consider also would it be better to implement this functionality as a separate
tool outside the core framework.

Code contributions
------------------

If you have fixed a bug or implemented an enhancement, you can contribute
your changes via GitHub's pull requests. This is not restricted to code,
on the contrary, fixes and enhancements to documentation_ and tests_ alone
are also very valuable.

Choosing something to work on
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Often you already have a bug or an enhancement you want to work on in your
mind, but you can also look at the `issue tracker`_ to find bugs and
enhancements submitted by others. The issues vary significantly in complexity
and difficulty, so you can try to find something that matches your skill level
and knowledge. There are two specific labels to look for when looking for
something to contribute:

`good first issue`__
   These issues typically do not require any knowledge of Robot Framework
   internals and are generally easy to implement or fix. Thus these issues
   are especially good for new contributors.

`help wanted`__
   These issues require external help to get implemented or fixed.

__ https://github.com/robotframework/robotframework/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22
__ https://github.com/robotframework/robotframework/issues?q=is%3Aopen+is%3Aissue+label%3A%22help+wanted%22

Pull requests
~~~~~~~~~~~~~

On GitHub pull requests are the main mechanism to contribute code. They
are easy to use both for the contributor and for the person accepting
the contribution, and with more complex contributions it is easy also
for others to join the discussion. Preconditions for creating pull
requests are having a `GitHub account <https://github.com/>`_,
installing `Git <https://git-scm.com>`_ and forking the
`Robot Framework project`_.

GitHub has good articles explaining how to
`set up Git <https://help.github.com/articles/set-up-git/>`_,
`fork a repository <https://help.github.com/articles/fork-a-repo/>`_ and
`use pull requests <https://help.github.com/articles/using-pull-requests>`_
and we do not go through them in more detail. We do, however, recommend to
create dedicated topic branches for pull requests instead of creating
them based on the master branch. This is especially important if you plan to
work on multiple pull requests at the same time.

Coding conventions
~~~~~~~~~~~~~~~~~~

General guidelines
''''''''''''''''''

Robot Framework uses the general Python code conventions defined in `PEP-8
<https://www.python.org/dev/peps/pep-0008/>`_. In addition to that, we try
to write `idiomatic Python
<http://python.net/~goodger/projects/pycon/2007/idiomatic/handout.html>`_
and follow the `SOLID principles
<https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)>`_ with all
new code. An important guideline is that the code should be clear enough that
comments are generally not needed.

All code, including test code, must be compatible with all supported Python
interpreters and versions. Most importantly this means that the code must
support both Python 2 and Python 3.

Line length
'''''''''''

Maximum line length with Python code, including docstrings and comments, is 88
characters. This is also what `Black <https://pypi.org/project/black/>`__ uses
by default and `their documentation
<https://black.readthedocs.io/en/stable/the_black_code_style.html#line-length>`__
explains why. Notice that we do not have immediate plans to actually take Black
into use but we may consider that later.

With Robot Framework tests the maximum line length is 100.

Whitespace
''''''''''

We are pretty picky about using whitespace. We follow `PEP-8`_ in how to use
blank lines and whitespace in general, but we also have some stricter rules:

- No blank lines inside functions.
- No blank lines between a class declaration and class attributes or between
  attributes.
- Indentation using spaces, not tabs.
- No trailing spaces.
- No extra empty lines at the end of the file.
- Files must end with a newline.

Most of these rules are such that any decent text editor or IDE can be
configured to automatically format files according to them.

Docstrings
''''''''''

Docstrings should be added to public APIs, but they are not generally needed in
internal code. When docstrings are added, they should follow `PEP-257
<https://www.python.org/dev/peps/pep-0257/>`_. See `API documentation`_
section below for more details about documentation syntax, generating
API docs, etc.

Documentation
~~~~~~~~~~~~~

With new features adequate documentation is as important as the actual
functionality. Different documentation is needed depending on the issue.

User Guide
''''''''''


Tests
~~~~~

When submitting a pull request with a new feature or a fix, you should
always include tests for your changes. These tests prove that your changes
work, help prevent bugs in the future, and help document what your changes
do. Depending on the change, you may need acceptance tests, unit tests
or both.

Make sure to run all of the tests before submitting a pull request to be sure
that your changes do not break anything. If you can, test in multiple
environments and interpreters (Windows, Linux, OS X, Python, Jython,
IronPython, Python 3, etc). Pull requests are also automatically tested on
continuous integration.

Executing changed code
''''''''''''''''''''''

Acceptance tests
''''''''''''''''

Unit tests
