TriBITS is tested in continuous integration testing and nightly testing along with the CASL VERA project which has a [private CDash dashboard](https://casl-dev.ornl.gov/cdash/index.php?project=VERA&subproject=TriBITS).  The version of TriBITS tested as part of CASL VERA is from a private clone of TriBITS that is synced to the github.com version frequently.  The reason for this testing and integration model is that CASL funds the majority of TriBITS development and this testing directly supports that project.

The github version is currently being tested at using the [Travis CI TriBITS build](https://travis-ci.org/TriBITSPub/TriBITS).  In the near future, independent CTest/CDash driver builds against the github.com 'master' branch will be set up that submit results to:

* [TriBITS my.cdash.org site](http://my.cdash.org/index.php?project=TriBITS)
