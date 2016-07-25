Contributions to TriBITS are welcomed.  However, there are some [requirements](#requirements) that every contribution needs to follow before it can be integrated into the main development branch of TriBITS and there is a [recommended process](#process) for suggesting and submitted proposed changes.

**Contents:**
* [Requirements for every change to TriBITS](#requirements)
* [Preferred process for suggesting and making changes to TriBITS](#process)

**NOTE:** All contributions that are submitted are assumed to be given under the **[3-clause BSD-like TriBITS License](https://github.com/TriBITSPub/TriBITS/blob/master/tribits/Copyright.txt).**

<a name="requirements"/>
## Requirements for every change to TriBITS

1. Any change in behavior or new behavior needs to be accompanied with **automated tests** to define and protect these changes.  If automated tests are not possible or too difficult, this can be discussed in the Github Issue or Pull-Request (see below).
2. All non-trivial changes should have a **GitHub Issue created** for them and all associated commits should **list the GitHub Issue ID in the commit logs**.
3. Any new feature or change in the behavior of an existing feature must be **fully documented** before it is accepted.  This documentation is generally added to one or more of the following places:
  1. In the implementation `*.cmake` file itself (formatted with restructuredText and pulled out automatically into the TriBITS Developers Guide, see existing examples)
  2. In the `TribitsDevelopersGuide.rst` document (under `tribits/doc/developers_guide/`)
  3. In the `TribitsBuildReferenceBody.rst` document (under `tribits/doc/build_ref/`)

<a name="process"/>
## Preferred process for suggesting and making changes to TriBITS

The following roles are mentioned on the process descriptions:
* **TriBITS Maintainer**: Individual with push rights to the main TriBITS repo (i.e. Ross Bartlett).  Must review all issues and suggested changes and accept pull-requests.

* **TriBITS Developer**: Someone who knows how to built TriBITS as a project with its tests, add tests, make acceptable changes, create pull-requests, etc. but can't directly push to the main TriBITS repo branches (see the role of [TriBITS System Developer](https://tribits.org/doc/TribitsDevelopersGuide.html#tribits-developer-and-user-roles)).  This might be the Issue Reporter.

* **Issue Reporter**: A person who first reports an issue with TriBITS and would like some type of change to happen (i.e. to fix a defect, implement a new feature, etc.).  This might be a TriBITS Developer.

With those definitions in place, the recommended/preferred process for contributing to TriBITS is as follows:

1. The Issue Reporter should **Submit a [GitHub Issue](https://github.com/TriBITSPub/TriBITS/issues) proposing the change** (see [Kanban Process](https://github.com/TriBITSPub/TriBITS/wiki/Kanban-Process-for-Issue-Tracking) used to manage TriBITS Issues).  That way, a conversation can be started to make sure the right contribution is made and to avoid wasted effort in case a suggested change can't be accepted for some reason.  **If the TriBITS Maintainer decides that the proposed change is not appropriate, then the Issue may be closed after the justification is added to a comment.**  Also, the TriBITS Maintainer may offer to implement the changes themselves or ask another TriBITS Developer to do so if that is most appropriate.  However, regardless of who actually makes the proposed changes, the following steps should is still be followed.
2. After the proposed change is approved in the GitHub Issue by the TriBITS Maintainer, then the TriBITS Developer (which might be the Issue Reporter or the TriBITS Maintainer) should **Create a topic/feature branch** in their forked TriBITS repo, **create commits with logs referencing the Issue ID (e.g. `#123`)**, and then **issue a [pull-request](https://help.github.com/articles/using-pull-requests/) (i.e. PR)**.  The change in the PR will automatically be tested using [Travis CI](https://travis-ci.org/TriBITSPub/TriBITS).  Also, the PR allows for a well managed code review (comments for each line of the change, for example).  The pull request should then reference the original GitHub Issue in a comment to link the PR to the original Issue.  (NOTE: A partial set of changes is just fine in the PR, just enough to start the code review process.)
3. A **Code review process is performed** by the TriBITS Maintainer and continued changes are made by the TriBITS Developer and new comments are created in the new PR or the original Issue (whatever makes sense but usually comments specific to changes in a given PR should should go in PR comments while more general comments not specific to a PR should go into the associated GitHub Issue).  New updates to the branch can be pushed by the TriBITS Developer as changes are made to address issues with the changes.
4. The TriBITS maintainer will then **either accept the PR** (by rebasing and merging the branch to main development branch) **or will state what further issues must be resolved** before the change can be incorporated.

**NOTE:** Very simple changes can but attached to a GitHub Issue which are generated using `git format-patch` but the above process involving pull requests is preferred.  But **generally raw patches will not be accepted** due to the added difficulty for the TriBITS Maintainer to review the changes and to eventually apply them to the TriBITS 'master' branch itself.  Also, using git commits send either through a branch in a pull-request or through `git format-patch` will record the author's contribution and give them credit for the change. 

**NOTE:** The above process is just a suggested process.  What is important are the [requirements](https://github.com/TriBITSPub/TriBITS/wiki/Contributing-to-TriBITS#requirements) listed above.
