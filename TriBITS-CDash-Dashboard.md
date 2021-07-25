TriBITs is currently being tested using  at using the [GitHub Actions(https://github.com/TriBITSPub/TriBITS/actions) with test results submitted to the CDash site:

* [TriBITS builds last two weeks on testing.sandia.gov/cdash/](https://testing.sandia.gov/cdash/index.php?project=TriBITS&display=project&filtercount=1&showfilters=1&field1=buildstarttime&compare1=83&value1=2%20weeks%20ago)

TriBITS is tested for a few different versions of CMake, compilers, Python, and other variations in the following scenarios:

* Pull requests against 'master' have results posted to the "Pull Request" CDash group with `pr-<id>_` prepended to the build names for the PR ID.
* Pushes to 'master' have results posted to the "Continuous" CDash group.
* Nightly builds have results posted to the "Nightly" CDash group.
* The "Experimental" CDash group is for any other submits of TriBITS test results using, for example, [`make dashboard`](https://tribitspub.github.io/TriBITS/build_ref/index.html#dashboard-submissions).
