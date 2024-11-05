---
title: Host redirect
weight: 442
description: Redirect requests to a different host. 
---

Redirect requests to a different host. 

For more information, see the [{{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} documentation](https://gateway-api.sigs.k8s.io/api-types/httproute/#filters-optional).

## Before you begin

{{< reuse "docs/snippets/prereq.md" >}}

## Set up host redirects

1. Create an HTTP route for the httpbin app that you created as part of the [Get started guide](/docs/quickstart/). In the following example, requests for the `host.redirect.example` domain are redirected to the `www.example.com` hostname, and a 302 HTTP response code is returned to the user.
   ```yaml
   kubectl apply -f- <<EOF
   apiVersion: gateway.networking.k8s.io/v1beta1
   kind: HTTPRoute
   metadata:
     name: httpbin-redirect
     namespace: httpbin
   spec:
     parentRefs:
       - name: http
         namespace: gloo-system
     hostnames:
       - host.redirect.example
     rules:
       - filters:
         - type: RequestRedirect
           requestRedirect:
             hostname: "www.example.com"
             statusCode: 302
   EOF
   ```

4. Send a request to the httpbin app on the `host.redirect.example` domain and verify that you get back a 302 HTTP response code and the redirect location `www.example.com/headers`. 
   {{< tabs items="Cloud Provider LoadBalancer,Port-forward for local testing" >}}
   {{% tab %}}
   ```sh
   curl -vik http://$INGRESS_GW_ADDRESS:8080/headers -H "host: host.redirect.example:8080"
   ```
   {{% /tab %}}
   {{% tab %}}
   ```sh
   curl -vik localhost:8080/headers -H "host: host.redirect.example"
   ```
   {{% /tab %}}
   {{< /tabs >}}

   Example output: 
   ```
   * Mark bundle as not supporting multiuse
   < HTTP/1.1 302 Found
   HTTP/1.1 302 Found
   < location: http://www.example.com/headers
   location: http://www.example.com/headers
   < date: Sat, 04 Nov 2023 01:40:06 GMT
   date: Sat, 04 Nov 2023 01:40:06 GMT
   < server: envoy
   server: envoy
   < content-length: 0
   content-length: 0
   ```

## Cleanup 

{{< reuse "docs/snippets/cleanup.md" >}}

```sh
kubectl delete httproute httpbin-redirect -n httpbin
```
