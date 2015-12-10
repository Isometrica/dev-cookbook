
# Source Control Management

### Branching Strategy

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
    - Branch off of `develop` for each release candidate.
    - Apply fixes to release candidate on _only_ on this branch.
    - Can be merged into `develop` periodically
    - Merged into `master` and tagged when released
    - _Must_ have passing build to merge into `master`

  - `hotfix/issues-key][description]`

    - Hotfix branch
    - _Only_ merged to / from `master`
    - _Must_ correspond to a JIRA issue
    - _Must_ have passing build to merge into `master`

  - `master`

    - Live stable branch
    - _Must_ have passing build

### Policies

- Individual developers are responsible for ensuring that their tests pass when merging into the development branch.
- Monday reviews are a good opportunity to review latest merges into the development branch.
- Merges into release candidate branches, hotfixes and master must be reviewed by the whole team.

### Hooks

- Ensure every feature branch has a JIRA issue.
- We use [smart commits](https://confluence.atlassian.com/fisheye/using-smart-commits-298976812.html) to manage JIRA issue workflows.
