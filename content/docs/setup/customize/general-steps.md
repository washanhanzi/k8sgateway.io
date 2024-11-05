---
title: Customize gateway proxies
weight: 10
---

The configuration that is used to spin up a gateway proxy is stored in several custom resources, including GatewayParameters, Settings, and a gateway proxy template. By default, {{< reuse "docs/snippets/product-name.md" >}} creates these resources for you during the installation so that you can spin up gateway proxies with the [default proxy configuration](/docs/setup/default/). You have the following options to change the default configuration for your gateway proxies: 

| Option | Description | 
| -- | -- | 
| Change GatewayParameters and Settings | Adjust settings on the gateway proxy, such as additional labels, security contexts, annotations, and more, by using the GatewayParameters and Settings resources. {{< reuse "docs/snippets/product-name.md" >}} continues to manage the gateway for you. The values that you set in the GatewayParameters and Settings resources are automatically translated and applied to the gateway proxies.  |
| Create self-managed gateways with custom proxy templates | If you want to change the [default gateway proxy template](/docs/setup/default/#gateway-proxy-template) and provide your own Envoy configuration to bootstrap the proxy with, you must create a self-managed gateway. For more information, see [Self-managed gateways (BYO)](/docs/setup/customize/selfmanaged). | 

## Customize the gateway proxy 

The example in this guide uses the GatewayParameters resource to change settings on the gateway proxy. To find other customization examples, see the [Gateway customization guides](/docs/setup/customize/).

1. Optional: Review the default configuration for your gateway proxies. This configuration can help you identify the settings that you want to change or add. 
   ```sh
   kubectl get gatewayparameters gloo-gateway -n gloo-system -o yaml
   ```

2. Create a GatewayParameters resource to add any custom settings to the gateway. The following example makes the following changes: 
   * The Kubernetes service type is changed to NodePort (default value: `LoadBalancer`). 
   * The `gateway: custom` label is added to the gateway proxy service that exposes the proxy (default value: `gloo=kube-gateway`). 
   * The `gateway: custom` label is added to the gateway proxy pod (default value: `gloo=kube-gateway` ). 
   * The security context of the gateway proxy is changed to use the 50000 as the supplemental group ID and user ID (default values: `10101` ). 
   
   {{< callout type="info" >}}
   For other settings, see the [GatewayParameters proto file](https://github.com/solo-io/gloo/blob/main/projects/gateway2/api/v1alpha1/gateway_parameters_types.go) or check out the [Gateway customization guides](../).
   {{< /callout >}}
   
   ```yaml
   kubectl apply -f- <<EOF
   apiVersion: gateway.gloo.solo.io/v1alpha1
   kind: GatewayParameters
   metadata:
     name: custom-gw-params
     namespace: gloo-system
   spec:
     kube: 
       service:
         type: NodePort
         extraLabels: 
           gateway: custom
       podTemplate: 
         extraLabels:
           gateway: custom
         securityContext: 
           fsGroup: 50000
           runAsUser: 50000
   EOF
   ```

3. Create a Gateway resource that references your custom GatewayParameters by using the `gateway.gloo.solo.io/gateway-parameters-name` annotation. 
   ```yaml
   kubectl apply -f- <<EOF
   kind: Gateway
   apiVersion: gateway.networking.k8s.io/v1
   metadata:
     name: custom
     namespace: gloo-system
     annotations:
       gateway.gloo.solo.io/gateway-parameters-name: "custom-gw-params"
   spec:
     gatewayClassName: gloo-gateway
     listeners:
     - protocol: HTTP
       port: 80
       name: http
       allowedRoutes:
         namespaces:
           from: All
   EOF
   ```

4. Verify that a pod is created for your gateway proxy and that it has the pod settings that you defined in the GatewayParameters resource. 
   ```sh
   kubectl get pods -l app.kubernetes.io/name=gloo-proxy-custom -n gloo-system -o yaml
   ```
   
   {{< callout type="info" >}}
   If the pod does not come up, try running `kubectl get events -n gloo-system` to see if the Kubernetes API server logged any failures. If no events are logged, ensure that the `gloo-gateway` GatewayClass is present in your cluster and that the Gateway resource shows an `Accepted` status. 
   {{< /callout >}}
   
   Example output:
   ```yaml {linenos=table,hl_lines=[13,20,21,22],linenostart=1,filename="gateway-pod.yaml"}
   apiVersion: v1
   kind: Pod
   metadata:
     annotations:
       prometheus.io/path: /metrics
       prometheus.io/port: "9091"
       prometheus.io/scrape: "true"
     creationTimestamp: "2024-08-07T19:47:27Z"
     generateName: gloo-proxy-custom-7d9bf46f96-
     labels:
       app.kubernetes.io/instance: custom
       app.kubernetes.io/name: gloo-proxy-custom
       gateway: custom
       gateway.networking.k8s.io/gateway-name: custom
       gloo: kube-gateway
   ...
     priority: 0
     restartPolicy: Always
     schedulerName: default-scheduler
     securityContext:
       fsGroup: 50000
       runAsUser: 50000
   ...
   ```

5. Get the details of the service that exposes the gateway proxy. Verify that the service is of type NodePort and that the extra label was added to the service. 
   ```sh
   kubectl get service gloo-proxy-custom -n gloo-system -o yaml
   ```
   
   Example output: 
   ```yaml {linenos=table,hl_lines=[12,36],linenostart=1,filename="gateway-service.yaml"}
   apiVersion: v1
   kind: Service
   metadata:
     creationTimestamp: "2024-08-07T19:47:27Z"
     labels:
       app.kubernetes.io/instance: custom
       app.kubernetes.io/managed-by: Helm
       app.kubernetes.io/name: gloo-proxy-custom
       app.kubernetes.io/version: 2.0.0-alpha1
       gateway: custom
       gateway.networking.k8s.io/gateway-name: custom
       gloo: kube-gateway
       helm.sh/chart: gloo-gateway-0.0.1-alpha1
     name: gloo-proxy-custom
     namespace: gloo-system
     ownerReferences:
     - apiVersion: gateway.networking.k8s.io/v1
       controller: true
       kind: Gateway
       name: custom
       uid: d29417ba-60f9-410c-a023-283b250f3d57
     resourceVersion: "7371789"
     uid: 67945b5f-e55f-42bb-b5f2-c35932659831
   spec:
     ports:
     - name: http
       nodePort: 30579
       port: 80
       protocol: TCP
       targetPort: 8080
     selector:
       app.kubernetes.io/instance: custom
       app.kubernetes.io/name: gloo-proxy-custom
       gateway.networking.k8s.io/gateway-name: custom
     sessionAffinity: None
     type: NodePort
   ```
   

## Cleanup

{{< reuse "docs/snippets/cleanup.md" >}}

```sh
kubectl delete gateway custom -n gloo-system
kubectl delete gatewayparameters custom-gw-params -n gloo-system
```
   
   