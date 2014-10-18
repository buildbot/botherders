Buildbot's releases are based on available time for stabilization and release testing, rather than on a schedule or completion of features.
We do not produce any sort of "preview" release (beta, rc, etc.).
If a major problem is discovered in a release, we will simply make a new release containing the fix.

Releases are announced via the buildbot-devel mailing list, the buildbot-announce list, and on [http://pypi.python.org/pypi/ pypi].
They are also described on the front page of http://trac.buildbot.net.
Package maintainers should watch at least one of these channels to see when new versions are released.

Version Numbers
===============

Buildbot follows [semantic versioning](http://semver.org/), although the duration of major version zero is longer than for most projects.
Given a Buildbot version number in the form X.Y.Z, the X will remain `0` until the major structure of the application/framework is complete.
This is the subject of much bikeshedding!

A change in the Y component indicates a more difficult upgrade - for example, requiring a database backend in 0.8.0.
The Z component increments monotonically with each non-major release, but note that significant new functionality may come with such an increment.

Support
=======

Note that only the most recent version of Buildbot is supported, meaning that we will not make patch releases of older versions ''except in the case of security vulnerabilities.''
See the [support policy](https://github.com/buildbot/botherders/blob/master/policies/support.md) and [security policy](https://github.com/buildbot/botherders/blob/master/policies/security.md).
