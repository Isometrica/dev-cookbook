
#Source Control Management

###Branching Strategy

- We use the [Gitflow](http://jeffkreeftmeijer.com/2010/why-arent-you-using-git-flow/) branching strategy.
- We expect to have the following branches:

  - `[issue-type]/[issues-key][description]`

    - Feature branches
    - `story/plio-28-create-risks`
    - `bug/plio-8-grammar-error`
    - _Must_ correspond to a JIRA issue
    - _Only_ merged to / from `develop`
    - _Must_ have passing build to merge into `develop`

  - `develop`

    - Working development branch

  - `rc/[version number]`

    - Release candidate branch
    - Branch off of `develop` and tagged for each release candidate.
    - Apply fixes to release candidate on _only_ on this branch.
    - Can be merged into `develop` periodically
    - Merged into `master` and tagged when released
    - _Must_ have passing build to merge into `master`

  - `hotfix/issues-key][description]`

    - Hotfix branch
    - _Only_ merged to / from `master`
    - Tagged when merged back into master
    - _Must_ correspond to a JIRA issue
    - _Must_ have passing build to merge into `master`

  - `master`

    - Live stable branch
    - _Must_ have passing build

###Policies

- Individual developers are responsible for ensuring that their tests pass when merging into the development branch.
- Monday reviews are a good opportunity to review latest merges into the development branch.
- Merges into release candidate branches, hotfixes and master must be reviewed by the whole team.

###Tags

- [Semantic versioning](http://semver.org/)
- Major release: `x.0.0`
- Release candidates: `x.y.0-RC.n`
- Minor release: `x.y.0`
- Hotfix off of master: `x.y.z`

###Commit Messages

Minimum commit message requirements:

```
[JIRA issue key] Short, one line summary of the change
```

Ideal commit message:

```
[JIRA issue key] [other smart commit metadata] Summary of the change

More detailed explanatory text, if necessary. Wrap it to about 72
characters or so. In some contexts, the first line is treated as the
subject of the commit and the rest of the text as the body. The
blank line separating the summary from the body is critical (unless
you omit the body entirely); various tools like `log`, `shortlog`
and `rebase` can get confused if you run the two together.

Signed off by: ....

```

###References

- [Commit message formatting.](http://chris.beams.io/posts/git-commit/)
- [Semver](http://semver.org/)
- [Smart commits](https://confluence.atlassian.com/fisheye/using-smart-commits-298976812.html)
