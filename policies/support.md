Buildbot's support policy is simple: we only support the most recent version.

If a significant bug is found in a version before the most recent release, users are encouraged to upgrade.

If a significant bug is found in the most recent released version, one of two things may happen.
If the current master is sufficiently stable, the bug will be fixed and a new full release made.
If the current master is not stable, and the fix is simple enough, then the fix will be applied on the release branch and a new patch release made (e.g., 9.2.1p1).

Security Releases
=================

The exception is for security releases - security patches will be made available for as many previous versions as possible or practical.
See https://github.com/buildbot/botherders/blob/master/policies/security.md for more.

Consequences
============

This simple policy comes at a cost: we will take care to make sure that upgrades between official releases are simple and do not lead to hidden surprises.
We can test this for "simple" configurations, but for more complex configurations that subclass arbitrary pieces of Buildbot, such assertions are more difficult to make.

In the short term, the Buildbot developers are happy to help anyone with such a configuration to upgrade to the latest version.
In the long term, we are working toward a well-defined API against which users can build their configurations and which the Buildbot developers will commit to support or change in a measured, well-publicized fashion.
