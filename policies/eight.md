Maintenance of Eight
====================

The current focus of development is 0.9.0 ("Nine") represented by the `master` branch in the git repository.
Until that release is made, there could be some problems found with the current stable version, which is on the `eight` branch.

There are two major cases that affect how the maintenance takes place:

 1. a bugfix or a new feature affects both Eight and Nine
 1. a bugfix or a new feature is not relevant for Nine any more

In the first case, the change must be first submitted against `master` and, after it is accepted, backported/adapted to `eight`.

In the second case, the change can be submitted directly to `eight` for inclusion.  There are two known areas where submission for Nine is not necessary:

* WebStatus modifications
* master-side support for old-style source steps

(Please check [release notes for the version in development](http://docs.buildbot.net/latest/relnotes/index.html))
