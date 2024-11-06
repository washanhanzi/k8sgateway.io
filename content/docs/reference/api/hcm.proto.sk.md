---
title: "hcm.proto"
weight: 10
---

<!-- Code generated by solo-kit. DO NOT EDIT. -->


**Package**: `hcm.options.gloo.solo.io` 
***Types**:


- [HttpConnectionManagerSettings](#httpconnectionmanagersettings)
- [SetCurrentClientCertDetails](#setcurrentclientcertdetails)
- [UuidRequestIdConfigSettings](#uuidrequestidconfigsettings)
- [CidrRange](#cidrrange)
- [InternalAddressConfig](#internaladdressconfig)
- [ForwardClientCertDetails](#forwardclientcertdetails)
- [ServerHeaderTransformation](#serverheadertransformation)
- [HeadersWithUnderscoreAction](#headerswithunderscoreaction)
- [PathWithEscapedSlashesAction](#pathwithescapedslashesaction)
- [CodecType](#codectype)
  



**Source File**: [github.com/solo-io/gloo/projects/gloo/api/v1/options/hcm/hcm.proto](https://github.com/solo-io/gloo/blob/main/projects/gloo/api/v1/options/hcm/hcm.proto)





---
### HttpConnectionManagerSettings

 
Contains various settings for Envoy's http connection manager.
See here for more information: https://www.envoyproxy.io/docs/envoy/v1.9.0/configuration/http_conn_man/http_conn_man
Now contains v3 fields as well
v3 documents https://www.envoyproxy.io/docs/envoy/latest/api-v3/extensions/filters/network/http_connection_manager/v3/http_connection_manager.proto#extensions-filters-network-http-connection-manager-v3-httpconnectionmanager

```yaml
"skipXffAppend": .google.protobuf.BoolValue
"via": .google.protobuf.StringValue
"xffNumTrustedHops": .google.protobuf.UInt32Value
"useRemoteAddress": .google.protobuf.BoolValue
"generateRequestId": .google.protobuf.BoolValue
"proxy100Continue": .google.protobuf.BoolValue
"streamIdleTimeout": .google.protobuf.Duration
"idleTimeout": .google.protobuf.Duration
"maxRequestHeadersKb": .google.protobuf.UInt32Value
"requestTimeout": .google.protobuf.Duration
"requestHeadersTimeout": .google.protobuf.Duration
"drainTimeout": .google.protobuf.Duration
"delayedCloseTimeout": .google.protobuf.Duration
"serverName": .google.protobuf.StringValue
"stripAnyHostPort": .google.protobuf.BoolValue
"acceptHttp10": .google.protobuf.BoolValue
"defaultHostForHttp10": .google.protobuf.StringValue
"allowChunkedLength": .google.protobuf.BoolValue
"enableTrailers": .google.protobuf.BoolValue
"properCaseHeaderKeyFormat": .google.protobuf.BoolValue
"preserveCaseHeaderKeyFormat": .google.protobuf.BoolValue
"tracing": .tracing.options.gloo.solo.io.ListenerTracingSettings
"forwardClientCertDetails": .hcm.options.gloo.solo.io.HttpConnectionManagerSettings.ForwardClientCertDetails
"setCurrentClientCertDetails": .hcm.options.gloo.solo.io.HttpConnectionManagerSettings.SetCurrentClientCertDetails
"preserveExternalRequestId": .google.protobuf.BoolValue
"upgrades": []protocol_upgrade.options.gloo.solo.io.ProtocolUpgradeConfig
"maxConnectionDuration": .google.protobuf.Duration
"maxStreamDuration": .google.protobuf.Duration
"maxHeadersCount": .google.protobuf.UInt32Value
"headersWithUnderscoresAction": .hcm.options.gloo.solo.io.HttpConnectionManagerSettings.HeadersWithUnderscoreAction
"maxRequestsPerConnection": .google.protobuf.UInt32Value
"serverHeaderTransformation": .hcm.options.gloo.solo.io.HttpConnectionManagerSettings.ServerHeaderTransformation
"pathWithEscapedSlashesAction": .hcm.options.gloo.solo.io.HttpConnectionManagerSettings.PathWithEscapedSlashesAction
"codecType": .hcm.options.gloo.solo.io.HttpConnectionManagerSettings.CodecType
"mergeSlashes": .google.protobuf.BoolValue
"normalizePath": .google.protobuf.BoolValue
"uuidRequestIdConfig": .hcm.options.gloo.solo.io.HttpConnectionManagerSettings.UuidRequestIdConfigSettings
"http2ProtocolOptions": .protocol.options.gloo.solo.io.Http2ProtocolOptions
"internalAddressConfig": .hcm.options.gloo.solo.io.HttpConnectionManagerSettings.InternalAddressConfig
"appendXForwardedPort": .google.protobuf.BoolValue

```

| Field | Type | Description |
| ----- | ---- | ----------- | 
| `skipXffAppend` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) |  |
| `via` | [.google.protobuf.StringValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/string-value) |  |
| `xffNumTrustedHops` | [.google.protobuf.UInt32Value](https://protobuf.dev/reference/protobuf/google.protobuf/#uint32-value) |  |
| `useRemoteAddress` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) |  |
| `generateRequestId` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) |  |
| `proxy100Continue` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) |  |
| `streamIdleTimeout` | [.google.protobuf.Duration](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/duration) |  |
| `idleTimeout` | [.google.protobuf.Duration](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/duration) |  |
| `maxRequestHeadersKb` | [.google.protobuf.UInt32Value](https://protobuf.dev/reference/protobuf/google.protobuf/#uint32-value) |  |
| `requestTimeout` | [.google.protobuf.Duration](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/duration) |  |
| `requestHeadersTimeout` | [.google.protobuf.Duration](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/duration) | The amount of time that Envoy will wait for the request headers to be received. The timer is activated when the first byte of the headers is received, and is disarmed when the last byte of the headers has been received. If not specified or set to 0, this timeout is disabled. |
| `drainTimeout` | [.google.protobuf.Duration](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/duration) |  |
| `delayedCloseTimeout` | [.google.protobuf.Duration](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/duration) |  |
| `serverName` | [.google.protobuf.StringValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/string-value) |  |
| `stripAnyHostPort` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) |  |
| `acceptHttp10` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) | For explanation of these settings see: https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/core/v3/protocol.proto#envoy-api-msg-core-http1protocoloptions. |
| `defaultHostForHttp10` | [.google.protobuf.StringValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/string-value) |  |
| `allowChunkedLength` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) | For an explanation of these settings, see: https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/core/v3/protocol.proto#config-core-v3-http1protocoloptions. |
| `enableTrailers` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) |  |
| `properCaseHeaderKeyFormat` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) | Formats the REQUEST HEADER by proper casing words: the first character and any character following a special character will be capitalized if it's an alpha character. For example, "content-type" becomes "Content-Type", and "foo$b#$are" becomes "Foo$B#$Are". Note that while this results in most headers following conventional casing, certain headers are not covered. For example, the "TE" header will be formatted as "Te". Only one of `properCaseHeaderKeyFormat` or `preserveCaseHeaderKeyFormat` can be set. |
| `preserveCaseHeaderKeyFormat` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) | Generates configuration for a stateful formatter extension that allows using received headers to affect the output of encoding headers. Specifically: preserving REQUEST HEADER case during proxying. Only one of `preserveCaseHeaderKeyFormat` or `properCaseHeaderKeyFormat` can be set. |
| `tracing` | [.tracing.options.gloo.solo.io.ListenerTracingSettings](../tracing.proto.sk/#listenertracingsettings) |  |
| `forwardClientCertDetails` | [.hcm.options.gloo.solo.io.HttpConnectionManagerSettings.ForwardClientCertDetails](#forwardclientcertdetails) |  |
| `setCurrentClientCertDetails` | [.hcm.options.gloo.solo.io.HttpConnectionManagerSettings.SetCurrentClientCertDetails](#setcurrentclientcertdetails) |  |
| `preserveExternalRequestId` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) |  |
| `upgrades` | [[]protocol_upgrade.options.gloo.solo.io.ProtocolUpgradeConfig](../protocol_upgrade.proto.sk/#protocolupgradeconfig) | HttpConnectionManager configuration for protocol upgrade requests. Note: WebSocket upgrades are enabled by default on the HTTP Connection Manager and must be explicitly disabled. |
| `maxConnectionDuration` | [.google.protobuf.Duration](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/duration) | For an explanation of these settings see https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/core/v3/protocol.proto#config-core-v3-httpprotocoloptions. |
| `maxStreamDuration` | [.google.protobuf.Duration](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/duration) | For an explanation of these settings see https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/core/v3/protocol.proto#config-core-v3-httpprotocoloptions. |
| `maxHeadersCount` | [.google.protobuf.UInt32Value](https://protobuf.dev/reference/protobuf/google.protobuf/#uint32-value) | For an explanation of these settings see https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/core/v3/protocol.proto#config-core-v3-httpprotocoloptions. |
| `headersWithUnderscoresAction` | [.hcm.options.gloo.solo.io.HttpConnectionManagerSettings.HeadersWithUnderscoreAction](#headerswithunderscoreaction) | For an explanation of these settings see https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/core/v3/protocol.proto#config-core-v3-httpprotocoloptions. |
| `maxRequestsPerConnection` | [.google.protobuf.UInt32Value](https://protobuf.dev/reference/protobuf/google.protobuf/#uint32-value) | For an explanation of these settings see https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/core/v3/protocol.proto#config-core-v3-httpprotocoloptions. |
| `serverHeaderTransformation` | [.hcm.options.gloo.solo.io.HttpConnectionManagerSettings.ServerHeaderTransformation](#serverheadertransformation) | For an explanation of the settings see: https://www.envoyproxy.io/docs/envoy/latest/api-v3/extensions/filters/network/http_connection_manager/v3/http_connection_manager.proto.html#envoy-v3-api-enum-extensions-filters-network-http-connection-manager-v3-httpconnectionmanager-serverheadertransformation. |
| `pathWithEscapedSlashesAction` | [.hcm.options.gloo.solo.io.HttpConnectionManagerSettings.PathWithEscapedSlashesAction](#pathwithescapedslashesaction) | Action to take when request URL path contains escaped slash sequences (%2F, %2f, %5C and %5c). The default value can be overridden by the :ref:`http_connection_manager.path_with_escaped_slashes_action<config_http_conn_man_runtime_path_with_escaped_slashes_action>` runtime variable. The :ref:`http_connection_manager.path_with_escaped_slashes_action_sampling<config_http_conn_man_runtime_path_with_escaped_slashes_action_enabled>` runtime variable can be used to apply the action to a portion of all requests. |
| `codecType` | [.hcm.options.gloo.solo.io.HttpConnectionManagerSettings.CodecType](#codectype) | Supplies the type of codec that the connection manager should use. See here for more information: https://www.envoyproxy.io/docs/envoy/latest/api-v3/extensions/filters/network/http_connection_manager/v3/http_connection_manager.proto#extensions-filters-network-http-connection-manager-v3-httpconnectionmanager. |
| `mergeSlashes` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) | Determines if adjacent slashes in the path are merged into one before any processing of requests by HTTP filters or routing. See here for more information: https://www.envoyproxy.io/docs/envoy/latest/api-v3/extensions/filters/network/http_connection_manager/v3/http_connection_manager.proto. |
| `normalizePath` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) | Should paths be normalized according to RFC 3986 before any processing of requests by HTTP filters or routing? Defaults to True. See here for more information: https://www.envoyproxy.io/docs/envoy/latest/api-v3/extensions/filters/network/http_connection_manager/v3/http_connection_manager.proto. |
| `uuidRequestIdConfig` | [.hcm.options.gloo.solo.io.HttpConnectionManagerSettings.UuidRequestIdConfigSettings](#uuidrequestidconfigsettings) |  |
| `http2ProtocolOptions` | [.protocol.options.gloo.solo.io.Http2ProtocolOptions](../protocol.proto.sk/#http2protocoloptions) | Additional HTTP/2 settings that are passed directly to the HTTP/2 codec. |
| `internalAddressConfig` | [.hcm.options.gloo.solo.io.HttpConnectionManagerSettings.InternalAddressConfig](#internaladdressconfig) | Configuration of internal addresses. |
| `appendXForwardedPort` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) | If true, configure Envoy to set the x-fowarded-port header to allow services to find Envoy's listener port. |




---
### SetCurrentClientCertDetails



```yaml
"subject": .google.protobuf.BoolValue
"cert": .google.protobuf.BoolValue
"chain": .google.protobuf.BoolValue
"dns": .google.protobuf.BoolValue
"uri": .google.protobuf.BoolValue

```

| Field | Type | Description |
| ----- | ---- | ----------- | 
| `subject` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) |  |
| `cert` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) |  |
| `chain` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) |  |
| `dns` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) |  |
| `uri` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) |  |




---
### UuidRequestIdConfigSettings

 
Contains setup for Envoy's UuidRequestIdConfig

```yaml
"packTraceReason": .google.protobuf.BoolValue
"useRequestIdForTraceSampling": .google.protobuf.BoolValue

```

| Field | Type | Description |
| ----- | ---- | ----------- | 
| `packTraceReason` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) | Whether the implementation alters the UUID to contain the trace sampling decision as per the `UuidRequestIdConfig` message documentation. This defaults to true. If disabled no modification to the UUID will be performed. It is important to note that if disabled, stable sampling of traces, access logs, etc. will no longer work and only random sampling will be possible. |
| `useRequestIdForTraceSampling` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) | Set whether to use :ref:`x-request-id<config_http_conn_man_headers_x-request-id>` for sampling or not. This defaults to true. See the :ref:`context propagation <arch_overview_tracing_context_propagation>` overview for more information. |




---
### CidrRange

 
Subnet mask for CIDR ranges

```yaml
"addressPrefix": string
"prefixLen": .google.protobuf.UInt32Value

```

| Field | Type | Description |
| ----- | ---- | ----------- | 
| `addressPrefix` | `string` | IPv4 or IPv6 address. |
| `prefixLen` | [.google.protobuf.UInt32Value](https://protobuf.dev/reference/protobuf/google.protobuf/#uint32-value) | Length of prefix in bits. |




---
### InternalAddressConfig

 
Manages Envoy's internal address configuration

```yaml
"unixSockets": .google.protobuf.BoolValue
"cidrRanges": []hcm.options.gloo.solo.io.HttpConnectionManagerSettings.CidrRange

```

| Field | Type | Description |
| ----- | ---- | ----------- | 
| `unixSockets` | [.google.protobuf.BoolValue](https://developers.google.com/protocol-buffers/docs/reference/csharp/class/google/protobuf/well-known-types/bool-value) | Whether unix socket addresses should be considered internal. |
| `cidrRanges` | [[]hcm.options.gloo.solo.io.HttpConnectionManagerSettings.CidrRange](../hcm.proto.sk/#cidrrange) | List of CIDR ranges that are treated as internal. |




---
### ForwardClientCertDetails



| Name | Description |
| ----- | ----------- | 
| `SANITIZE` |  |
| `FORWARD_ONLY` |  |
| `APPEND_FORWARD` |  |
| `SANITIZE_SET` |  |
| `ALWAYS_FORWARD_ONLY` |  |




---
### ServerHeaderTransformation



| Name | Description |
| ----- | ----------- | 
| `OVERWRITE` | (DEFAULT) Overwrite any Server header with the contents of server_name. |
| `APPEND_IF_ABSENT` | If no Server header is present, append Server server_name If a Server header is present, pass it through. |
| `PASS_THROUGH` | Pass through the value of the server header, and do not append a header if none is present. |




---
### HeadersWithUnderscoreAction

 
Action to take when Envoy receives client request with header names containing underscore characters. Underscore character 
is allowed in header names by the RFC-7230 and this behavior is implemented as a security measure due to systems that treat 
‘_’ and ‘-‘ as interchangeable. Envoy by default allows client request headers with underscore characters.

| Name | Description |
| ----- | ----------- | 
| `ALLOW` | ⁣Allow headers with underscores. This is the default behavior. |
| `REJECT_CLIENT_REQUEST` | ⁣Reject client request. HTTP/1 requests are rejected with the 400 status. HTTP/2 requests end with the stream reset. The “httpN.requests_rejected_with_underscores_in_headers” counter is incremented for each rejected request. |
| `DROP_HEADER` | ⁣Drop the client header with name containing underscores. The header is dropped before the filter chain is invoked and as such filters will not see dropped headers. The “httpN.dropped_headers_with_underscores” is incremented for each dropped header. |




---
### PathWithEscapedSlashesAction

 
Determines the action for request that contain %2F, %2f, %5C or %5c sequences in the URI path.
This operation occurs before URL normalization and the merge slashes transformations if they were enabled.

| Name | Description |
| ----- | ----------- | 
| `IMPLEMENTATION_SPECIFIC_DEFAULT` | Default behavior specific to implementation (i.e. Envoy) of this configuration option. Envoy, by default, takes the KEEP_UNCHANGED action. NOTE: the implementation may change the default behavior at-will. |
| `KEEP_UNCHANGED` | Keep escaped slashes. |
| `REJECT_REQUEST` | Reject client request with the 400 status. gRPC requests will be rejected with the INTERNAL (13) error code. The "httpN.downstream_rq_failed_path_normalization" counter is incremented for each rejected request. |
| `UNESCAPE_AND_REDIRECT` | Unescape %2F and %5C sequences and redirect request to the new path if these sequences were present. Redirect occurs after path normalization and merge slashes transformations if they were configured. NOTE: gRPC requests will be rejected with the INTERNAL (13) error code. This option minimizes possibility of path confusion exploits by forcing request with unescaped slashes to traverse all parties: downstream client, intermediate proxies, Envoy and upstream server. The "httpN.downstream_rq_redirected_with_normalized_path" counter is incremented for each redirected request. |
| `UNESCAPE_AND_FORWARD` | Unescape %2F and %5C sequences. Note: this option should not be enabled if intermediaries perform path based access control as it may lead to path confusion vulnerabilities. |




---
### CodecType



| Name | Description |
| ----- | ----------- | 
| `AUTO` | For every new connection, the connection manager will determine which codec to use. This mode supports both ALPN for TLS listeners as well as protocol inference for plaintext listeners. If ALPN data is available, it is preferred, otherwise protocol inference is used. In almost all cases, this is the right option to choose for this setting. |
| `HTTP1` | The connection manager will assume that the client is speaking HTTP/1.1. |
| `HTTP2` | The connection manager will assume that the client is speaking HTTP/2 (Envoy does not require HTTP/2 to take place over TLS or to use ALPN. Prior knowledge is allowed). |





<!-- Start of HubSpot Embed Code -->
<script type="text/javascript" id="hs-script-loader" async defer src="//js.hs-scripts.com/5130874.js"></script>
<!-- End of HubSpot Embed Code -->