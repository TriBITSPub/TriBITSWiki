## Overview

TriBITs is currently being tested using  at using the [GitHub Actions](https://github.com/TriBITSPub/TriBITS/actions) with test results submitted to the CDash site:

* [testing.sandia.gov/cdash/](https://testing.sandia.gov/cdash/index.php?project=TriBITS&filtercount=0&showfilters=1)
  * [current testing day](https://testing.sandia.gov/cdash/index.php?project=TriBITS&filtercount=0&showfilters=1)
  * [builds over last 2 weeks](https://testing.sandia.gov/cdash/index.php?project=TriBITS&display=project&filtercount=1&showfilters=1&field1=buildstarttime&compare1=83&value1=2%20weeks%20ago)

TriBITS is tested for a few different versions of CMake, compilers, Python, and other variations post to the following CDash groups:

* `Nightly`: Nightly builds posted every day regardless if there have been any repository activity that day <sup>[1]</sup>.
* `Continuous`: Pushes to 'master' <sup>[2]</sup>.
* `Pull Request`: Pull requests against 'master' with `pr-<id>_` prepended to the build names for the PR ID.
* `Experimental`: Any other submits of TriBITS test results using, for example, [`make dashboard`](https://tribitspub.github.io/TriBITS/build_ref/index.html#dashboard-submissions) on local machines.

For more details on the testing that is done, see the active [GitHub Actions drivers](https://github.com/TriBITSPub/TriBITS/tree/master/.github/workflows).

* [1]: Nightly builds primarily test that underlying infrastructure to ensure that everything is working so that when PRs and pushes are done, it will work when needed. 
* [2]: Even through each branch on a PR is tested before merging to 'master', it is still important to test when PR branches are merged to 'master' because two independent PRs that are tested at the same time can pass all of the tests independently but fail when merged together (i.e. a violation of the "additive test assumption of branches").

## GitHub Actions Pull Request Testing

Automated testing of TriBITS Pull Requests is currently performed using GitHub Actions as described above.  TriBITS has implemented bidirectional links from the GitHub actions jobs to the results on CDash and from the builds on CDash back to the GitHub Actions.  The builds on CDash for a single PR testing iteration look like:

![Single PR Iteration Builds on CDash](https://user-images.githubusercontent.com/1959736/128937317-2613b71b-e149-4c91-bc08-e8e9b167356d.png)

(NOTE: The current set of builds being done may be different that what is shown above.)

### Revision column on CDash build

As shown above, each build on CDash includes a "Revision" field that gives the shortened Git SHA1 for the commit being tested.  In the case of a PR, this is the SHA1 for a merge commit merging the PR topic branch into the target branch (i.e. 'master').   If one clicks on that SHA1 on CDash it takes you to a CDash page like [this](https://testing.sandia.gov/cdash/viewUpdate.php?buildid=9707976) that gives the full SHA1 and is hyperlinked to the commits on GitHub.  Amazingly, GitHub stores these merge commits so they can be examined on GitHub.

### Links from CDash builds back to GitHub PR

As shown above, each build on CDash shows the icon ![PR Link Icon](https://user-images.githubusercontent.com/1959736/128937363-a7f05a43-b0e0-4f62-8486-aba52dc1056f.png) that provides a link back to the PR (PR #401 in this case).

### Links from GitHub Actions Jobs to results on CDash

In addition, the GitHub Actions Jobs for a PR testing iteration provide hyperlinks to the build result on CDash under the "URL to results on CDash" step of the job as shown below.

<details>

<br>

<summary>Screenshots of the GitHub Actions Job hyperlink to results on CDash</summary>

On each passing GitHub Actions testing job, there is a "URL to results on CDash" step that contains a link to the results on CDash as shown below:

![Screenshot of the GitHub Actions Job "URL to results on CDash" hyperlink](https://user-images.githubusercontent.com/1959736/129061257-8aa7f806-cf4a-47a6-8d83-60fe0cb354a0.png)

This [hyperlink](https://testing.sandia.gov/cdash/index.php?project=TriBITS&filtercount=3&showfilters=1&filtercombine=and&field1=site&compare1=61&value1=ubuntu-latest&field2=buildname&compare2=61&value2=pr-401_tribits_cmake-3.17.5_makefiles_python-2.7_g%2B%2B-8&field3=buildstamp&compare3=61&value3=20210810-1744-Pull%20Request) takes you to a CDash build view as shown below:

![CDash results for build pr-401_tribits_cmake-3.17.5_makefiles_python-2.7_g++-8](https://user-images.githubusercontent.com/1959736/128960748-b9b7cc3c-5d94-4f46-95de-53909cb1ddff.png)

However, when there is a failure, the "URL to results on CDash" step is not run but a hyperlink to the results on CDash is also provided at the end of the "Run configure, build, test and submit to CDash" step as shown below:

![Screenshot of the GitHub Actions job "Run configure, build, test and submit to CDash" hyperlink for a failure](https://user-images.githubusercontent.com/1959736/129278812-343980b1-5f5e-43b4-a9d1-3ee21c6c506e.png)

</details>

### Query of all builds for a given PR on CDash

As shown above, the builds for any given PR `<pr-id>` (401 in this case) is given the build-name prefix `pr-<pr-id>_`.  This makes it easy to create a CDash query locating all of the configure, build, and test results associated with a PR using a [query URL like this for PR #401](https://testing.sandia.gov/cdash/index.php?project=TriBITS&filtercount=2&showfilters=1&filtercombine=and&field1=buildname&compare1=65&value1=pr-401_&field2=buildstarttime&compare2=84&value2=now) (just replace `401` in the `Build Name` field with the `<pr-id>` for the PR of interest).  This shows results like shown below.

<details>

<summary>Screenshot of all build and test results on CDash for PR #410</summary>

<br>

![Screenshot of all build and test results on CDash for PR #410](https://user-images.githubusercontent.com/1959736/128960998-f72d70d7-543f-4d09-9460-35ffe88ba652.png)

</details>

### Query of all GitHub Actions Test Jobs for a given PR

One can view all of the GitHub Actions PR testing iterations for a given PR using a [GitHub Actions Query like this for PR #401 with topic branch 154-improve-cdash-github-interaction](https://github.com/TriBITSPub/TriBITS/actions/workflows/tribits_testing.yml?query=event%3Apull_request+branch%3A154-improve-cdash-github-interaction) with results as shown below.

<details>

<summary>Screenshot of query for all GitHub Actions test iterations for a given PR branch</summary>

<br>

</details>

It is not too hard to match up those GitHub Actions PR testing iterations and the builds on CDash to go back in history.  But again, going from a given GitHub Action job to results on CDash is a direct hyperlink.  It is just that going from an arbitrary CDash build to its driving GitHub Actions Job is not as direct.  (Adding direct links for that would be a feature request.)

### Implementation details

For details on the implementation of this, see [GitHub Actions drivers](https://github.com/TriBITSPub/TriBITS/tree/master/.github/workflows), PR [#389](https://github.com/TriBITSPub/TriBITS/pull/389), [#401](https://github.com/TriBITSPub/TriBITS/pull/401), and other commits related to Issues [#363](https://github.com/TriBITSPub/TriBITS/issues/363) and [#154](https://github.com/TriBITSPub/TriBITS/issues/154).
