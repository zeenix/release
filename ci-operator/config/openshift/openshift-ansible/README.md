Building openshift-ansible image
======

* `rpm_build_commands` - use `tito` to build RPMs and put them in the repo dir. tito doesn't create repodata, so `createrepo` is used for that
* `test_binary_build_commands` prepares unit test image - installs tox and makes `/etc/passwd` writable
* `tests`:
  1. unit tests - ensures temporary openshift user has `/etc/passwd` entry and runs tox
  2. autogenerated tests using ci-operator