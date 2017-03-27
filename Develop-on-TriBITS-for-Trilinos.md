One can easily do co-development of Trilinos and TriBITS and develop on TriBITS for Trilinos.

Instructions for setting up to develop on TriBITS for Trilinos and performing the development processes are given at:

* http://trac.trilinos.org/wiki/TriBITSTrilinosDev

The basics are that one just needs to clone the TriBITS repo under the Trilinos base repo with:

```
$ cd Trilinos/
$ git clone git@github.com/TriBITSPub/TriBITS.git
```

and the configure Trilinos with:

```
-DTrilinos_TRIBITS_DIR:STRING=TriBITS/tribits
```

Then one can make changes to TriBITS in the local TriBITS repo clone on a branch, and then submit that branch as a [pull request](https://github.com/tribitspub/tribits/pulls).
