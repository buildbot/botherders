Buildbot depends on many other pieces of software.
The "Requirements" section of the documentation specifies the requirements for each version of Buildbot, while this page describes the general approach used to determine those versions.

We have an advantage in using Python: it is quite possible to install arbitrary versions of Python distribution packages in a virtualenv without requiring root access.
However, this is often inconvenient.

Batteries Included
==================

It should always be possible to `pip install buildbot` and get something functional.
That may be single-master, and may not be as performant as possible, but it should work.
The upshot is that we can't depend by default on external services (such as a database engine) or software (such as libzmq).

Changing Requirements
=====================

When the Buildbot requirements change, the NEWS for the release should make the change clear, and also summarize the rationale for the change.

Buildmaster
===========

A Buildbot installation will usually only have one master, and that master will receive a lot of attention from the user.
As such, the extra cost of installing recent versions of prerequisite Python packages is smaller than for a buildslave.
Non-Python packages are more problematic, as many users have well-defined systems for installing binary packages (for example, Enterprise Linux users), and it may be difficult to install the latest and greatest using that system.
Finally, versions of Python are particularly problematic, because many other system components depend on Python and an upgrade can be very disruptive.

Python Packages
---------------

All efforts should be made to support the versions of Python packages that are available in the most recent versions of common operating-system distributions.

Where practical, compatibility with older versions should be maintained, e.g., disabling features when such older versions are detected.
Such considerations should not substantially complicate the Buildbot source code - if the workarounds become overwhelming, consider dropping support for older versions.
General compatibility and workarounds should be tested regularly by the metabuildbot.

System Packages
---------------

Buildbot should be as accepting as possible of system package versions, and should support at least the versions in the latest long-term-support (LTS) versions of various distros.
In most cases, such dependencies should be optional (e.g., version-control packages), and Buildbot should still function without the package.

Python Versions
---------------

Because it is so difficult to upgrade to a new Python version, Buildbot's support for Python versions should remain as broad as possible.
We will only drop support for an older version of Python when that version is no longer the default on commonly-available operating systems (e.g., Python 2.3 as of 2010) or when compatibility with that version is blocking a substantial new Buildbot feature.
All supported versions of Python should be tested regularly by the metabuildbot, as it is very easy to accidentally use newer language features.

Python 3
--------

As Python 3 becomes more common, and when Twisted support for Python 3 is in place, we may consider reducing support for older versions of Python 2 in order to support Python 3.
At this time, it may be worth considering a long-term maintenance fork (which will require an adjustment to the SupportPolicy).
See [glyph's answer](http://stackoverflow.com/questions/172306/how-are-you-planning-on-handling-the-migration-to-python-3) for more thoughts on the topic.

Buildslave
==========

Any Buildbot installation will have many more slaves than masters, and in many cases the slaves are outside of the buildbot user's administrative domain.
It's also quite common to run the buildslave on odd architectures that may only have very old versions available.
As such, the buildslave is much more sensitive to version dependencies.
It is also a much simpler application, and should be able to maintain broader compatibility.
All supported version combinations should be tested regularly by the metabuildbot.

Buildslave's primary prerequisites are Python and Twisted.
We will only drop support for an older version of either when it is no longer practical to test with that version.
For example, we dropped Twisted-2.5.0 support because it is difficult to download and install that version of Twisted using virtualenvs.
