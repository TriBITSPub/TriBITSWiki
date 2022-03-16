# TriBITS Wiki Repo

This repo:

* https://github.com/TriBITSPub/TriBITSWiki

exists to facilitate Pull Requests for changes to the TriBITS wiki https://github.com/TriBITSPub/TriBITS/wiki provided by cloning the repo `git@github.com:TriBITSPub/TriBITS.wiki.git`.

First, create a fork of the GitHub repo:

* https://github.com/TriBITSPub/TriBITSWiki

to hold your topic branches.

The workflow is to first set up the local repo and remotes:

```
$ git clone -o production git@github.com/TriBITSPub/TriBITS.wiki.git TriBITSWiki
$ cd TriBITSWiki/
$ git remote add my-remote git@github.com/<your-github-id>/TriBITSWiki.git
```

With the above setup, the local 'master' branch will track the branch 'production/master'.

To create a new topic branch (always creating it off of the 'master' branch from the 'production' repo) and make changes and push as:

```
$ cd TriBITSWiki/
$ git checkout master
$ git pull   # Pulls from 'production/master'
$ git checkout -b <my-topic-branch>
<make changes to files and create commits>
$ git push -u my-remote HEAD
```

Then, create a Pull Request (PR) against the 'master' branch in the repo:

* https://github.com/TriBITSPub/TriBITSWiki

The PR will then be reviewed and changes suggested if any.

The PR in the repo https://github.com/TriBITSPub/TriBITSWiki will **not** get directly merged.  Instead, the topic branch from this PR will need to be manually merged to the 'master' branch of the repo `git@github.com:TriBITSPub/TriBITS.wiki.git` and then the 'master' branch of that repo must be manually merged to the repo `git@github.com:TriBITSPub/TriBITSWiki.git`.  The syncing of the 'master' branch will automatically close the PR showing it as 'merged'.

NOTES:

* The 'master' branch from the repo [`git@github.com:TriBITSPub/TriBITSWiki.git`](https://github.com/TriBITSPub/TriBITSWiki) must **never** be merged to the 'master' branch of the repo `git@github.com:TriBITSPub/TriBITS.wiki.git`.  The repo TriBITSWiki 'master' branch has extra commits like for [this REAMDE.md file](https://github.com/TriBITSPub/TriBITSWiki/edit/master/README.md) that we never want to be displayed on the production wiki site.

* Before the PR is open 'master' branches from the repo `git@github.com:TriBITSPub/TriBITS.wiki.git` must be merged to the 'master' branch of the repo `git@github.com:TriBITSPub/TriBITSWiki.git`.  Otherwise, the PR created from the 'master' branch of the repo `git@github.com:TriBITSPub/TriBITS.wiki.git` will show more commits and diffs than just unique to this PR topic branch.  Currently, that sync of the 'master' branch must be done manually.  In the future, it could be do automatically through a syncing cron job.
