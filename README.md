# rhoai-install
Custum Resource Definitions for installing Red Hat OpenShift AI 


## Operators

Located in `k8/operators` directory:

- OpenShift Pipelines
- OpenShift ServiceMesh 2.x (latest stable version)
- OpenShift Serverless
- OpenShift AI

## Cluster Resource Definitions

Located in `k8/operators` directory:

- DataScienceCluster

## Install Operators

Run the following command

```bash
oc apply -f k8/operators
```

Wait for all operators to become ready.  

## Install DataCenterCluster

Run the following command:

```bash
oc apply -f k8/cluster
```

Wait for the datasciencecluster default-dsc to be ready

Example:
```bash
oc get datasciencecluster default-dsc                                                                                        

NAME          READY   REASON
default-dsc   True    
```

## Get Route to OpenShift AI Dashboard

To get the route to the OpenShift AI Dashboard, Select the 6 x 6 grid at the top of the OpenShift Web Console and select `Red Hat OpenShift AI` or run the following command to get it's URL/Route

```bash
oc get route rhods-dashboard -n redhat-ods-applications -o jsonpath='{.spec.host}'
```

Copy and paste the output into a web browser