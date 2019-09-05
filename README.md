docs-ksm
==========

Docs for [Container Services Manager for Pivotal Cloud Foundry](https://network.pivotal.io/products/container-services-manager/) (PCF)(Beta)

## Where is the book repository?
https://github.com/pivotal-cf/docs-book-ksm

## Which branch to use?

**Note**: Provide instructions in your PRs to indicate which branches you want Docs to apply your commits to. 

| Branch name | Use for… |
|-------------| ------|
| master      | upcoming releases http://docs-pcf-staging.cfapps.io/ksm/0-n/ 
| 0.4       | v0.4.x  http://docs-pcf-staging.cfapps.io/ksm/0-4/ |

## Steps for local development
```
$ git clone git@github.com:pivotal-cf/docs-layout-repo
$ git clone git@github.com:pivotal-cf/docs-ksm
$ cd docs-ksm && git checkout <branch> && cd -
$ git clone git@github.com:pivotal-cf/docs-book-ksm
$ cd docs-book-ksm
$ bundle install
$ bundle exec bookbinder watch
$ open http://127.0.0.1:XXXX/ksm/<branch>
```


## Style Guide

This is a word list for terminology and word usage specific to the KSM for PCF docs.

| Word | Explanation |
|------|-------------|
| KSM |Acronym for Container Services Manager|
| KSM CLI | CLI component for Container Services Manager for PCF. Unless you are referring to what it is called on Pivotal Network, Container Services Manager CLIs or [OPERATIING-SYSTEM] for KSM, use KSM CLI.|
|cf marketplace| Generally, the Services Marketplace, or the Marketplace, should not be referred to in this doc. App developers do not interact with the Marketplace. They interact with `cf marketplace`.|

## Historical Note

Previously, this repository was named docs-bazaar and the book repository was named docs-book-bazaar.
