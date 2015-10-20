Contributions to TriBITS are welcomed.  However, there are some requirements that every contribution needs to follow before it can be integrated into the main development branch of TriBITS and there is a recommended process for suggesting and submitted proposed changes.

## Requirements for every change to TriBITS

1. Any change in behavior or new behavior needs to be accompanied with automated tests to define and protect these changes.  If automated tests are not possible or too difficult, this can be discussed in the Github Issue or Pull-Request (see below).
2. Any new feature or change in the behavior of an existing feature must be fully documented before it is accepted.  This documentation is generally added to one or more of the following places:
  1. In the implementation `*.cmake` file itself (formatted with restructuredText and pulled out automatically into the TriBITS Developers Guide, see existing examples)
  2. In the `TribitsDevelopersGuide.rst` document (under `tribits/doc/developers_guide/`)
  3. In the `TribitsBuildReferenceBody.rst` document (under `tribits/doc/build_ref/`)

## Preferred process for suggesting and making changes to TriBITS

1. Submit a [GitHub Issue](https://github.com/TriBITSPub/TriBITS/issues) proposing the change (see [Kanban Process](https://github.com/TriBITSPub/TriBITS/wiki/Kanban-Process-for-Issue-Tracking) used to manage TriBITS Issues).  That way a conversation can be started to make sure the right contribution is made and to avoid wasted effort in case a suggested change can't be accepted for some reason.  If the TriBITS maintainer decides that the proposed change is not appropriate, then the Issue may be closed after the justification is added to a comment.  Also, the TriBITS maintainer may offer to implement the changes themselves if that is most appropriate.  However, regardless of who actually makes the proposed changes, the following process is still followed.
2. After the proposed change is approved in the GitHub Issue, then the contributor should create a topic/feature branch in their forked TriBITS repo and then issue a [pull-request](https://help.github.com/articles/using-pull-requests/) (i.e. PR).  That pull request should then reference the original GitHub Issue in a comment to link the PR to the original Issue.  (NOTE: A partial set of changes is just fine in the PR, just enough to start the code review process.)
3. A code review process is performed and continued changes are then carried out with comments made in the new PR or the original Issue (whatever makes sense but usually comment specific to changes in a give PR should should go in PR comments).  New updates to the branch can be pushed as changes are made to address issues with the changes.
4. The TriBITS maintainer will then either accept the PR (by rebasing and merging the branch to main development branch) or will state what further issues must be resolved before the change can be incorporated.

NOTES:
* All changes that are submitted are assumed to be given under the [3-clause BSD-like TriBITS License](https://github.com/TriBITSPub/TriBITS/blob/master/tribits/Copyright.txt)
* Very simple changes can but attached to a GitHub Issue using `git format-patch` but the above process involving pull requests is preferred.  Generally raw patches will not be accepted.
