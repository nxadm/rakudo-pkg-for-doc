# rakudo-pkg-for-doc

[![Build Status](https://travis-ci.org/nxadm/rakudo-pkg-for-doc.svg?branch=master)](https://travis-ci.org/nxadm/rakudo-pkg-for-doc)

This repository is not intended for end users, but as part of the Perl 6 CI
infrastructure. See [rakudo-pkg](https://github.com/nxadm/) for user packages.

This repository is used to automatically creat a deb pkg for Rakudo and the
Perl 6 modules that are required to test the
[Perl 6 documentation](https://github.com/perl6/doc).

## Use the package for testing perl6/doc

To use the packages add this to the .travis.yml:
```yaml
env:
  global:
    - PATH="/opt/rakudo-pkg-for-doc/bin:/opt/rakudo-pkg-for-doc/share/perl6/site/bin:$PATH"
sudo: required
install:
  - echo "deb https://dl.bintray.com/nxadm/perl6-doc trusty main" | sudo tee -a /etc/apt/sources.list
  - sudo apt-get update && sudo apt-get install rakudo-pkg-for-doc
```

## New builds

In .travis.yml, bump the version and create a branch with the name
v\<version>-\<revison>, e.g. v2018.02.1-01, v2018.03-01.
