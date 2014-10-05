Buildbot's releases are based on time, rather than new features.
We try to produce a new release every 2-3 months, although the schedule is not firm and can be adjusted to fix bugs, finish a major feature, or avoid holidays.
We do not produce any sort of "preview" release (beta, rc, etc.).
If a major problem is discovered in a release, we will simply make a new release containing the fix.

Releases are announced via the buildbot-devel mailing list, [http://pypi.python.org/pypi/ pypi], and [http://freshmeat.net freshmeat].
They are also described on the front page of http://buildbot.net, and the release files are available from [http://buildbot.googlecode.com google code].
Package maintainers should watch at least one of these channels to see when new versions are released.

Version Numbers
===============

Given a Buildbot version number in the form X.Y.Z, the X will remain {{{0}}} until the major structure of the application/framework is complete.
This is the subject of much bikeshedding!
A change in the Y component indicates a more difficult upgrade - for example, requiring a database backend in 0.8.0.
The Z component increments monotonically with each non-major release, but note that significant new functionality may come with such an increment.

Support
=======

Note that only the most recent version of Buildbot is supported, meaning that we will not make patch releases of older versions ''except in the case of security vulnerabilities.''

In general, we will try to make an exceptionally stable release X.Y.Z before releasing X.(Y+1).0, so that users who cannot upgrade quickly are not left on an unstable, unsupported version.
The X.(Y+1).0 version will be a minimal change from the stable X.Y.Z, without extraneous new features or complications, to minimize the complications from the upgrade.
