---
title: Managing Kubernetes Clusters for KSM
owner: Platform Engineering (KSM Team)
---

<strong><%= modified_date %></strong>

This topic describes how to register, manage, and deregister Kubernetes clusters for use with <%= vars.product_full %> (<%= vars.product_short %>).

##<a id='overview'></a> Overview

Before offering a service with <%= vars.product_short %>, you must register the Kubernetes cluster(s) that service instances
will use. <%= vars.product_short %> stores the Kubernetes cluster credentials securely in CredHub. 
This makes it possible for each plan in your KSM service offering to be provisioned to a different cluster. This may be useful for services that
require special cluster configurations. (See plans)

For each plan in your KSM offer, you must either:
+ Specify a registered Kubernetes cluster

OR
+ Before saving the offer, set a default cluster (see setting default)

##<a id='create-cluster-file'></a> Creating a cluster credentials file
1. Get your server and certificate authority by running the following commands:
    <pre class="terminal">
    $ kube_config="PATH_TO_KUBE_CONFIG"<br>
    $ cluster=`grep current $kube_config|sed "s/ //g"|cut -d ":" -f 2`<br>
    $ echo "Using cluster $cluster"<br>
    $ server=`grep -B 2 "name: $cluster" $kube_config |grep server|sed "s/ //g"|sed "s/^[^:]*://g"`<br>
    $ certificate=`grep -B 2 "name: $cluster" $kube_config|grep certificate|sed "s/ //g"|sed "s/.*://"`
    </pre> <br>
1. Create a dedicated service account for <%= vars.product_short %>
with the `cluster-admin` role:

    1. Create a YAML file for the <%= vars.product_short %> service account
    and `ClusterRoleBinding` using the following YAML:

        ```yaml
            ---
            apiVersion: v1
            kind: ServiceAccount
            metadata:
              name: ksm-admin
              namespace: kube-system
            ---
            apiVersion: rbac.authorization.k8s.io/v1beta1
            kind: ClusterRoleBinding
            metadata:
              name: ksm-cluster-admin
            roleRef:
              apiGroup: rbac.authorization.k8s.io
              kind: ClusterRole
              name: cluster-admin
            subjects:
              - kind: ServiceAccount
                name: ksm-admin
                namespace: kube-system
        ```
       
        For information about service accounts,
        see [Managing Service Accounts](https://kubernetes.io/docs/reference/access-authn-authz/service-accounts-admin)
        in the Kubernetes documentation. <br>

        For information about `ClusterRoleBinding`,
        see [RoleBinding and ClusterRoleBinding](https://kubernetes.io/docs/reference/access-authn-authz/rbac/#rolebinding-and-clusterrolebinding)
        in the Kubernetes documentation.  <br><br>
    1. Create the service account and `ClusterRoleBinding` defined in your YAML file
    by running the following command:

        ```
        kubectl apply -f SERVICE-ACCOUNT.yml
        ```
       Where `SERVICE-ACCOUNT` is name of the YAML file you created in the previous step.
       
 1. Get your service account token by running the following commands:
     <pre class="terminal">
     $ secret&#95;name=$(kubectl get serviceaccount ksm-admin \
       --namespace=kube-system -o jsonpath='{.secrets[0].name}')  <br>
     $ secret&#95;val=$(kubectl --namespace=kube-system get secret $secret&#95;name \
       -o jsonpath='{.data.token}') <br>
     $ secret_val=$(echo ${secret&#95;val} | base64 --decode)
     </pre>
 
 1. Save variables to a file:
    <pre class="terminal">
    $ cat > cluster-creds.yaml << EOF
    token: ${secret_val}
    server: ${server}
    caData: ${certificate}
    EOF
    </pre>   
       
##<a id='registering'></a> Registering Kubernetes Clusters

You must use the <%= vars.product_short %> CLI to register a Kubernetes cluster with KSM. 

To register a cluster:

1. Create a cluster credentials yaml file with server, token, and caData. See [Creating a cluster credentials file](#create-cluster-file).

1. Register a Kubernetes cluster with <%= vars.product_short %>  by running:

```
ksm cluster register CLUSTER-NAME PATH/TO/CLUSTER-CREDS.YAML
```
Where:  
+ `CLUSTER-NAME` is the name <%= vars.product_short %> will use to track the cluster. Name must be lowercase letters, numbers, and hyphens.
+ `PATH/TO/CLUSTER-CREDS.YAML`is the path to your cluster credentials file [Creating a cluster credentials file](#create-cluster-file).

##<a id='updating'></a> Updating Kubernetes Clusters
To update the credentials for an existing cluster that has already been registered with <%= vars.product_short %>: 

1. Create a cluster credentials yaml file with server, token, and caData. See [Creating a cluster credentials file](#create-cluster-file).

1. Update a registered Kubernetes cluster with <%= vars.product_short %> by running:

```
ksm cluster register CLUSTER-NAME PATH/TO/CLUSTER-CREDS.YAML --update
```
Where:  
+ `CLUSTER-NAME` is the name <%= vars.product_short %> will use to track the cluster.
+ `PATH/TO/CLUSTER-CREDS.YAML`is the path to your cluster credentials file [Creating a cluster credentials file](#create-cluster-file).

*NOTE:* If there are existing instances running on the cluster, you will be required to use the --force flag.

##<a id='set-default'></a> (Optional) Set a Default Kubernetes Cluster

If you set a default cluster, you do not need to specify a cluster when you create an offer. See [Creating an offer]().

To set a default cluster:
```
ksm cluster set-default CLUSTER-NAME
```
Where:  
+ `CLUSTER-NAME` is the name you previously registered the cluster with in <%= vars.product_short %>

##<a id='listing'></a> Listing registered Kubernetes Clusters
To see a list of registered Kubernetes Clusters:
```
ksm cluster list
```
##<a id='deregistering'></a> Deregistering Kubernetes Clusters
Before deregistering a cluster, be sure that it is not the default cluster, it does not have any instances,
and the cluster is not associated with any plans in any offers.

To deregister a cluster:
```
ksm cluster deregister CLUSTER-NAME
```

Where:  
+ `CLUSTER-NAME` is the name you previously registered the cluster with in <%= vars.product_short %>
