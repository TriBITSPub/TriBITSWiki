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
* [2]: Even through each branch on a PR is tested before merging to 'master', it is still important to test when PR branches are merged to 'master' because two independent PRs that are tested at the same time can pass all of the tests independently but fail when merged together.
