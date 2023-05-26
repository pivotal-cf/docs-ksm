docs-ksm
==========

Docs for [Tanzu Service Manager](https://network.pivotal.io/products/tanzu-service-manager/)

## Where is the book repository?
https://github.com/pivotal-cf/docs-book-ksm

## Which branch to use?

**Note**: Provide instructions in your PRs to indicate which branches you want Docs to apply your commits to.

| Branch name | Use for… |
|-------------| ---------|
| master      | upcoming releases http://docs-pcf-staging.cfapps.io/tanzu-service-manager/1-n/ - If your PR is not version-specific, please use this branch |
| 1.0        | v1.0.x  archived here: https://docs.vmware.com/en/VMware-Tanzu-Service-Manager/1.0/tanzu-service-manager-1-0.pdf |
| 0.11       | v0.11.x  NOT IN USE no longer published |
| 0.10       | v0.10.x  NOT IN USE no longer published |
| 0.9        | v0.9.x  NOT IN USE no longer published   |
| 0.8        | v0.8.x  NOT IN USE no longer published   |
| 0.7        | v0.7.x  NOT IN USE no longer published   |
| 0.6        | v0.6.x  NOT IN USE no longer published   |
| 0.5        | v0.5.x  NOT IN USE no longer published   |
| 0.4        | v0.4.x  NOT IN USE no longer published |

## Steps for local development
```
$ git clone git@github.com:pivotal-cf/docs-layout-repo
$ git clone git@github.com:pivotal-cf/docs-ksm
$ cd docs-ksm && git checkout <branch> && cd -
$ git clone git@github.com:pivotal-cf/docs-book-ksm
$ cd docs-book-ksm
$ bundle install
$ bundle exec bookbinder watch
$ open http://127.0.0.1:XXXX/tanzu-service-manager/<branch>
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
|private container image registry| Container registries can be public or private. VMware recommends using **private** container registries. |
|public container image registry| If you mean "public container registry" or "private container registry" say so, at least on first use in the paragraph. Don't assume that the reader/learner knows which you mean. Don't shorten to "public registry" or "private registry". |

This is a list of terms found in the v0.11 doc that should be defined/standardized:

| Term| Similar term that may or may not mean the same thing |
|------|-------------|
|service offering| |
|custom service offering| cf service offering and service |
|service offering plan | cf service plan|
|service plan| cf service and service offering plan |
|private registry | |
|private container registry | cf private registry and private container image registry (above) |


## Historical Note

Previously, this repository was named docs-bazaar and the book repository was named docs-book-bazaar.
