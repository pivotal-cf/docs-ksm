---
title: Managing Kubernetes Clusters for KSM
owner: Platform Engineering (KSM Team)
---

<strong><%= modified_date %></strong>

This topic describes how to register, manage, and deregister Kubernetes clusters for use with <%= vars.product_full %> (<%= vars.product_short %>).

##<a id='overview'></a> Overview

Before offering a service with <%= vars.product_short %>, you must register the Kubernetes cluster(s) that service instances
will be provisioned to and run on. <%= vars.product_short %> stores the Kubernetes cluster credentials securely in Credhub. 
This makes it possible for each plan in your KSM service offering to be provisioned to different. This may be useful for services that
require special cluster configurations. (See plans)

For each plan in your KSM service offerings, you must either:
+ Specify a registered Kubernetes cluster that service instances will be provisioned on

OR
+ Before saving the offer, set a default cluster that service instances will be provisioned on.  (see setting default)

##<a id='registering'></a> Registering Kubernetes Clusters

You must use the <%= vars.product_short %> CLI to register a Kubernetes cluster with KSM. 

To create a sample service offering directory:

1. Create a cluster credentials file with this script : link 
- this script creates  a service account with x persmission and generates a kubeconfig file that can be used to 
register the cluster with KSM

1. Register a Kubernetes cluster with <%= vars.product_short %>  by running:

```
ksm cluster register CLUSTER-NAME PATH/TO/CLUSTER-CREDS.YAML
```
Where:  
+ `CLUSTER-NAME` is the name <%= vars.product_short %> will use to track the cluster.
+ `PATH/TO/CLUSTER-CREDS.YAML`is the path to your cluster credentials file create in step 1. 

Notes- retrieve credentials 

##<a id='set-default'></a> (Optional) Set a Default Kubernetes Cluster

If a cluster is not specified in a plans.yaml, the service will be provisioned and run on a set default at the time of provision. 


