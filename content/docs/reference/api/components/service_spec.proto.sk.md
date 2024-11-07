---
title: "service_spec.proto"
weight: 10
---

<!-- Code generated by solo-kit. DO NOT EDIT. -->


**Package**: `options.gloo.solo.io` 
**Types**:


- [ServiceSpec](#servicespec)
  



**Source File**: [github.com/solo-io/gloo/projects/gloo/api/v1/options/service_spec.proto](https://github.com/solo-io/gloo/blob/main/projects/gloo/api/v1/options/service_spec.proto)





---
### ServiceSpec

 
Describes APIs and application-level information for services
{{< reuse "docs/snippets/product-name.md" >}} routes to. ServiceSpec is contained within the UpstreamSpec for certain types
of upstreams, including Kubernetes, Consul, and Static.
ServiceSpec configuration is opaque to {{< reuse "docs/snippets/product-name.md" >}} and handled by Service Options.

```yaml
"rest": .rest.options.gloo.solo.io.ServiceSpec
"grpc": .grpc.options.gloo.solo.io.ServiceSpec
"grpcJsonTranscoder": .grpc_json.options.gloo.solo.io.GrpcJsonTranscoder

```

| Field | Type | Description |
| ----- | ---- | ----------- | 
| `rest` | [.rest.options.gloo.solo.io.ServiceSpec](../rest.proto.sk/#servicespec) |  Only one of `rest`, `grpc`, `grpcJsonTranscoder`, or `graphql` can be set. |
| `grpc` | [.grpc.options.gloo.solo.io.ServiceSpec](../grpc.proto.sk/#servicespec) |  Only one of `grpc`, `rest`, `grpcJsonTranscoder`, or `graphql` can be set. |
| `grpcJsonTranscoder` | [.grpc_json.options.gloo.solo.io.GrpcJsonTranscoder](../grpc_json.proto.sk/#grpcjsontranscoder) |  Only one of `grpcJsonTranscoder`, `rest`, `grpc`, or `graphql` can be set. |





<!-- Start of HubSpot Embed Code -->
<script type="text/javascript" id="hs-script-loader" async defer src="//js.hs-scripts.com/5130874.js"></script>
<!-- End of HubSpot Embed Code -->