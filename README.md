docs-ksm
==========

Docs for [Tanzu Service Manager](https://network.pivotal.io/products/tanzu-service-manager/)(Beta)

## Where is the book repository?
https://github.com/pivotal-cf/docs-book-ksm

## Which branch to use?

**Note**: Provide instructions in your PRs to indicate which branches you want Docs to apply your commits to.

| Branch name | Use for… |
|-------------| ---------|
| master      | upcoming releases http://docs-pcf-staging.cfapps.io/ksm/0-n/ - If your PR is not version-specific, please use this branch |
| 0.11       | v0.11.x  http://docs.pivotal.io/ksm/0-11/ |
| 0.10       | v0.10.x  http://docs.pivotal.io/ksm/0-10/ |
| 0.9        | v0.9.x  http://docs.pivotal.io/ksm/0-9/   |
| 0.8        | v0.8.x  http://docs.pivotal.io/ksm/0-8/   |
| 0.7        | v0.7.x  http://docs.pivotal.io/ksm/0-7/   |
| 0.6        | v0.6.x  http://docs.pivotal.io/ksm/0-6/   |
| 0.5        | v0.5.x  http://docs.pivotal.io/ksm/0-5/   |
| 0.4        | NOT IN USE docs have been removed http://docs.pivotal.io/ksm/0-4/ |

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

This is a word list for terminology and word usage specific to the TSMGR for docs.

| Word | Explanation |
|------|-------------|
| platform cluster | The Kubernetes cluster that the Tanzu Service Manager is installed on. |
| workload cluster |  The cluster in which Tanzu Service Manager provisions services |
| TSMGR |Acronym for Tanzu Service Manager|
| tsmgr CLI | CLI component for TSMGR. Unless you are referring to what it is called on VMware Network, Tanzu Service Manager CLIs or [OPERATIING-SYSTEM] for TSMGR, use tsmgr CLI.|
|cf marketplace| Generally, the Services Marketplace, or the Marketplace, should not be referred to in this doc. App developers do not interact with the Marketplace. They interact with `cf marketplace`.|
|private container image registry| Container registries can be public or private. VMware recommends using **private** conatiner registries. |
|public container image registry| If you mean "public container registry" or "private container registry" say so, at least on first use in the paragraph. Don't assume that the reader/learner knows which you mean. Don't shorten to "public registry" or "private registry". |


## Historical Note

Previously, this repository was named docs-bazaar and the book repository was named docs-book-bazaar.
