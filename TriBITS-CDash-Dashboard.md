**NOTE: TRAVIS CI TESTING IS CURRENTLY DISABLED**

The github version is currently being tested at using the [Travis CI TriBITS build](https://travis-ci.org/TriBITSPub/TriBITS) which submits results to the CDash site:

* [TriBITS builds on testing.sandia.gov/cdash/](https://testing.sandia.gov/cdash/index.php?project=TriBITS&display=project&filtercount=1&showfilters=1&field1=buildstarttime&compare1=83&value1=2%20weeks%20ago)

All pushes to every branch in this main github repo and every PR created in this repo is testing using Travis CI which submits results to that CDash site.  To see the connection between the Travis CI output and the CDash site, look for output of the form:

```
See results for:

  Site: TravisCI

  Build Name: Linux-UNKNOWN-SERIAL_DEBUG_TravisCI

at:

  http://testing-vm.sandia.gov/cdash/index.php?project=TriBITS&display=project
```

