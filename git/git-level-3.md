# Git - Level 3

## master



## develop

## feature/

Features should never interact directly with `master`.

 `Feature` branches are generally created off to the latest `develop`branch.

## release

Once `develop` has acquired enough features for a release \(or a predetermined release date is approaching\), you fork a `release`branch off of `develop`. Creating this branch starts the next release cycle, so no new features can be added after this point—only bug fixes, documentation generation, and other release-oriented tasks should go in this branch. Once it's ready to ship, the `release`branch gets merged into `master` and tagged with a version number. In addition, it should be merged back into `develop`, which may have progressed since the release was initiated.

{% embed url="https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow" %}



