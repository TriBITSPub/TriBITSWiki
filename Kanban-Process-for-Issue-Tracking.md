## Kanban stages

TriBITS uses a Kanban process with Github Issue tracking and Pull Request (PR) management using a [TriBITS GitHub Project board](https://github.com/TriBITSPub/TriBITS/projects).

The Kanban stages for TriBITS GitHub Issues (and PRs) are:

* **Backlog**: Every issue not in one of the below stages
* **ToDo**: Items of higher priority in the backlog that could be ready to work soon.
* **Selected**: Items scoped and ready to be worked when there is available capacity
* **In Progress**: Issues we are actively being worked (or have already started to be worked)
* **In Review**: Issues that are complete but need to be reviewed or are in review
* **Done**: Issues have been completed and are providing real value to the customer

NOTES:

* All new Issues are automatically considered in the "Backlog" and are not shown on the Kanban boards.
* Even issues that are stalled can be listed "In Progress".
* Issues and Pull Requests (PR) closed without being completed/merged must be marked with the label `resolution: wontfix` or `resolution: invalid` and should be removed from the Kanban boards Done column.  Also, amending the title with `WONTFIX: ` or `INVALID: ` can also help to make clear the Issue/PR was not worked/resolved.

## TriBITS GitHub Issue Process

The intended Kanban process lifecycle for a **TriBITS GitHub Issue** is as follows (consistent with [TriBITS/CONTRIBUTING.md](https://github.com/TriBITSPub/TriBITS/blob/master/CONTRIBUTING.md)):

* Someone creates a new Issue as a suggestion (and it automatically is placed in the Backlog).
* The Product Owner then takes the Issue and reviews it in the Backlog and comments on it (or closes it if justified).
* Issues are regularly are moved into "ToDo" or "Selected" when they are high enough priority and are ready to be worked.  (We should not cram a bunch of stuff into "Selected".  We should keep that list short so that it is clear what to work on next.)
* When adequate capacity is freed up, an Issue is moved from "Selected" to "In Progress" by the developer and it is actively worked.
* Issues "In Progress" should be worked as quickly as possible to get them done.
* Once an Issue "In Progress" is ready, it is moved into "In Review" so it can be reviewed by someone.  (The code related to this issue should be submitted on a branch as a pull request to allow the review.)
* Once the Issue (and associated pull request) is independently reviewed, then the branch is merged and pushed (if the Issue is for a code change) and the Issue may be closed (if the PR completed resolved the issue).

That is the basic Kanban Issue process in a nutshell.  The process details are given in [TriBITS/CONTRIBUTING.md](https://github.com/TriBITSPub/TriBITS/blob/master/CONTRIBUTING.md).

## TriBITS Pull Request Process

The Kanban lifecycle process fopr Pull Requests (PRs) follows a reduced number of Kanban stages:

* A new Pull Request is automatically added to the **In Progress** stage.
* GitHub Actions testing is performed on each push to the PR branch with results displayed on [CDash](https://github.com/TriBITSPub/TriBITS/wiki/TriBITS-CDash-Dashboard).
* When the PR is ready to be reviewed, it is moved to the **In Review** stage and reviewers are assigned.
* Once the PR has been reviewed and accepted, it is merged (and the associated topic branch is merged to the main development branch).

## TriBITS Vulnerability Reports

<a name="vulnerability_reports"/>

* There are no known mechanisms where TriBITS software could cause a vulnerability.  But if a vulnerability is suspected to be caused by TriBITS, please directly contact the TriBITS Maintainer [**@bartlettroscoe**](https://bartlettroscoe.github.io/) with the details. <sup>[<a href="#vulnerability_reports">vulnerability_reports</a>]</sup>

<!--

LocalWords:  Kanban TriBITS

-->
