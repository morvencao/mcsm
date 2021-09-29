# Application for Istio Multicluster Service Mesh

The home for istio multicluster service mesh Applications, based on the open-clutser-management.io Subscription, Channel and Placement API

## Requirements

- `open-cluster-management.io` or Red Hat Advanced Cluster Management for Kubernetes v2.3+
- `submariner-addon` enabled for the connected clusters in the mesh in managedclusterset named `mcsm-demo`.

# How to use

1. Replace the `<istio-chart-repository-url>` in `subscriptions/istio-operator/channel.yaml` and then deploy the `istio-operator` Application:

```
oc apply -k subscriptions/istio-operator
```

> Note: this is broken now, please use `istio-operator` helm chart to install it in each clusters.

2. Deploy the `istio-multicluster` Application:

```
oc apply -k subscriptions/istio-mcsm
```

3. Deploy the `bookinfo` Application:

```
oc apply -k subscriptions/bookinfo
```

4. Then you can deploy the istio configuration under `[1-6]-bookinfo-*` directories to validate the istio functions.

> Note: the number prefix is the apply order.