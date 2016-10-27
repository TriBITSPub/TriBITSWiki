The github version is currently being tested at using the [Travis CI TriBITS build](https://travis-ci.org/TriBITSPub/TriBITS) which submits results to the CDash site:

* [TriBITS my.cdash.org site](http://my.cdash.org/index.php?project=TriBITS)

All pushes to every branch in this main github repo is testing using Travis CI which submits results to that CDash site.  To see the connection between the Travis CI output and the CDash site, look for output of the form:

```
See results for:

  Site: testing-gce-2b75b718-84f7-49a0-9423-ebf20b554c66

  Build Name: Linux-UNKNOWN-SERIAL_DEBUG_TravisCI

at:

  http://my.cdash.org/index.php?project=TriBITS&display=project
```

Now that every Travis CI build has a unique `Site` name so one can use a CDash query to find the matching build.

Note that  TriBITS is also involved in continuous integration testing and nightly testing along with the CASL VERA project which has a [private CDash dashboard](https://casl-dev.ornl.gov/cdash/index.php?project=VERA&subproject=TriBITS).  The version of TriBITS tested as part of CASL VERA is from a private clone of TriBITS that is synced to the github.com 'master' branch frequently.  TriBITS changes that are targeted for CASL VERA are typically pushed directly the the CASL VERA clone and then synced to the GitHub 'master' branch.
