---
title: Helm value reference
weight: 10
---

Review the Helm values for the open source {{< reuse "docs/snippets/product-name.md" >}} Helm chart.

|Option|Type|Default Value|Description|
|------|----|-----------|-------------|
|namespace.create|bool|false|create the installation namespace|
|kubeGateway.enabled|bool|false|Enable the {{< reuse "docs/snippets/product-name.md" >}} {{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} controller.|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.image.repository|string|gloo-envoy-wrapper|The image repository (name) for the container.|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.capabilities.add[]|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.capabilities.drop[]|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.privileged|bool|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.seLinuxOptions.user|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.seLinuxOptions.role|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.seLinuxOptions.type|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.seLinuxOptions.level|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.windowsOptions.gmsaCredentialSpecName|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.windowsOptions.gmsaCredentialSpec|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.windowsOptions.runAsUserName|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.windowsOptions.hostProcess|bool|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.runAsUser|int64|10101||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.runAsGroup|int64|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.runAsNonRoot|bool|true||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.readOnlyRootFilesystem|bool|true||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.allowPrivilegeEscalation|bool|false||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.procMount|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.seccompProfile.type|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.seccompProfile.localhostProfile|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.appArmorProfile.type|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.securityContext.appArmorProfile.localhostProfile|string|||
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.resources.limits.memory|string||amount of memory|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.resources.limits.cpu|string||amount of CPUs|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.resources.requests.memory|string||amount of memory|
|kubeGateway.gatewayParameters.glooGateway.envoyContainer.resources.requests.cpu|string||amount of CPUs|
|kubeGateway.gatewayParameters.glooGateway.proxyDeployment.replicas|int32|1|number of instances to deploy. If set to null, a default of 1 will be imposed.|
|kubeGateway.gatewayParameters.glooGateway.service.type|string|LoadBalancer|K8s service type. If set to null, a default of LoadBalancer will be imposed.|
|kubeGateway.gatewayParameters.glooGateway.serviceAccount.extraLabels.NAME|string||Extra labels to add to the service account.|
|kubeGateway.gatewayParameters.glooGateway.serviceAccount.extraAnnotations.NAME|string||Extra annotations to add to the service account.|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.image.repository|string|sds|The image repository (name) for the container.|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.capabilities.add[]|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.capabilities.drop[]|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.privileged|bool|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.seLinuxOptions.user|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.seLinuxOptions.role|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.seLinuxOptions.type|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.seLinuxOptions.level|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.windowsOptions.gmsaCredentialSpecName|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.windowsOptions.gmsaCredentialSpec|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.windowsOptions.runAsUserName|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.windowsOptions.hostProcess|bool|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.runAsUser|int64|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.runAsGroup|int64|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.runAsNonRoot|bool|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.readOnlyRootFilesystem|bool|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.allowPrivilegeEscalation|bool|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.procMount|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.seccompProfile.type|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.seccompProfile.localhostProfile|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.appArmorProfile.type|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.securityContext.appArmorProfile.localhostProfile|string|||
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.logLevel|string|info|Log level for sds.  Options include "info", "debug", "warn", "error", "panic" and "fatal". Default level is info.|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.sdsResources.limits.memory|string||amount of memory|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.sdsResources.limits.cpu|string||amount of CPUs|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.sdsResources.requests.memory|string||amount of memory|
|kubeGateway.gatewayParameters.glooGateway.sdsContainer.sdsResources.requests.cpu|string||amount of CPUs|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.image.tag|string|1.22.0|The image tag for the container.|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.image.repository|string|proxyv2|The image repository (name) for the container.|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.image.registry|string|docker.io/istio|The image hostname prefix and registry, such as quay.io/solo-io.|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.capabilities.add[]|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.capabilities.drop[]|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.privileged|bool|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.seLinuxOptions.user|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.seLinuxOptions.role|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.seLinuxOptions.type|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.seLinuxOptions.level|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.windowsOptions.gmsaCredentialSpecName|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.windowsOptions.gmsaCredentialSpec|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.windowsOptions.runAsUserName|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.windowsOptions.hostProcess|bool|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.runAsUser|int64|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.runAsGroup|int64|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.runAsNonRoot|bool|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.readOnlyRootFilesystem|bool|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.allowPrivilegeEscalation|bool|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.procMount|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.seccompProfile.type|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.seccompProfile.localhostProfile|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.appArmorProfile.type|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.securityContext.appArmorProfile.localhostProfile|string|||
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.logLevel|string|warning|Log level for istio-proxy. Options include "info", "debug", "warning", and "error". Default level is info Default is 'warning'.|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.istioMetaMeshId|string|cluster.local|ISTIO_META_MESH_ID Environment Variable. Warning: this value is only supported with {{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} proxy. Defaults to "cluster.local"|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.istioMetaClusterId|string|Kubernetes|ISTIO_META_CLUSTER_ID Environment Variable. Warning: this value is only supported with {{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} proxy. Defaults to "Kubernetes"|
|kubeGateway.gatewayParameters.glooGateway.istio.istioProxyContainer.istioDiscoveryAddress|string|istiod.istio-system.svc:15012|discoveryAddress field of the PROXY_CONFIG environment variable. Warning: this value is only supported with {{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} proxy. Defaults to "istiod.istio-system.svc:15012"|
|kubeGateway.gatewayParameters.glooGateway.istio.customSidecars[]|interface||Override the default Istio sidecar in gateway-proxy with a custom container. Ignored if Istio.enabled is false|
|kubeGateway.gatewayParameters.glooGateway.stats.enabled|bool|true|Enable the prometheus endpoint|
|kubeGateway.gatewayParameters.glooGateway.stats.routePrefixRewrite|string|/stats/prometheus|Set the prefix rewrite used for the prometheus endpoint|
|kubeGateway.gatewayParameters.glooGateway.stats.enableStatsRoute|bool|true|Enable the stats endpoint|
|kubeGateway.gatewayParameters.glooGateway.stats.statsRoutePrefixRewrite|string|/stats|Set the prefix rewrite used for the stats endpoint|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.enabled|bool|false|Enable the AI extension|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.image.repository|string|gloo-ai-extension|The image repository (name) for the container.|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.image.registry|string|quay.io/solo-io|The image hostname prefix and registry, such as quay.io/solo-io.|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.image.pullPolicy|string|IfNotPresent|The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.capabilities.add[]|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.capabilities.drop[]|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.privileged|bool|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.seLinuxOptions.user|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.seLinuxOptions.role|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.seLinuxOptions.type|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.seLinuxOptions.level|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.windowsOptions.gmsaCredentialSpecName|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.windowsOptions.gmsaCredentialSpec|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.windowsOptions.runAsUserName|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.windowsOptions.hostProcess|bool|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.runAsUser|int64|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.runAsGroup|int64|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.runAsNonRoot|bool|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.readOnlyRootFilesystem|bool|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.allowPrivilegeEscalation|bool|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.procMount|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.seccompProfile.type|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.seccompProfile.localhostProfile|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.appArmorProfile.type|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.securityContext.appArmorProfile.localhostProfile|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.resources.limits.memory|string||amount of memory|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.resources.limits.cpu|string||amount of CPUs|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.resources.requests.memory|string||amount of memory|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.resources.requests.cpu|string||amount of CPUs|
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].name|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].value|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.fieldRef.apiVersion|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.fieldRef.fieldPath|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.resourceFieldRef.containerName|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.resourceFieldRef.resource|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.resourceFieldRef.divisor|int64|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.resourceFieldRef.divisor|int32|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.resourceFieldRef.divisor|bool|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.resourceFieldRef.divisor[]|uint|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.resourceFieldRef.divisor[]|int32|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.resourceFieldRef.divisor[]|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.resourceFieldRef.divisor[]|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.configMapKeyRef.name|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.configMapKeyRef.key|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.configMapKeyRef.optional|bool|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.secretKeyRef.name|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.secretKeyRef.key|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.env[].valueFrom.secretKeyRef.optional|bool|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.ports[].name|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.ports[].hostPort|int32|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.ports[].containerPort|int32|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.ports[].protocol|string|||
|kubeGateway.gatewayParameters.glooGateway.aiExtension.ports[].hostIP|string|||
|kubeGateway.gatewayParameters.glooGateway.floatingUserId|bool||If true, allows the cluster to dynamically assign a user ID for the processes running in the container. Default is false.|
|settings.watchNamespaces[]|string||whitelist of namespaces for Gloo Edge to watch for services and CRDs. Empty list means all namespaces. If this and WatchNamespaceSelectors are specified, this takes precedence and WatchNamespaceSelectors is ignored|
|settings.watchNamespaceSelectors|interface||A list of Kubernetes selectors that specify the set of namespaces to restrict the namespaces that Gloo controllers take into consideration when watching for resources. Elements in the list are disjunctive (OR semantics), i.e. a namespace will be included if it matches any selector. An empty list means all namespaces. If this and WatchNamespaces are specified, WatchNamespaces takes precedence and this is ignored|
|settings.writeNamespace|string||namespace where intermediary CRDs will be written to, e.g. Upstreams written by Gloo Edge Discovery.|
|settings.integrations.knative.enabled|bool|false|enabled knative components|
|settings.integrations.knative.version|string|0.10.0|the version of knative installed to the cluster. if using version < 0.8.0, Gloo Edge will use Knative's ClusterIngress API for configuration rather than the namespace-scoped Ingress|
|settings.integrations.knative.proxy.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|settings.integrations.knative.proxy.image.repository|string|gloo-envoy-wrapper|The image repository (name) for the container.|
|settings.integrations.knative.proxy.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|settings.integrations.knative.proxy.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|settings.integrations.knative.proxy.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|settings.integrations.knative.proxy.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|settings.integrations.knative.proxy.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|settings.integrations.knative.proxy.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|settings.integrations.knative.proxy.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|settings.integrations.knative.proxy.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|settings.integrations.knative.proxy.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|settings.integrations.knative.proxy.httpPort|int|8080|HTTP port for the proxy|
|settings.integrations.knative.proxy.httpsPort|int|8443|HTTPS port for the proxy|
|settings.integrations.knative.proxy.tracing|string||tracing configuration|
|settings.integrations.knative.proxy.runAsUser|float64||Explicitly set the user ID for the pod to run as. Default is 10101|
|settings.integrations.knative.proxy.loopBackAddress|string|127.0.0.1|Name on which to bind the loop-back interface for this instance of Envoy. Defaults to 127.0.0.1, but other common values may be localhost or ::1|
|settings.integrations.knative.proxy.stats|bool||Controls whether or not Envoy stats are enabled|
|settings.integrations.knative.proxy.extraClusterIngressProxyLabels.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.labels data of the cluster ingress proxy deployment.|
|settings.integrations.knative.proxy.extraClusterIngressProxyAnnotations.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.annotations data of the cluster ingress proxy deployment.|
|settings.integrations.knative.proxy.internal.deployment.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|settings.integrations.knative.proxy.internal.service.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|settings.integrations.knative.proxy.internal.configMap.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|settings.integrations.knative.proxy.replicas|int|1|number of instances to deploy|
|settings.integrations.knative.proxy.customEnv[].name|string|||
|settings.integrations.knative.proxy.customEnv[].value|string|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.fieldRef.apiVersion|string|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.fieldRef.fieldPath|string|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.resourceFieldRef.containerName|string|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.resourceFieldRef.resource|string|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.resourceFieldRef.divisor|int64|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.resourceFieldRef.divisor|int32|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.resourceFieldRef.divisor|bool|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.resourceFieldRef.divisor[]|uint|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.resourceFieldRef.divisor[]|int32|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.configMapKeyRef.name|string|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.configMapKeyRef.key|string|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.configMapKeyRef.optional|bool|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.secretKeyRef.name|string|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.secretKeyRef.key|string|||
|settings.integrations.knative.proxy.customEnv[].valueFrom.secretKeyRef.optional|bool|||
|settings.integrations.knative.proxy.restartPolicy|string||restart policy to use when the pod exits|
|settings.integrations.knative.proxy.priorityClassName|string||name of a defined priority class|
|settings.integrations.knative.proxy.nodeName|string||name of node to run on|
|settings.integrations.knative.proxy.nodeSelector.NAME|string||label selector for nodes|
|settings.integrations.knative.proxy.tolerations[].key|string|||
|settings.integrations.knative.proxy.tolerations[].operator|string|||
|settings.integrations.knative.proxy.tolerations[].value|string|||
|settings.integrations.knative.proxy.tolerations[].effect|string|||
|settings.integrations.knative.proxy.tolerations[].tolerationSeconds|int64|||
|settings.integrations.knative.proxy.affinity.NAME|interface|||
|settings.integrations.knative.proxy.hostAliases[]|interface|||
|settings.integrations.knative.proxy.initContainers[]|interface||[InitContainers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of initContainers on the deployment.|
|settings.integrations.knative.proxy.resources.limits.memory|string||amount of memory|
|settings.integrations.knative.proxy.resources.limits.cpu|string||amount of CPUs|
|settings.integrations.knative.proxy.resources.requests.memory|string||amount of memory|
|settings.integrations.knative.proxy.resources.requests.cpu|string||amount of CPUs|
|settings.integrations.knative.proxy.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|settings.integrations.knative.proxy.service.type|string|LoadBalancer|K8s service type|
|settings.integrations.knative.proxy.service.extraAnnotations.NAME|string||extra annotations to add to the service|
|settings.integrations.knative.proxy.service.loadBalancerIP|string||IP address of the load balancer|
|settings.integrations.knative.proxy.service.httpPort|int|80|HTTP port for the knative/ingress proxy service|
|settings.integrations.knative.proxy.service.httpsPort|int|443|HTTPS port for the knative/ingress proxy service|
|settings.integrations.knative.proxy.service.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|settings.integrations.knative.proxy.configMap.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|settings.integrations.knative.proxy.deployment.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|settings.integrations.knative.proxy.containerSecurityContext.capabilities.add[]|string|||
|settings.integrations.knative.proxy.containerSecurityContext.capabilities.drop[]|string|||
|settings.integrations.knative.proxy.containerSecurityContext.privileged|bool|||
|settings.integrations.knative.proxy.containerSecurityContext.seLinuxOptions.user|string|||
|settings.integrations.knative.proxy.containerSecurityContext.seLinuxOptions.role|string|||
|settings.integrations.knative.proxy.containerSecurityContext.seLinuxOptions.type|string|||
|settings.integrations.knative.proxy.containerSecurityContext.seLinuxOptions.level|string|||
|settings.integrations.knative.proxy.containerSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|settings.integrations.knative.proxy.containerSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|settings.integrations.knative.proxy.containerSecurityContext.windowsOptions.runAsUserName|string|||
|settings.integrations.knative.proxy.containerSecurityContext.windowsOptions.hostProcess|bool|||
|settings.integrations.knative.proxy.containerSecurityContext.runAsUser|int64|||
|settings.integrations.knative.proxy.containerSecurityContext.runAsGroup|int64|||
|settings.integrations.knative.proxy.containerSecurityContext.runAsNonRoot|bool|||
|settings.integrations.knative.proxy.containerSecurityContext.readOnlyRootFilesystem|bool|||
|settings.integrations.knative.proxy.containerSecurityContext.allowPrivilegeEscalation|bool|||
|settings.integrations.knative.proxy.containerSecurityContext.procMount|string|||
|settings.integrations.knative.proxy.containerSecurityContext.seccompProfile.type|string|||
|settings.integrations.knative.proxy.containerSecurityContext.seccompProfile.localhostProfile|string|||
|settings.integrations.knative.proxy.containerSecurityContext.appArmorProfile.type|string|||
|settings.integrations.knative.proxy.containerSecurityContext.appArmorProfile.localhostProfile|string|||
|settings.integrations.knative.proxy.containerSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|settings.integrations.knative.requireIngressClass|bool||only serve traffic for Knative Ingress objects with the annotation 'networking.knative.dev/ingress.class: gloo.ingress.networking.knative.dev'.|
|settings.integrations.knative.extraKnativeInternalLabels.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.labels data of the knative internal deployment.|
|settings.integrations.knative.extraKnativeInternalAnnotations.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.annotations data of the knative internal deployment.|
|settings.integrations.knative.extraKnativeExternalLabels.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.labels data of the knative external deployment.|
|settings.integrations.knative.extraKnativeExternalAnnotations.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.annotations data of the knative external deployment.|
|settings.integrations.consul.datacenter|string||Datacenter to use. If not provided, the default agent datacenter is used.|
|settings.integrations.consul.username|string||Username to use for HTTP Basic Authentication.|
|settings.integrations.consul.password|string||Password to use for HTTP Basic Authentication.|
|settings.integrations.consul.token|string||Token is used to provide a per-request ACL token which overrides the agent's default token.|
|settings.integrations.consul.caFile|string||caFile is the optional path to the CA certificate used for Consul communication, defaults to the system bundle if not specified.|
|settings.integrations.consul.caPath|string||caPath is the optional path to a directory of CA certificates to use for Consul communication, defaults to the system bundle if not specified.|
|settings.integrations.consul.certFile|string||CertFile is the optional path to the certificate for Consul communication. If this is set then you need to also set KeyFile.|
|settings.integrations.consul.keyFile|string||KeyFile is the optional path to the private key for Consul communication. If this is set then you need to also set CertFile.|
|settings.integrations.consul.insecureSkipVerify|bool||InsecureSkipVerify if set to true will disable TLS host verification.|
|settings.integrations.consul.waitTime|string||WaitTime limits how long a watches for Consul resources will block. If not provided, the agent default values will be used.|
|settings.integrations.consul.serviceDiscovery.dataCenters[]|string||Use this parameter to restrict the data centers that will be considered when discovering and routing to services. If not provided, Gloo Edge will use all available data centers.|
|settings.integrations.consul.httpAddress|string||The address of the Consul HTTP server. Used by service discovery and key-value storage (if-enabled). Defaults to the value of the standard CONSUL_HTTP_ADDR env if set, otherwise to 127.0.0.1:8500.|
|settings.integrations.consul.dnsAddress|string||The address of the DNS server used to resolve hostnames in the Consul service address. Used by service discovery (required when Consul service instances are stored as DNS names). Defaults to 127.0.0.1:8600. (the default Consul DNS server)|
|settings.integrations.consul.dnsPollingInterval|string||The polling interval for the DNS server. If there is a Consul service address with a hostname instead of an IP, Gloo Edge will resolve the hostname with the configured frequency to update endpoints with any changes to DNS resolution. Defaults to 5s.|
|settings.integrations.consulUpstreamDiscovery.useTlsTagging|bool||Allow Gloo Edge to automatically apply tls to consul services that are tagged the tlsTagName value. Requires RootCaResourceNamespace and RootCaResourceName to be set if true.|
|settings.integrations.consulUpstreamDiscovery.tlsTagName|string||The tag Gloo Edge should use to identify consul services that ought to use TLS. If splitTlsServices is true, then this tag is also used to sort serviceInstances into the tls upstream. Defaults to 'glooUseTls'.|
|settings.integrations.consulUpstreamDiscovery.splitTlsServices|bool||If true, then create two upstreams to be created when a consul service contains the tls tag; one with TLS and one without.|
|settings.integrations.consulUpstreamDiscovery.rootCa.namespace|string||The namespace of this resource.|
|settings.integrations.consulUpstreamDiscovery.rootCa.name|string||The name of this resource.|
|settings.create|bool|true|create a Settings CRD which provides bootstrap configuration to Gloo Edge controllers|
|settings.extensions|interface|||
|settings.singleNamespace|bool||Enable to use install namespace as WatchNamespace and WriteNamespace|
|settings.invalidConfigPolicy.replaceInvalidRoutes|bool|false|Rather than pausing configuration updates, in the event of an invalid Route defined on a virtual service or route table, Gloo Edge will serve the route with a predefined direct response action. This allows valid routes to be updated when other routes are invalid.|
|settings.invalidConfigPolicy.invalidRouteResponseCode|int64|404|the response code for the direct response|
|settings.invalidConfigPolicy.invalidRouteResponseBody|string|{{< reuse "docs/snippets/product-name.md" >}} has invalid configuration. Administrators should run `glooctl check` to find and fix config errors.|the response body for the direct response|
|settings.linkerd|bool|false|Enable automatic Linkerd integration in Gloo Edge|
|settings.disableProxyGarbageCollection|bool|false|Set this option to determine the state of an Envoy listener when the corresponding Proxy resource has no routes. If false (default), Gloo Edge will propagate the state of the Proxy to Envoy, resetting the listener to a clean slate with no routes. If true, Gloo Edge will keep serving the routes from the last applied valid configuration.|
|settings.regexMaxProgramSize|uint32|1024|Set this field to specify the RE2 default max program size which is a rough estimate of how complex the compiled regex is to evaluate. If not specified, this defaults to 1024.|
|settings.disableKubernetesDestinations|bool|false|Enable or disable Gloo Edge to scan Kubernetes services in the cluster and create in-memory Upstream resources to represent them. These resources enable Gloo Edge to route requests to a Kubernetes service. Note that if you have a large number of services in your cluster and you do not restrict the namespaces that Gloo Edge watches, the API snapshot increases which can have a negative impact on the Gloo Edge translation time. In addition, load balancing is done in kube-proxy which can have further performance impacts. Using Gloo Upstreams as a routing destination bypasses kube-proxy as the request is routed to the pod directly. Alternatively, you can use [Kubernetes](https://docs.solo.io/gloo-edge/latest/reference/api/github.com/solo-io/gloo/projects/gloo/api/v1/options/kubernetes/kubernetes.proto.sk/) Upstream resources as a routing destination to forward requests to the pod directly. For more information, see the [docs](https://docs.solo.io/gloo-edge/latest/guides/traffic_management/destination_types/kubernetes_services/).|
|settings.aws.enableCredentialsDiscovery|bool||Enable AWS credentials discovery in Envoy for lambda requests. If enableServiceAccountCredentials is also set, it will take precedence as only one may be enabled in Gloo Edge|
|settings.aws.enableServiceAccountCredentials|bool||Use ServiceAccount credentials to authenticate lambda requests. If enableCredentialsDiscovery is also set, this will take precedence as only one may be enabled in Gloo Edge|
|settings.aws.stsCredentialsRegion|string||Regional endpoint to use for AWS STS requests. If empty will default to global sts endpoint.|
|settings.aws.propagateOriginalRouting|bool||Send downstream path and method as x-envoy-original-path and x-envoy-original-method headers on the request to AWS lambda.|
|settings.aws.credential_refresh_delay.seconds|int32||The value of this duration in seconds.|
|settings.aws.credential_refresh_delay.nanos|int32||The value of this duration in nanoseconds.|
|settings.aws.fallbackToFirstFunction|bool||It will use the first function which if discovery is enabled the first function is the first function name alphabetically from the last discovery run. Defaults to false.|
|settings.rateLimit|interface||Partial config for Gloo Edge Enterprise’s rate-limiting service, based on Envoy’s rate-limit service; supports Envoy’s rate-limit service API. (reference here: https://github.com/lyft/ratelimit#configuration) Configure rate-limit descriptors here, which define the limits for requests based on their descriptors. Configure rate-limits (composed of actions, which define how request characteristics get translated into descriptors) on the VirtualHost or its routes.|
|settings.ratelimitServer|interface||External Ratelimit Server configuration for Gloo Edge Open Sources’s rate-limiting service, based on Envoy’s rate-limit service; supports Envoy’s rate-limit service API. (reference here: https://docs.solo.io/gloo-edge/main/guides/security/rate_limiting/)|
|settings.circuitBreakers.maxConnections|uint32||Set this field to specify the maximum number of connections that Envoy will make to the upstream cluster. If not specified, the default is 1024.|
|settings.circuitBreakers.maxPendingRequests|uint32||Set this field to specify the maximum number of pending requests that Envoy will allow to the upstream cluster. If not specified, the default is 1024.|
|settings.circuitBreakers.maxRequests|uint32||Set this field to specify the maximum number of parallel requests that Envoy will make to the upstream cluster. If not specified, the default is 1024.|
|settings.circuitBreakers.maxRetries|uint32||Set this field to specify the maximum number of parallel retries that Envoy will allow to the upstream cluster. If not specified, the default is 3.|
|settings.enableRestEds|bool|false|Whether or not to use rest xds for all EDS by default. Defaults to false.|
|settings.devMode|bool||Whether or not to enable dev mode. Defaults to false. Setting to true at install time will expose the gloo dev admin endpoint on port 10010. Not recommended for production. Warning: this value is deprecated as of 1.17 and will be removed in a future release.|
|settings.secretOptions.sources[].vault.address|string||Address of the Vault server. This should be a complete URL such as http://solo.io and include port if necessary (vault's default port is 8200).|
|settings.secretOptions.sources[].vault.rootKey|string||All keys stored in Vault will begin with this Vault this can be used to run multiple instances of Gloo against the same Vault cluster defaults to gloo.|
|settings.secretOptions.sources[].vault.pathPrefix|string||Optional. The name of a Vault Secrets Engine to which Vault should route traffic. For more info see https://learn.hashicorp.com/tutorials/vault/getting-started-secrets-engines. Defaults to 'secret'.|
|settings.secretOptions.sources[].vault.tlsConfig.caCert|string||Path to a PEM-encoded CA cert file to use to verify the Vault server SSL certificate.|
|settings.secretOptions.sources[].vault.tlsConfig.caPath|string||Path to a directory of PEM-encoded CA cert files to verify the Vault server SSL certificate.|
|settings.secretOptions.sources[].vault.tlsConfig.clientCert|string||Path to the certificate for Vault communication.|
|settings.secretOptions.sources[].vault.tlsConfig.clientKey|string||Path to the private key for Vault communication.|
|settings.secretOptions.sources[].vault.tlsConfig.tlsServerName|string||If set, it is used to set the SNI host when connecting via TLS.|
|settings.secretOptions.sources[].vault.tlsConfig.insecure|bool||Disables TLS verification when set to true.|
|settings.secretOptions.sources[].vault.accessToken|string||Vault token to use for authentication. Only one of accessToken or aws may be set.|
|settings.secretOptions.sources[].vault.aws.vaultRole|string||The Vault role we are trying to authenticate to. This is not necessarily the same as the AWS role to which the Vault role is configured.|
|settings.secretOptions.sources[].vault.aws.region|string||The AWS region to use for the login attempt.|
|settings.secretOptions.sources[].vault.aws.iamServerIdHeader|string||The IAM Server ID Header required to be included in the request.|
|settings.secretOptions.sources[].vault.aws.mountPath|string||The Vault path on which the AWS auth is mounted.|
|settings.secretOptions.sources[].vault.aws.accessKeyID|string||Optional. The Access Key ID as provided by the security credentials on the AWS IAM resource. In cases such as receiving temporary credentials through assumed roles with AWS Security Token Service (STS) or IAM Roles for Service Accounts (IRSA), this field can be omitted. https://developer.hashicorp.com/vault/docs/auth/aws#iam-authentication-inferences.|
|settings.secretOptions.sources[].vault.aws.secretAccessKey|string||Optional. The Secret Access Key as provided by the security credentials on the AWS IAM resource. In cases such as receiving temporary credentials through assumed roles with AWS Security Token Service (STS) or IAM Roles for Service Accounts (IRSA), this field can be omitted. https://developer.hashicorp.com/vault/docs/auth/aws#iam-authentication-inferences.|
|settings.secretOptions.sources[].vault.aws.sessionToken|string||The Session Token as provided by the security credentials on the AWS IAM resource.|
|settings.secretOptions.sources[].vault.aws.leaseIncrement|uint32||The time increment, in seconds, used in renewing the lease of the Vault token. See: https://developer.hashicorp.com/vault/docs/concepts/lease#lease-durations-and-renewal. Defaults to 0, which causes the default TTL to be used.|
|settings.secretOptions.sources[].directory.directory|string||Directory to read secrets from.|
|settings.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gloo.deployment.xdsPort|int|9977|port where gloo serves xDS API to Envoy.|
|gloo.deployment.restXdsPort|uint32|9976|port where gloo serves REST xDS API to Envoy.|
|gloo.deployment.validationPort|int|9988|port where gloo serves gRPC Proxy Validation to Gateway.|
|gloo.deployment.proxyDebugPort|int|9966|port where gloo serves gRPC Proxy contents to glooctl.|
|gloo.deployment.stats.enabled|bool||Controls whether or not Envoy stats are enabled|
|gloo.deployment.stats.routePrefixRewrite|string||The Envoy stats endpoint to which the metrics are written|
|gloo.deployment.stats.setDatadogAnnotations|bool||Sets the default datadog annotations|
|gloo.deployment.stats.enableStatsRoute|bool||Enables an additional route to the stats cluster defaulting to /stats|
|gloo.deployment.stats.statsPrefixRewrite|string||The Envoy stats endpoint with general metrics for the additional stats route|
|gloo.deployment.stats.serviceMonitorEnabled|bool||Whether or not to expose an http-monitoring port that can be scraped by a Prometheus Service Monitor. Requires that 'enabled' is also true|
|gloo.deployment.stats.podMonitorEnabled|bool||Whether or not to expose an http-monitoring port that can be scraped by a Prometheus Pod Monitor. Requires that 'enabled' is also true|
|gloo.deployment.floatingUserId|bool||If true, allows the cluster to dynamically assign a user ID for the processes running in the container. If a SecurityContext is defined for the container, this value is not applied for the container.|
|gloo.deployment.runAsUser|float64||Explicitly set the user ID for the processes in the container to run as. Default is 10101. If a SecurityContext is defined for the pod or container, this value is not applied for the pod/container.|
|gloo.deployment.externalTrafficPolicy|string||Set the external traffic policy on the gloo service.|
|gloo.deployment.extraGlooLabels.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.labels data of the primary gloo deployment.|
|gloo.deployment.extraGlooAnnotations.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.annotations data of the primary gloo deployment.|
|gloo.deployment.livenessProbeEnabled|bool||Set to true to enable a liveness probe for Gloo Edge (default is false).|
|gloo.deployment.ossImageTag|string|<release_version, ex: 1.2.3>|Used for debugging. The version of Gloo OSS that the current version of Gloo Enterprise was built with.|
|gloo.deployment.podSecurityContext.seLinuxOptions.user|string|||
|gloo.deployment.podSecurityContext.seLinuxOptions.role|string|||
|gloo.deployment.podSecurityContext.seLinuxOptions.type|string|||
|gloo.deployment.podSecurityContext.seLinuxOptions.level|string|||
|gloo.deployment.podSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|gloo.deployment.podSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|gloo.deployment.podSecurityContext.windowsOptions.runAsUserName|string|||
|gloo.deployment.podSecurityContext.windowsOptions.hostProcess|bool|||
|gloo.deployment.podSecurityContext.runAsUser|int64|||
|gloo.deployment.podSecurityContext.runAsGroup|int64|||
|gloo.deployment.podSecurityContext.runAsNonRoot|bool|||
|gloo.deployment.podSecurityContext.supplementalGroups[]|int64|||
|gloo.deployment.podSecurityContext.supplementalGroupsPolicy|string|||
|gloo.deployment.podSecurityContext.fsGroup|int64|||
|gloo.deployment.podSecurityContext.sysctls[].name|string|||
|gloo.deployment.podSecurityContext.sysctls[].value|string|||
|gloo.deployment.podSecurityContext.fsGroupChangePolicy|string|||
|gloo.deployment.podSecurityContext.seccompProfile.type|string|||
|gloo.deployment.podSecurityContext.seccompProfile.localhostProfile|string|||
|gloo.deployment.podSecurityContext.appArmorProfile.type|string|||
|gloo.deployment.podSecurityContext.appArmorProfile.localhostProfile|string|||
|gloo.deployment.podSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|gloo.deployment.replicas|int|1|number of instances to deploy|
|gloo.deployment.customEnv[].name|string|||
|gloo.deployment.customEnv[].value|string|||
|gloo.deployment.customEnv[].valueFrom.fieldRef.apiVersion|string|||
|gloo.deployment.customEnv[].valueFrom.fieldRef.fieldPath|string|||
|gloo.deployment.customEnv[].valueFrom.resourceFieldRef.containerName|string|||
|gloo.deployment.customEnv[].valueFrom.resourceFieldRef.resource|string|||
|gloo.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|int64|||
|gloo.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|int32|||
|gloo.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|bool|||
|gloo.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|uint|||
|gloo.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|int32|||
|gloo.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|gloo.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|gloo.deployment.customEnv[].valueFrom.configMapKeyRef.name|string|||
|gloo.deployment.customEnv[].valueFrom.configMapKeyRef.key|string|||
|gloo.deployment.customEnv[].valueFrom.configMapKeyRef.optional|bool|||
|gloo.deployment.customEnv[].valueFrom.secretKeyRef.name|string|||
|gloo.deployment.customEnv[].valueFrom.secretKeyRef.key|string|||
|gloo.deployment.customEnv[].valueFrom.secretKeyRef.optional|bool|||
|gloo.deployment.restartPolicy|string||restart policy to use when the pod exits|
|gloo.deployment.priorityClassName|string||name of a defined priority class|
|gloo.deployment.nodeName|string||name of node to run on|
|gloo.deployment.nodeSelector.NAME|string||label selector for nodes|
|gloo.deployment.tolerations[].key|string|||
|gloo.deployment.tolerations[].operator|string|||
|gloo.deployment.tolerations[].value|string|||
|gloo.deployment.tolerations[].effect|string|||
|gloo.deployment.tolerations[].tolerationSeconds|int64|||
|gloo.deployment.affinity.NAME|interface|||
|gloo.deployment.hostAliases[]|interface|||
|gloo.deployment.initContainers[]|interface||[InitContainers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of initContainers on the deployment.|
|gloo.deployment.resources.limits.memory|string||amount of memory|
|gloo.deployment.resources.limits.cpu|string||amount of CPUs|
|gloo.deployment.resources.requests.memory|string||amount of memory|
|gloo.deployment.resources.requests.cpu|string||amount of CPUs|
|gloo.deployment.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gloo.deployment.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|gloo.deployment.image.repository|string|gloo|The image repository (name) for the container.|
|gloo.deployment.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|gloo.deployment.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|gloo.deployment.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|gloo.deployment.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|gloo.deployment.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|gloo.deployment.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|gloo.deployment.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|gloo.deployment.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|gloo.deployment.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|gloo.deployment.glooContainerSecurityContext.capabilities.add[]|string|||
|gloo.deployment.glooContainerSecurityContext.capabilities.drop[]|string|||
|gloo.deployment.glooContainerSecurityContext.privileged|bool|||
|gloo.deployment.glooContainerSecurityContext.seLinuxOptions.user|string|||
|gloo.deployment.glooContainerSecurityContext.seLinuxOptions.role|string|||
|gloo.deployment.glooContainerSecurityContext.seLinuxOptions.type|string|||
|gloo.deployment.glooContainerSecurityContext.seLinuxOptions.level|string|||
|gloo.deployment.glooContainerSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|gloo.deployment.glooContainerSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|gloo.deployment.glooContainerSecurityContext.windowsOptions.runAsUserName|string|||
|gloo.deployment.glooContainerSecurityContext.windowsOptions.hostProcess|bool|||
|gloo.deployment.glooContainerSecurityContext.runAsUser|int64|||
|gloo.deployment.glooContainerSecurityContext.runAsGroup|int64|||
|gloo.deployment.glooContainerSecurityContext.runAsNonRoot|bool|||
|gloo.deployment.glooContainerSecurityContext.readOnlyRootFilesystem|bool|||
|gloo.deployment.glooContainerSecurityContext.allowPrivilegeEscalation|bool|||
|gloo.deployment.glooContainerSecurityContext.procMount|string|||
|gloo.deployment.glooContainerSecurityContext.seccompProfile.type|string|||
|gloo.deployment.glooContainerSecurityContext.seccompProfile.localhostProfile|string|||
|gloo.deployment.glooContainerSecurityContext.appArmorProfile.type|string|||
|gloo.deployment.glooContainerSecurityContext.appArmorProfile.localhostProfile|string|||
|gloo.deployment.glooContainerSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|gloo.serviceAccount.extraAnnotations.NAME|string||extra annotations to add to the service account|
|gloo.serviceAccount.disableAutomount|bool||disable automounting the service account to the gateway proxy. not mounting the token hardens the proxy container, but may interfere with service mesh integrations|
|gloo.serviceAccount.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gloo.splitLogOutput|bool||Set to true to send debug/info/warning logs to stdout, error/fatal/panic to stderr. Set to false to send all logs to stdout|
|gloo.service.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gloo.logLevel|string||Level at which the pod should log. Options include "info", "debug", "warn", "error", "panic" and "fatal". Default level is info|
|gloo.disableLeaderElection|bool||Set to true to disable leader election, and ensure all running replicas are considered the leader. Do not enable this with multiple replicas of Gloo|
|gloo.headerSecretRefNsMatchesUs|bool||Set to true to require that secrets sent in headers via headerSecretRefs come from the same namespace as the destination upstream. Default: false|
|gloo.podDisruptionBudget.minAvailable|string||Corresponds directly with the _minAvailable_ field in the [PodDisruptionBudgetSpec](https://kubernetes.io/docs/reference/kubernetes-api/policy-resources/pod-disruption-budget-v1/#PodDisruptionBudgetSpec). This value is mutually exclusive with _maxUnavailable_.|
|gloo.podDisruptionBudget.maxUnavailable|string||Corresponds directly with the _maxUnavailable_ field in the [PodDisruptionBudgetSpec](https://kubernetes.io/docs/reference/kubernetes-api/policy-resources/pod-disruption-budget-v1/#PodDisruptionBudgetSpec). This value is mutually exclusive with _minAvailable_.|
|discovery.deployment.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|discovery.deployment.image.repository|string|discovery|The image repository (name) for the container.|
|discovery.deployment.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|discovery.deployment.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|discovery.deployment.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|discovery.deployment.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|discovery.deployment.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|discovery.deployment.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|discovery.deployment.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|discovery.deployment.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|discovery.deployment.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|discovery.deployment.stats.enabled|bool||Controls whether or not Envoy stats are enabled|
|discovery.deployment.stats.routePrefixRewrite|string||The Envoy stats endpoint to which the metrics are written|
|discovery.deployment.stats.setDatadogAnnotations|bool||Sets the default datadog annotations|
|discovery.deployment.stats.enableStatsRoute|bool||Enables an additional route to the stats cluster defaulting to /stats|
|discovery.deployment.stats.statsPrefixRewrite|string||The Envoy stats endpoint with general metrics for the additional stats route|
|discovery.deployment.stats.serviceMonitorEnabled|bool||Whether or not to expose an http-monitoring port that can be scraped by a Prometheus Service Monitor. Requires that 'enabled' is also true|
|discovery.deployment.stats.podMonitorEnabled|bool||Whether or not to expose an http-monitoring port that can be scraped by a Prometheus Pod Monitor. Requires that 'enabled' is also true|
|discovery.deployment.floatingUserId|bool||If true, allows the cluster to dynamically assign a user ID for the processes running in the container.|
|discovery.deployment.runAsUser|float64||Explicitly set the user ID for the processes in the container to run as. Default is 10101.|
|discovery.deployment.fsGroup|float64||Explicitly set the group ID for volume ownership. Default is 10101|
|discovery.deployment.extraDiscoveryLabels.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.labels data of the gloo edge discovery deployment.|
|discovery.deployment.extraDiscoveryAnnotations.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.annotations data of the gloo edge discovery deployment.|
|discovery.deployment.enablePodSecurityContext|bool|true|Whether or not to render the pod security context. Default is true|
|discovery.deployment.discoveryContainerSecurityContext.capabilities.add[]|string|||
|discovery.deployment.discoveryContainerSecurityContext.capabilities.drop[]|string|||
|discovery.deployment.discoveryContainerSecurityContext.privileged|bool|||
|discovery.deployment.discoveryContainerSecurityContext.seLinuxOptions.user|string|||
|discovery.deployment.discoveryContainerSecurityContext.seLinuxOptions.role|string|||
|discovery.deployment.discoveryContainerSecurityContext.seLinuxOptions.type|string|||
|discovery.deployment.discoveryContainerSecurityContext.seLinuxOptions.level|string|||
|discovery.deployment.discoveryContainerSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|discovery.deployment.discoveryContainerSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|discovery.deployment.discoveryContainerSecurityContext.windowsOptions.runAsUserName|string|||
|discovery.deployment.discoveryContainerSecurityContext.windowsOptions.hostProcess|bool|||
|discovery.deployment.discoveryContainerSecurityContext.runAsUser|int64|||
|discovery.deployment.discoveryContainerSecurityContext.runAsGroup|int64|||
|discovery.deployment.discoveryContainerSecurityContext.runAsNonRoot|bool|||
|discovery.deployment.discoveryContainerSecurityContext.readOnlyRootFilesystem|bool|||
|discovery.deployment.discoveryContainerSecurityContext.allowPrivilegeEscalation|bool|||
|discovery.deployment.discoveryContainerSecurityContext.procMount|string|||
|discovery.deployment.discoveryContainerSecurityContext.seccompProfile.type|string|||
|discovery.deployment.discoveryContainerSecurityContext.seccompProfile.localhostProfile|string|||
|discovery.deployment.discoveryContainerSecurityContext.appArmorProfile.type|string|||
|discovery.deployment.discoveryContainerSecurityContext.appArmorProfile.localhostProfile|string|||
|discovery.deployment.discoveryContainerSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|discovery.deployment.replicas|int|1|number of instances to deploy|
|discovery.deployment.customEnv[].name|string|||
|discovery.deployment.customEnv[].value|string|||
|discovery.deployment.customEnv[].valueFrom.fieldRef.apiVersion|string|||
|discovery.deployment.customEnv[].valueFrom.fieldRef.fieldPath|string|||
|discovery.deployment.customEnv[].valueFrom.resourceFieldRef.containerName|string|||
|discovery.deployment.customEnv[].valueFrom.resourceFieldRef.resource|string|||
|discovery.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|int64|||
|discovery.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|int32|||
|discovery.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|bool|||
|discovery.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|uint|||
|discovery.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|int32|||
|discovery.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|discovery.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|discovery.deployment.customEnv[].valueFrom.configMapKeyRef.name|string|||
|discovery.deployment.customEnv[].valueFrom.configMapKeyRef.key|string|||
|discovery.deployment.customEnv[].valueFrom.configMapKeyRef.optional|bool|||
|discovery.deployment.customEnv[].valueFrom.secretKeyRef.name|string|||
|discovery.deployment.customEnv[].valueFrom.secretKeyRef.key|string|||
|discovery.deployment.customEnv[].valueFrom.secretKeyRef.optional|bool|||
|discovery.deployment.restartPolicy|string||restart policy to use when the pod exits|
|discovery.deployment.priorityClassName|string||name of a defined priority class|
|discovery.deployment.nodeName|string||name of node to run on|
|discovery.deployment.nodeSelector.NAME|string||label selector for nodes|
|discovery.deployment.tolerations[].key|string|||
|discovery.deployment.tolerations[].operator|string|||
|discovery.deployment.tolerations[].value|string|||
|discovery.deployment.tolerations[].effect|string|||
|discovery.deployment.tolerations[].tolerationSeconds|int64|||
|discovery.deployment.affinity.NAME|interface|||
|discovery.deployment.hostAliases[]|interface|||
|discovery.deployment.initContainers[]|interface||[InitContainers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of initContainers on the deployment.|
|discovery.deployment.resources.limits.memory|string||amount of memory|
|discovery.deployment.resources.limits.cpu|string||amount of CPUs|
|discovery.deployment.resources.requests.memory|string||amount of memory|
|discovery.deployment.resources.requests.cpu|string||amount of CPUs|
|discovery.deployment.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|discovery.fdsMode|string|WHITELIST|mode for function discovery (blacklist or whitelist). See more info in the settings docs|
|discovery.udsOptions.enabled|bool||Enable upstream discovery service. Defaults to true.|
|discovery.udsOptions.watchLabels.NAME|string||Map of labels to watch. Only services which match all of the selectors specified here will be discovered by UDS.|
|discovery.fdsOptions.graphqlEnabled|bool||Enable GraphQL schema generation on the function discovery service. Defaults to true.|
|discovery.enabled|bool|true|enable Discovery features|
|discovery.serviceAccount.extraAnnotations.NAME|string||extra annotations to add to the service account|
|discovery.serviceAccount.disableAutomount|bool||disable automounting the service account to the gateway proxy. not mounting the token hardens the proxy container, but may interfere with service mesh integrations|
|discovery.serviceAccount.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|discovery.logLevel|string||Level at which the pod should log. Options include "info", "debug", "warn", "error", "panic" and "fatal". Default level is info.|
|gateway.enabled|bool|true|enable Gloo Edge API Gateway features|
|gateway.validation.enabled|bool|true|enable Gloo Edge API Gateway validation hook (default true)|
|gateway.validation.alwaysAcceptResources|bool|true|unless this is set this to false in order to ensure validation webhook rejects invalid resources. by default, validation webhook will only log and report metrics for invalid resource admission without rejecting them outright.|
|gateway.validation.allowWarnings|bool|true|set this to false in order to ensure validation webhook rejects resources that would have warning status or rejected status, rather than just rejected.|
|gateway.validation.warnMissingTlsSecret|bool|true|set this to false in order to treat missing tls secret references as errors, causing validation to fail.|
|gateway.validation.serverEnabled|bool|true|By providing the validation field (parent of this object) the user is implicitly opting into validation. This field allows the user to opt out of the validation server, while still configuring pre-existing fields such as warn_route_short_circuiting and disable_transformation_validation.|
|gateway.validation.disableTransformationValidation|bool|false|set this to true to disable transformation validation. This may bring significant performance benefits if using many transformations, at the cost of possibly incorrect transformations being sent to Envoy. When using this value make sure to pre-validate transformations.|
|gateway.validation.warnRouteShortCircuiting|bool|false|Write a warning to route resources if validation produced a route ordering warning (defaults to false). By setting to true, this means that Gloo Edge will start assigning warnings to resources that would result in route short-circuiting within a virtual host.|
|gateway.validation.secretName|string|gateway-validation-certs|Name of the Kubernetes Secret containing TLS certificates used by the validation webhook server. This secret will be created by the certGen Job if the certGen Job is enabled.|
|gateway.validation.failurePolicy|string|Ignore|failurePolicy defines how unrecognized errors from the Gateway validation endpoint are handled - allowed values are 'Ignore' or 'Fail'. Defaults to Ignore |
|gateway.validation.webhook.enabled|bool|true|enable validation webhook (default true)|
|gateway.validation.webhook.disableHelmHook|bool|false|do not create the webhook as helm hook (default false)|
|gateway.validation.webhook.timeoutSeconds|int||the timeout for the webhook, defaults to 10|
|gateway.validation.webhook.extraAnnotations.NAME|string||extra annotations to add to the webhook|
|gateway.validation.webhook.skipDeleteValidationResources[]|string||resource types in this list will not use webhook valdaition for DELETEs. Use '*' to skip validation for all resources. Valid values are 'virtualservices', 'routetables','upstreams', 'secrets', 'ratelimitconfigs', and '*'. Invalid values will be accepted but will not be used.|
|gateway.validation.webhook.enablePolicyApi|bool|true|enable validation of Policy Api resources (RouteOptions, VirtualHostOptions) (default: true). NOTE: This only applies if the Kubernetes Gateway Integration is also enabled (kubeGateway.enabled).|
|gateway.validation.webhook.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gateway.validation.validationServerGrpcMaxSizeBytes|int|104857600|gRPC max message size in bytes for the gloo validation server|
|gateway.validation.livenessProbeEnabled|bool||Set to true to enable a liveness probe for the gateway (default is false). You must also set the 'Probes' value to true.|
|gateway.validation.fullEnvoyValidation|bool|false|enable feature which validates all final translated config against envoy Validate mode|
|gateway.certGenJob.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|gateway.certGenJob.image.repository|string|certgen|The image repository (name) for the container.|
|gateway.certGenJob.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|gateway.certGenJob.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|gateway.certGenJob.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|gateway.certGenJob.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|gateway.certGenJob.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|gateway.certGenJob.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|gateway.certGenJob.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|gateway.certGenJob.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|gateway.certGenJob.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|gateway.certGenJob.restartPolicy|string|OnFailure|restart policy to use when the pod exits|
|gateway.certGenJob.priorityClassName|string||name of a defined priority class|
|gateway.certGenJob.nodeName|string||name of node to run on|
|gateway.certGenJob.nodeSelector.NAME|string||label selector for nodes|
|gateway.certGenJob.tolerations[].key|string|||
|gateway.certGenJob.tolerations[].operator|string|||
|gateway.certGenJob.tolerations[].value|string|||
|gateway.certGenJob.tolerations[].effect|string|||
|gateway.certGenJob.tolerations[].tolerationSeconds|int64|||
|gateway.certGenJob.affinity.NAME|interface|||
|gateway.certGenJob.hostAliases[]|interface|||
|gateway.certGenJob.initContainers[]|interface||[InitContainers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of initContainers on the deployment.|
|gateway.certGenJob.activeDeadlineSeconds|int||Deadline in seconds for Kubernetes jobs.|
|gateway.certGenJob.backoffLimit|int||Specifies the number of retries before marking this job failed. In kubernetes, defaults to 6|
|gateway.certGenJob.completions|int||Specifies the desired number of successfully finished pods the job should be run with.|
|gateway.certGenJob.manualSelector|bool||Controls generation of pod labels and pod selectors.|
|gateway.certGenJob.parallelism|int||Specifies the maximum desired number of pods the job should run at any given time.|
|gateway.certGenJob.ttlSecondsAfterFinished|int|60|Clean up the finished job after this many seconds. Defaults to 300 for the rollout jobs and 60 for the rest.|
|gateway.certGenJob.extraPodLabels.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.labels data of the job.|
|gateway.certGenJob.extraPodAnnotations.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.annotations data of the job.|
|gateway.certGenJob.containerSecurityContext.capabilities.add[]|string|||
|gateway.certGenJob.containerSecurityContext.capabilities.drop[]|string|||
|gateway.certGenJob.containerSecurityContext.privileged|bool|||
|gateway.certGenJob.containerSecurityContext.seLinuxOptions.user|string|||
|gateway.certGenJob.containerSecurityContext.seLinuxOptions.role|string|||
|gateway.certGenJob.containerSecurityContext.seLinuxOptions.type|string|||
|gateway.certGenJob.containerSecurityContext.seLinuxOptions.level|string|||
|gateway.certGenJob.containerSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|gateway.certGenJob.containerSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|gateway.certGenJob.containerSecurityContext.windowsOptions.runAsUserName|string|||
|gateway.certGenJob.containerSecurityContext.windowsOptions.hostProcess|bool|||
|gateway.certGenJob.containerSecurityContext.runAsUser|int64|||
|gateway.certGenJob.containerSecurityContext.runAsGroup|int64|||
|gateway.certGenJob.containerSecurityContext.runAsNonRoot|bool|||
|gateway.certGenJob.containerSecurityContext.readOnlyRootFilesystem|bool|||
|gateway.certGenJob.containerSecurityContext.allowPrivilegeEscalation|bool|||
|gateway.certGenJob.containerSecurityContext.procMount|string|||
|gateway.certGenJob.containerSecurityContext.seccompProfile.type|string|||
|gateway.certGenJob.containerSecurityContext.seccompProfile.localhostProfile|string|||
|gateway.certGenJob.containerSecurityContext.appArmorProfile.type|string|||
|gateway.certGenJob.containerSecurityContext.appArmorProfile.localhostProfile|string|||
|gateway.certGenJob.containerSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|gateway.certGenJob.kubeResourceOverride.NAME|interface||override fields in the gateway-certgen job.|
|gateway.certGenJob.mtlsKubeResourceOverride.NAME|interface||override fields in the gloo-mtls-certgen job.|
|gateway.certGenJob.enabled|bool|true|enable the job that generates the certificates for the validating webhook at install time (default true)|
|gateway.certGenJob.setTtlAfterFinished|bool|true|Set ttlSecondsAfterFinished on the job. Defaults to true|
|gateway.certGenJob.floatingUserId|bool||If true, allows the cluster to dynamically assign a user ID for the processes running in the container.|
|gateway.certGenJob.forceRotation|bool|true|If true, will create new certs even if the old one are still valid.|
|gateway.certGenJob.rotationDuration|string|65s|Time duration string indicating the (environment-specific) expected time for all pods to pick up a secret update via SDS. This is only applicable to the mTLS certgen job and cron job. If this duration is too short, secret changes may not have time to propagate to all pods, and some requests may be dropped during cert rotation. Since we do 2 secret updates during a cert rotation, the certgen job is expected to run for at least twice this amount of time. If activeDeadlineSeconds is set on the job, make sure it is at least twice as long as the rotation duration, otherwise the certgen job might time out.|
|gateway.certGenJob.runAsUser|float64||Explicitly set the user ID for the processes in the container to run as. Default is 10101.|
|gateway.certGenJob.resources.limits.memory|string||amount of memory|
|gateway.certGenJob.resources.limits.cpu|string||amount of CPUs|
|gateway.certGenJob.resources.requests.memory|string||amount of memory|
|gateway.certGenJob.resources.requests.cpu|string||amount of CPUs|
|gateway.certGenJob.runOnUpdate|bool|false|enable to run the job also on pre-upgrade|
|gateway.certGenJob.cron.enabled|bool|false|enable the cronjob|
|gateway.certGenJob.cron.schedule|string|* * * * *|Cron job scheduling|
|gateway.certGenJob.cron.mtlsKubeResourceOverride.NAME|interface||override fields in the gloo-mtls-certgen cronjob.|
|gateway.certGenJob.cron.validationWebhookKubeResourceOverride.NAME|interface||override fields in the gateway-certgen cronjob.|
|gateway.rolloutJob.restartPolicy|string|OnFailure|restart policy to use when the pod exits|
|gateway.rolloutJob.priorityClassName|string||name of a defined priority class|
|gateway.rolloutJob.nodeName|string||name of node to run on|
|gateway.rolloutJob.nodeSelector.NAME|string||label selector for nodes|
|gateway.rolloutJob.tolerations[].key|string|||
|gateway.rolloutJob.tolerations[].operator|string|||
|gateway.rolloutJob.tolerations[].value|string|||
|gateway.rolloutJob.tolerations[].effect|string|||
|gateway.rolloutJob.tolerations[].tolerationSeconds|int64|||
|gateway.rolloutJob.affinity.NAME|interface|||
|gateway.rolloutJob.hostAliases[]|interface|||
|gateway.rolloutJob.initContainers[]|interface||[InitContainers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of initContainers on the deployment.|
|gateway.rolloutJob.activeDeadlineSeconds|int||Deadline in seconds for Kubernetes jobs.|
|gateway.rolloutJob.backoffLimit|int||Specifies the number of retries before marking this job failed. In kubernetes, defaults to 6|
|gateway.rolloutJob.completions|int||Specifies the desired number of successfully finished pods the job should be run with.|
|gateway.rolloutJob.manualSelector|bool||Controls generation of pod labels and pod selectors.|
|gateway.rolloutJob.parallelism|int||Specifies the maximum desired number of pods the job should run at any given time.|
|gateway.rolloutJob.ttlSecondsAfterFinished|int|300|Clean up the finished job after this many seconds. Defaults to 300 for the rollout jobs and 60 for the rest.|
|gateway.rolloutJob.extraPodLabels.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.labels data of the job.|
|gateway.rolloutJob.extraPodAnnotations.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.annotations data of the job.|
|gateway.rolloutJob.containerSecurityContext.capabilities.add[]|string|||
|gateway.rolloutJob.containerSecurityContext.capabilities.drop[]|string|||
|gateway.rolloutJob.containerSecurityContext.privileged|bool|||
|gateway.rolloutJob.containerSecurityContext.seLinuxOptions.user|string|||
|gateway.rolloutJob.containerSecurityContext.seLinuxOptions.role|string|||
|gateway.rolloutJob.containerSecurityContext.seLinuxOptions.type|string|||
|gateway.rolloutJob.containerSecurityContext.seLinuxOptions.level|string|||
|gateway.rolloutJob.containerSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|gateway.rolloutJob.containerSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|gateway.rolloutJob.containerSecurityContext.windowsOptions.runAsUserName|string|||
|gateway.rolloutJob.containerSecurityContext.windowsOptions.hostProcess|bool|||
|gateway.rolloutJob.containerSecurityContext.runAsUser|int64|||
|gateway.rolloutJob.containerSecurityContext.runAsGroup|int64|||
|gateway.rolloutJob.containerSecurityContext.runAsNonRoot|bool|||
|gateway.rolloutJob.containerSecurityContext.readOnlyRootFilesystem|bool|||
|gateway.rolloutJob.containerSecurityContext.allowPrivilegeEscalation|bool|||
|gateway.rolloutJob.containerSecurityContext.procMount|string|||
|gateway.rolloutJob.containerSecurityContext.seccompProfile.type|string|||
|gateway.rolloutJob.containerSecurityContext.seccompProfile.localhostProfile|string|||
|gateway.rolloutJob.containerSecurityContext.appArmorProfile.type|string|||
|gateway.rolloutJob.containerSecurityContext.appArmorProfile.localhostProfile|string|||
|gateway.rolloutJob.containerSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|gateway.rolloutJob.enabled|bool|true|Enable the job that applies default Gloo Edge custom resources at install and upgrade time (default true).|
|gateway.rolloutJob.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|gateway.rolloutJob.image.repository|string|kubectl|The image repository (name) for the container.|
|gateway.rolloutJob.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|gateway.rolloutJob.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|gateway.rolloutJob.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|gateway.rolloutJob.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|gateway.rolloutJob.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|gateway.rolloutJob.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|gateway.rolloutJob.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|gateway.rolloutJob.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|gateway.rolloutJob.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|gateway.rolloutJob.resources.limits.memory|string||amount of memory|
|gateway.rolloutJob.resources.limits.cpu|string||amount of CPUs|
|gateway.rolloutJob.resources.requests.memory|string||amount of memory|
|gateway.rolloutJob.resources.requests.cpu|string||amount of CPUs|
|gateway.rolloutJob.floatingUserId|bool||If true, allows the cluster to dynamically assign a user ID for the processes running in the container.|
|gateway.rolloutJob.runAsUser|float64||Explicitly set the user ID for the processes in the container to run as. Default is 10101.|
|gateway.rolloutJob.timeout|int|120|Time to wait in seconds until the job has completed. If it exceeds this limit, it is deemed to have failed. Defaults to 120|
|gateway.cleanupJob.restartPolicy|string|OnFailure|restart policy to use when the pod exits|
|gateway.cleanupJob.priorityClassName|string||name of a defined priority class|
|gateway.cleanupJob.nodeName|string||name of node to run on|
|gateway.cleanupJob.nodeSelector.NAME|string||label selector for nodes|
|gateway.cleanupJob.tolerations[].key|string|||
|gateway.cleanupJob.tolerations[].operator|string|||
|gateway.cleanupJob.tolerations[].value|string|||
|gateway.cleanupJob.tolerations[].effect|string|||
|gateway.cleanupJob.tolerations[].tolerationSeconds|int64|||
|gateway.cleanupJob.affinity.NAME|interface|||
|gateway.cleanupJob.hostAliases[]|interface|||
|gateway.cleanupJob.initContainers[]|interface||[InitContainers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of initContainers on the deployment.|
|gateway.cleanupJob.activeDeadlineSeconds|int||Deadline in seconds for Kubernetes jobs.|
|gateway.cleanupJob.backoffLimit|int||Specifies the number of retries before marking this job failed. In kubernetes, defaults to 6|
|gateway.cleanupJob.completions|int||Specifies the desired number of successfully finished pods the job should be run with.|
|gateway.cleanupJob.manualSelector|bool||Controls generation of pod labels and pod selectors.|
|gateway.cleanupJob.parallelism|int||Specifies the maximum desired number of pods the job should run at any given time.|
|gateway.cleanupJob.ttlSecondsAfterFinished|int|60|Clean up the finished job after this many seconds. Defaults to 300 for the rollout jobs and 60 for the rest.|
|gateway.cleanupJob.extraPodLabels.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.labels data of the job.|
|gateway.cleanupJob.extraPodAnnotations.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.annotations data of the job.|
|gateway.cleanupJob.containerSecurityContext.capabilities.add[]|string|||
|gateway.cleanupJob.containerSecurityContext.capabilities.drop[]|string|||
|gateway.cleanupJob.containerSecurityContext.privileged|bool|||
|gateway.cleanupJob.containerSecurityContext.seLinuxOptions.user|string|||
|gateway.cleanupJob.containerSecurityContext.seLinuxOptions.role|string|||
|gateway.cleanupJob.containerSecurityContext.seLinuxOptions.type|string|||
|gateway.cleanupJob.containerSecurityContext.seLinuxOptions.level|string|||
|gateway.cleanupJob.containerSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|gateway.cleanupJob.containerSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|gateway.cleanupJob.containerSecurityContext.windowsOptions.runAsUserName|string|||
|gateway.cleanupJob.containerSecurityContext.windowsOptions.hostProcess|bool|||
|gateway.cleanupJob.containerSecurityContext.runAsUser|int64|||
|gateway.cleanupJob.containerSecurityContext.runAsGroup|int64|||
|gateway.cleanupJob.containerSecurityContext.runAsNonRoot|bool|||
|gateway.cleanupJob.containerSecurityContext.readOnlyRootFilesystem|bool|||
|gateway.cleanupJob.containerSecurityContext.allowPrivilegeEscalation|bool|||
|gateway.cleanupJob.containerSecurityContext.procMount|string|||
|gateway.cleanupJob.containerSecurityContext.seccompProfile.type|string|||
|gateway.cleanupJob.containerSecurityContext.seccompProfile.localhostProfile|string|||
|gateway.cleanupJob.containerSecurityContext.appArmorProfile.type|string|||
|gateway.cleanupJob.containerSecurityContext.appArmorProfile.localhostProfile|string|||
|gateway.cleanupJob.containerSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|gateway.cleanupJob.enabled|bool|true|Enable the job that removes Gloo Edge custom resources when Gloo Edge is uninstalled (default true).|
|gateway.cleanupJob.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|gateway.cleanupJob.image.repository|string|kubectl|The image repository (name) for the container.|
|gateway.cleanupJob.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|gateway.cleanupJob.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|gateway.cleanupJob.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|gateway.cleanupJob.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|gateway.cleanupJob.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|gateway.cleanupJob.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|gateway.cleanupJob.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|gateway.cleanupJob.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|gateway.cleanupJob.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|gateway.cleanupJob.resources.limits.memory|string||amount of memory|
|gateway.cleanupJob.resources.limits.cpu|string||amount of CPUs|
|gateway.cleanupJob.resources.requests.memory|string||amount of memory|
|gateway.cleanupJob.resources.requests.cpu|string||amount of CPUs|
|gateway.cleanupJob.floatingUserId|bool||If true, allows the cluster to dynamically assign a user ID for the processes running in the container.|
|gateway.cleanupJob.runAsUser|float64||Explicitly set the user ID for the processes in the container to run as. Default is 10101.|
|gateway.updateValues|bool||if true, will use a provided helm helper 'gloo.updatevalues' to update values during template render - useful for plugins/extensions|
|gateway.proxyServiceAccount.extraAnnotations.NAME|string||extra annotations to add to the service account|
|gateway.proxyServiceAccount.disableAutomount|bool||disable automounting the service account to the gateway proxy. not mounting the token hardens the proxy container, but may interfere with service mesh integrations|
|gateway.proxyServiceAccount.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gateway.readGatewaysFromAllNamespaces|bool|false|if true, read Gateway custom resources from all watched namespaces rather than just the namespace of the Gateway controller|
|gateway.isolateVirtualHostsBySslConfig|bool|false|if true, Added support for the envoy.filters.listener.tls_inspector listener_filter when using the gateway.isolateVirtualHostsBySslConfig=true global setting.|
|gateway.compressedProxySpec|bool||if true, enables compression for the Proxy CRD spec|
|gateway.persistProxySpec|bool||Enable writing Proxy CRD to etcd. Disabled by default for performance.|
|gateway.translateEmptyGateways|bool|false|If true, the gateways will be translated into Envoy listeners even if no VirtualServices exist.|
|gateway.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.NAME.kind.deployment.replicas|int||number of instances to deploy|
|gatewayProxies.NAME.kind.deployment.customEnv[].name|string|||
|gatewayProxies.NAME.kind.deployment.customEnv[].value|string|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.fieldRef.apiVersion|string|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.fieldRef.fieldPath|string|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.resourceFieldRef.containerName|string|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.resourceFieldRef.resource|string|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|int64|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|int32|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|bool|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|uint|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|int32|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.configMapKeyRef.name|string|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.configMapKeyRef.key|string|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.configMapKeyRef.optional|bool|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.secretKeyRef.name|string|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.secretKeyRef.key|string|||
|gatewayProxies.NAME.kind.deployment.customEnv[].valueFrom.secretKeyRef.optional|bool|||
|gatewayProxies.NAME.kind.deployment.restartPolicy|string||restart policy to use when the pod exits|
|gatewayProxies.NAME.kind.deployment.priorityClassName|string||name of a defined priority class|
|gatewayProxies.NAME.kind.deployment.nodeName|string||name of node to run on|
|gatewayProxies.NAME.kind.deployment.nodeSelector.NAME|string||label selector for nodes|
|gatewayProxies.NAME.kind.deployment.tolerations[].key|string|||
|gatewayProxies.NAME.kind.deployment.tolerations[].operator|string|||
|gatewayProxies.NAME.kind.deployment.tolerations[].value|string|||
|gatewayProxies.NAME.kind.deployment.tolerations[].effect|string|||
|gatewayProxies.NAME.kind.deployment.tolerations[].tolerationSeconds|int64|||
|gatewayProxies.NAME.kind.deployment.affinity.NAME|interface|||
|gatewayProxies.NAME.kind.deployment.hostAliases[]|interface|||
|gatewayProxies.NAME.kind.deployment.initContainers[]|interface||[InitContainers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of initContainers on the deployment.|
|gatewayProxies.NAME.kind.deployment.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.NAME.kind.daemonSet.hostPort|bool||whether or not to enable host networking on the pod. Only relevant when running as a DaemonSet|
|gatewayProxies.NAME.kind.daemonSet.hostNetwork|bool|||
|gatewayProxies.NAME.namespace|string||Namespace in which to deploy this gateway proxy. Defaults to the value of Settings.WriteNamespace|
|gatewayProxies.NAME.podTemplate.httpPort|int||HTTP port for the gateway service target port.|
|gatewayProxies.NAME.podTemplate.httpsPort|int||HTTPS port for the gateway service target port.|
|gatewayProxies.NAME.podTemplate.extraPorts[]|interface||extra ports for the gateway pod.|
|gatewayProxies.NAME.podTemplate.extraAnnotations.NAME|string||extra annotations to add to the pod.|
|gatewayProxies.NAME.podTemplate.nodeName|string||name of node to run on.|
|gatewayProxies.NAME.podTemplate.nodeSelector.NAME|string||label selector for nodes.|
|gatewayProxies.NAME.podTemplate.tolerations[].key|string|||
|gatewayProxies.NAME.podTemplate.tolerations[].operator|string|||
|gatewayProxies.NAME.podTemplate.tolerations[].value|string|||
|gatewayProxies.NAME.podTemplate.tolerations[].effect|string|||
|gatewayProxies.NAME.podTemplate.tolerations[].tolerationSeconds|int64|||
|gatewayProxies.NAME.podTemplate.probes|bool||Set to true to enable a readiness probe (default is false). Then, you can also enable a liveness probe.|
|gatewayProxies.NAME.podTemplate.livenessProbeEnabled|bool||Set to true to enable a liveness probe (default is false).|
|gatewayProxies.NAME.podTemplate.resources.limits.memory|string||amount of memory|
|gatewayProxies.NAME.podTemplate.resources.limits.cpu|string||amount of CPUs|
|gatewayProxies.NAME.podTemplate.resources.requests.memory|string||amount of memory|
|gatewayProxies.NAME.podTemplate.resources.requests.cpu|string||amount of CPUs|
|gatewayProxies.NAME.podTemplate.disableNetBind|bool||don't add the NET_BIND_SERVICE capability to the pod. This means that the gateway proxy will not be able to bind to ports below 1024. If podSecurityContext is defined, this value is not applied.|
|gatewayProxies.NAME.podTemplate.runUnprivileged|bool||run Envoy as an unprivileged user. If a SecurityContext is defined for the pod or container, this value is not applied for the pod/container.|
|gatewayProxies.NAME.podTemplate.floatingUserId|bool||If true, allows the cluster to dynamically assign a user ID for the processes running in the container. If podSecurityContext is defined, this value is not applied.|
|gatewayProxies.NAME.podTemplate.runAsUser|float64||Explicitly set the user ID for the processes in the container to run as. Default is 10101. If a SecurityContext is defined for the pod or container, this value is not applied for the pod/container.|
|gatewayProxies.NAME.podTemplate.fsGroup|float64||Explicitly set the group ID for volume ownership. Default is 10101. If podSecurityContext is defined, this value is not applied.|
|gatewayProxies.NAME.podTemplate.gracefulShutdown.enabled|bool||Enable grace period before shutdown to finish current requests while Envoy health checks fail to e.g. notify external load balancers. *NOTE:* This will not have any effect if you have not defined health checks via the health check filter|
|gatewayProxies.NAME.podTemplate.gracefulShutdown.sleepTimeSeconds|int||Time (in seconds) for the preStop hook to wait before allowing Envoy to terminate|
|gatewayProxies.NAME.podTemplate.terminationGracePeriodSeconds|int||Time in seconds to wait for the pod to terminate gracefully. See [kubernetes docs](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#istio-lifecycle) for more info.|
|gatewayProxies.NAME.podTemplate.customReadinessProbe.exec.command[]|string|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.httpGet.path|string|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.httpGet.port|int64|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.httpGet.port|int32|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.httpGet.port|string|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.httpGet.host|string|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.httpGet.scheme|string|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.httpGet.httpHeaders[].name|string|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.httpGet.httpHeaders[].value|string|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.tcpSocket.port|int64|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.tcpSocket.port|int32|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.tcpSocket.port|string|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.tcpSocket.host|string|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.grpc.port|int32|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.grpc.service|string|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.initialDelaySeconds|int32|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.timeoutSeconds|int32|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.periodSeconds|int32|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.successThreshold|int32|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.failureThreshold|int32|||
|gatewayProxies.NAME.podTemplate.customReadinessProbe.terminationGracePeriodSeconds|int64|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.exec.command[]|string|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.httpGet.path|string|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.httpGet.port|int64|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.httpGet.port|int32|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.httpGet.port|string|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.httpGet.host|string|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.httpGet.scheme|string|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.httpGet.httpHeaders[].name|string|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.httpGet.httpHeaders[].value|string|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.tcpSocket.port|int64|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.tcpSocket.port|int32|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.tcpSocket.port|string|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.tcpSocket.host|string|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.grpc.port|int32|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.grpc.service|string|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.initialDelaySeconds|int32|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.timeoutSeconds|int32|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.periodSeconds|int32|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.successThreshold|int32|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.failureThreshold|int32|||
|gatewayProxies.NAME.podTemplate.customLivenessProbe.terminationGracePeriodSeconds|int64|||
|gatewayProxies.NAME.podTemplate.extraGatewayProxyLabels.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.labels data of the gloo edge gateway-proxy deployment.|
|gatewayProxies.NAME.podTemplate.extraContainers[]|interface||Extra [containers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of containers on the gateway proxy deployment.|
|gatewayProxies.NAME.podTemplate.extraInitContainers[]|interface||Extra [initContainers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of initContainers on the gateway proxy deployment.|
|gatewayProxies.NAME.podTemplate.enablePodSecurityContext|bool||Whether or not to render the pod security context. Default is true.|
|gatewayProxies.NAME.podTemplate.podSecurityContext.seLinuxOptions.user|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.seLinuxOptions.role|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.seLinuxOptions.type|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.seLinuxOptions.level|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.windowsOptions.runAsUserName|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.windowsOptions.hostProcess|bool|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.runAsUser|int64|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.runAsGroup|int64|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.runAsNonRoot|bool|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.supplementalGroups[]|int64|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.supplementalGroupsPolicy|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.fsGroup|int64|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.sysctls[].name|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.sysctls[].value|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.fsGroupChangePolicy|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.seccompProfile.type|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.seccompProfile.localhostProfile|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.appArmorProfile.type|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.appArmorProfile.localhostProfile|string|||
|gatewayProxies.NAME.podTemplate.podSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|gatewayProxies.NAME.podTemplate.image.tag|string||The image tag for the container.|
|gatewayProxies.NAME.podTemplate.image.repository|string||The image repository (name) for the container.|
|gatewayProxies.NAME.podTemplate.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|gatewayProxies.NAME.podTemplate.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|gatewayProxies.NAME.podTemplate.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|gatewayProxies.NAME.podTemplate.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|gatewayProxies.NAME.podTemplate.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|gatewayProxies.NAME.podTemplate.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|gatewayProxies.NAME.podTemplate.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|gatewayProxies.NAME.podTemplate.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|gatewayProxies.NAME.podTemplate.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.capabilities.add[]|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.capabilities.drop[]|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.privileged|bool|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.seLinuxOptions.user|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.seLinuxOptions.role|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.seLinuxOptions.type|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.seLinuxOptions.level|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.windowsOptions.runAsUserName|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.windowsOptions.hostProcess|bool|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.runAsUser|int64|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.runAsGroup|int64|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.runAsNonRoot|bool|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.readOnlyRootFilesystem|bool|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.allowPrivilegeEscalation|bool|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.procMount|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.seccompProfile.type|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.seccompProfile.localhostProfile|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.appArmorProfile.type|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.appArmorProfile.localhostProfile|string|||
|gatewayProxies.NAME.podTemplate.glooContainerSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|gatewayProxies.NAME.configMap.data.NAME|string|||
|gatewayProxies.NAME.configMap.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.NAME.customStaticLayer|interface||Configure the static layer for global overrides to Envoy behavior, as defined in the Envoy bootstrap YAML. You cannot use this setting to set overload or upstream layers. For more info, see the Envoy docs. https://www.envoyproxy.io/docs/envoy/latest/configuration/operations/runtime#config-runtime|
|gatewayProxies.NAME.globalDownstreamMaxConnections|uint32||the number of concurrent connections needed. limit used to protect against exhausting file descriptors on host machine|
|gatewayProxies.NAME.healthyPanicThreshold|int8||the percentage of healthy hosts required to load balance based on health status of hosts|
|gatewayProxies.NAME.service.type|string||gateway [service type](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types). default is `LoadBalancer`|
|gatewayProxies.NAME.service.httpPort|int||HTTP port for the gateway service|
|gatewayProxies.NAME.service.httpsPort|int||HTTPS port for the gateway service|
|gatewayProxies.NAME.service.httpNodePort|int||HTTP nodeport for the gateway service if using type NodePort|
|gatewayProxies.NAME.service.httpsNodePort|int||HTTPS nodeport for the gateway service if using type NodePort|
|gatewayProxies.NAME.service.clusterIP|string||static clusterIP (or `None`) when `gatewayProxies[].gatewayProxy.service.type` is `ClusterIP`|
|gatewayProxies.NAME.service.extraAnnotations.NAME|string|||
|gatewayProxies.NAME.service.externalTrafficPolicy|string|||
|gatewayProxies.NAME.service.name|string||Custom name override for the service resource of the proxy|
|gatewayProxies.NAME.service.httpsFirst|bool||List HTTPS port before HTTP|
|gatewayProxies.NAME.service.loadBalancerIP|string||IP address of the load balancer|
|gatewayProxies.NAME.service.loadBalancerSourceRanges[]|string||List of IP CIDR ranges that are allowed to access the load balancer|
|gatewayProxies.NAME.service.customPorts[]|interface||List of custom port to expose in the Envoy proxy. Each element follows conventional port syntax (port, targetPort, protocol, name)|
|gatewayProxies.NAME.service.externalIPs[]|string||externalIPs is a list of IP addresses for which nodes in the cluster will also accept traffic for this service|
|gatewayProxies.NAME.service.configDumpService.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.NAME.service.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.NAME.antiAffinity|bool||configure anti affinity such that pods are preferably not co-located|
|gatewayProxies.NAME.affinity.NAME|interface|||
|gatewayProxies.NAME.topologySpreadConstraints[]|interface||configure topologySpreadConstraints for gateway proxy pods|
|gatewayProxies.NAME.tracing.provider.NAME|interface|||
|gatewayProxies.NAME.tracing.cluster[].NAME|interface|||
|gatewayProxies.NAME.gatewaySettings.enabled|bool||enable/disable default gateways|
|gatewayProxies.NAME.gatewaySettings.disableGeneratedGateways|bool||set to true to disable the gateway generation for a gateway proxy|
|gatewayProxies.NAME.gatewaySettings.disableHttpGateway|bool||Set to true to disable http gateway generation.|
|gatewayProxies.NAME.gatewaySettings.disableHttpsGateway|bool||Set to true to disable https gateway generation.|
|gatewayProxies.NAME.gatewaySettings.ipv4Only|bool||set to true if your network allows ipv4 addresses only. Sets the Gateway spec's bindAddress to 0.0.0.0 instead of ::|
|gatewayProxies.NAME.gatewaySettings.useProxyProto|bool||use proxy protocol|
|gatewayProxies.NAME.gatewaySettings.httpHybridGateway.NAME|interface||custom yaml to use for hybrid gateway settings for the http gateway|
|gatewayProxies.NAME.gatewaySettings.httpsHybridGateway.NAME|interface||custom yaml to use for hybrid gateway settings for the https gateway|
|gatewayProxies.NAME.gatewaySettings.customHttpGateway.NAME|interface||custom yaml to use for http gateway settings|
|gatewayProxies.NAME.gatewaySettings.customHttpsGateway.NAME|interface||custom yaml to use for https gateway settings|
|gatewayProxies.NAME.gatewaySettings.accessLoggingService.NAME|interface||custom yaml to use for access logging service (https://docs.solo.io/gloo-edge/latest/reference/api/github.com/solo-io/gloo/projects/gloo/api/v1/options/als/als.proto.sk/)|
|gatewayProxies.NAME.gatewaySettings.options.NAME|interface||custom options for http(s) gateways (https://docs.solo.io/gloo-edge/latest/reference/api/github.com/solo-io/gloo/projects/gloo/api/v1/options.proto.sk/#listeneroptions)|
|gatewayProxies.NAME.gatewaySettings.httpGatewayKubeOverride.NAME|interface|||
|gatewayProxies.NAME.gatewaySettings.httpsGatewayKubeOverride.NAME|interface|||
|gatewayProxies.NAME.gatewaySettings.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.NAME.extraEnvoyArgs[]|string||Envoy container args, (e.g. https://www.envoyproxy.io/docs/envoy/latest/operations/cli)|
|gatewayProxies.NAME.extraContainersHelper|string|||
|gatewayProxies.NAME.extraInitContainersHelper|string|||
|gatewayProxies.NAME.extraVolumes[].NAME|interface|||
|gatewayProxies.NAME.extraVolumeHelper|string|||
|gatewayProxies.NAME.extraListenersHelper|string|||
|gatewayProxies.NAME.stats.enabled|bool||Controls whether or not Envoy stats are enabled|
|gatewayProxies.NAME.stats.routePrefixRewrite|string||The Envoy stats endpoint to which the metrics are written|
|gatewayProxies.NAME.stats.setDatadogAnnotations|bool||Sets the default datadog annotations|
|gatewayProxies.NAME.stats.enableStatsRoute|bool||Enables an additional route to the stats cluster defaulting to /stats|
|gatewayProxies.NAME.stats.statsPrefixRewrite|string||The Envoy stats endpoint with general metrics for the additional stats route|
|gatewayProxies.NAME.stats.serviceMonitorEnabled|bool||Whether or not to expose an http-monitoring port that can be scraped by a Prometheus Service Monitor. Requires that 'enabled' is also true|
|gatewayProxies.NAME.stats.podMonitorEnabled|bool||Whether or not to expose an http-monitoring port that can be scraped by a Prometheus Pod Monitor. Requires that 'enabled' is also true|
|gatewayProxies.NAME.readConfig|bool||expose a read-only subset of the Envoy admin api|
|gatewayProxies.NAME.readConfigMulticluster|bool||expose a read-only subset of the Envoy admin api to gloo-fed|
|gatewayProxies.NAME.extraProxyVolumeMounts[].NAME|interface|||
|gatewayProxies.NAME.extraProxyVolumeMountHelper|string||name of custom made named template allowing for extra volume mounts on the proxy container|
|gatewayProxies.NAME.loopBackAddress|string||Name on which to bind the loop-back interface for this instance of Envoy. Defaults to 127.0.0.1, but other common values may be localhost or ::1|
|gatewayProxies.NAME.failover.enabled|bool||(Enterprise Only): Configure this proxy for failover|
|gatewayProxies.NAME.failover.port|uint||(Enterprise Only): Port to use for failover Gateway Bind port, and service. Default is 15443|
|gatewayProxies.NAME.failover.nodePort|uint||(Enterprise Only): Optional NodePort for failover Service|
|gatewayProxies.NAME.failover.secretName|string||(Enterprise Only): Secret containing downstream Ssl Secrets Default is failover-downstream|
|gatewayProxies.NAME.failover.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.NAME.disabled|bool||Skips creation of this gateway proxy. Used to turn off gateway proxies created by preceding configurations|
|gatewayProxies.NAME.envoyApiVersion|string||Version of the Envoy API to use for the xDS transport and resources. Default is V3|
|gatewayProxies.NAME.envoyBootstrapExtensions[].NAME|interface||List of bootstrap extensions to add to Envoy bootstrap config. Examples include Wasm Service (https://www.envoyproxy.io/docs/envoy/latest/api-v3/extensions/wasm/v3/wasm.proto#extensions-wasm-v3-wasmservice).|
|gatewayProxies.NAME.envoyOverloadManager.NAME|interface||Overload Manager definition for Envoy bootstrap config. If enabled, a list of Resource Monitors MUST be defined in order to produce a valid Envoy config (https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/overload/v3/overload.proto#overload-manager).|
|gatewayProxies.NAME.envoyStaticClusters[].NAME|interface||List of extra static clusters to be added to Envoy bootstrap config. https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/cluster/v3/cluster.proto#envoy-v3-api-msg-config-cluster-v3-cluster|
|gatewayProxies.NAME.horizontalPodAutoscaler.apiVersion|string||accepts autoscaling/v1, autoscaling/v2beta2 or autoscaling/v2. Note: autoscaling/v2beta2 is deprecated as of Kubernetes 1.26.|
|gatewayProxies.NAME.horizontalPodAutoscaler.minReplicas|int32||minReplicas is the lower limit for the number of replicas to which the autoscaler can scale down.|
|gatewayProxies.NAME.horizontalPodAutoscaler.maxReplicas|int32||maxReplicas is the upper limit for the number of replicas to which the autoscaler can scale up. It cannot be less that minReplicas.|
|gatewayProxies.NAME.horizontalPodAutoscaler.targetCPUUtilizationPercentage|int32||target average CPU utilization (represented as a percentage of requested CPU) over all the pods. Used only with apiVersion autoscaling/v1|
|gatewayProxies.NAME.horizontalPodAutoscaler.metrics[].NAME|interface||metrics contains the specifications for which to use to calculate the desired replica count (the maximum replica count across all metrics will be used). Used only with apiVersion autoscaling/v2beta2|
|gatewayProxies.NAME.horizontalPodAutoscaler.behavior.NAME|interface||behavior configures the scaling behavior of the target in both Up and Down directions (scaleUp and scaleDown fields respectively). Used only with apiVersion autoscaling/v2beta2|
|gatewayProxies.NAME.horizontalPodAutoscaler.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.NAME.podDisruptionBudget.minAvailable|string||Corresponds directly with the _minAvailable_ field in the [PodDisruptionBudgetSpec](https://kubernetes.io/docs/reference/kubernetes-api/policy-resources/pod-disruption-budget-v1/#PodDisruptionBudgetSpec). This value is mutually exclusive with _maxUnavailable_.|
|gatewayProxies.NAME.podDisruptionBudget.maxUnavailable|string||Corresponds directly with the _maxUnavailable_ field in the [PodDisruptionBudgetSpec](https://kubernetes.io/docs/reference/kubernetes-api/policy-resources/pod-disruption-budget-v1/#PodDisruptionBudgetSpec). This value is mutually exclusive with _minAvailable_.|
|gatewayProxies.NAME.podDisruptionBudget.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.NAME.istioMetaMeshId|string||ISTIO_META_MESH_ID Environment Variable. Defaults to "cluster.local"|
|gatewayProxies.NAME.istioMetaClusterId|string||ISTIO_META_CLUSTER_ID Environment Variable. Defaults to "Kubernetes"|
|gatewayProxies.NAME.istioDiscoveryAddress|string||discoveryAddress field of the PROXY_CONFIG environment variable. Defaults to "istiod.istio-system.svc:15012"|
|gatewayProxies.NAME.istioSpiffeCertProviderAddress|string||Address of the spiffe certificate provider. Defaults to istioDiscoveryAddress|
|gatewayProxies.NAME.envoyLogLevel|string||Level at which the pod should log. Options include "trace", "info", "debug", "warn", "error", "critical" and "off". Default level is info|
|gatewayProxies.NAME.envoyStatsConfig.NAME|interface||Envoy statistics configuration, such as tagging. For more info, see https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/metrics/v3/stats.proto#config-metrics-v3-statsconfig|
|gatewayProxies.NAME.xdsServiceAddress|string||The k8s service name for the xds server. Defaults to gloo.|
|gatewayProxies.NAME.xdsServicePort|uint32||The k8s service port for the xds server. Defaults to the value from .Values.gloo.deployment.xdsPort, but can be overridden to use, for example, xds-relay.|
|gatewayProxies.NAME.tcpKeepaliveTimeSeconds|uint32||The amount of time in seconds for connections to be idle before sending keep-alive probes. Defaults to 60. See here: https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/core/v3/address.proto#envoy-v3-api-msg-config-core-v3-tcpkeepalive|
|gatewayProxies.NAME.disableCoreDumps|bool||If set to true, Envoy will not generate core dumps in the event of a crash. Defaults to false|
|gatewayProxies.NAME.disableExtauthSidecar|bool||If set to true, this gateway proxy will not come up with an extauth sidecar container when global.extAuth.envoySidecar is enabled. This setting has no effect otherwise. Defaults to false|
|gatewayProxies.NAME.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.gatewayProxy.kind.deployment.replicas|int|1|number of instances to deploy|
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].name|string|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].value|string|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.fieldRef.apiVersion|string|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.fieldRef.fieldPath|string|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.resourceFieldRef.containerName|string|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.resourceFieldRef.resource|string|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|int64|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|int32|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|bool|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|uint|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|int32|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.configMapKeyRef.name|string|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.configMapKeyRef.key|string|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.configMapKeyRef.optional|bool|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.secretKeyRef.name|string|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.secretKeyRef.key|string|||
|gatewayProxies.gatewayProxy.kind.deployment.customEnv[].valueFrom.secretKeyRef.optional|bool|||
|gatewayProxies.gatewayProxy.kind.deployment.restartPolicy|string||restart policy to use when the pod exits|
|gatewayProxies.gatewayProxy.kind.deployment.priorityClassName|string||name of a defined priority class|
|gatewayProxies.gatewayProxy.kind.deployment.nodeName|string||name of node to run on|
|gatewayProxies.gatewayProxy.kind.deployment.nodeSelector.NAME|string||label selector for nodes|
|gatewayProxies.gatewayProxy.kind.deployment.tolerations[].key|string|||
|gatewayProxies.gatewayProxy.kind.deployment.tolerations[].operator|string|||
|gatewayProxies.gatewayProxy.kind.deployment.tolerations[].value|string|||
|gatewayProxies.gatewayProxy.kind.deployment.tolerations[].effect|string|||
|gatewayProxies.gatewayProxy.kind.deployment.tolerations[].tolerationSeconds|int64|||
|gatewayProxies.gatewayProxy.kind.deployment.affinity.NAME|interface|||
|gatewayProxies.gatewayProxy.kind.deployment.hostAliases[]|interface|||
|gatewayProxies.gatewayProxy.kind.deployment.initContainers[]|interface||[InitContainers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of initContainers on the deployment.|
|gatewayProxies.gatewayProxy.kind.deployment.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.gatewayProxy.kind.daemonSet.hostPort|bool||whether or not to enable host networking on the pod. Only relevant when running as a DaemonSet|
|gatewayProxies.gatewayProxy.kind.daemonSet.hostNetwork|bool|||
|gatewayProxies.gatewayProxy.namespace|string||Namespace in which to deploy this gateway proxy. Defaults to the value of Settings.WriteNamespace|
|gatewayProxies.gatewayProxy.podTemplate.httpPort|int|8080|HTTP port for the gateway service target port.|
|gatewayProxies.gatewayProxy.podTemplate.httpsPort|int|8443|HTTPS port for the gateway service target port.|
|gatewayProxies.gatewayProxy.podTemplate.extraPorts[]|interface||extra ports for the gateway pod.|
|gatewayProxies.gatewayProxy.podTemplate.extraAnnotations.NAME|string||extra annotations to add to the pod.|
|gatewayProxies.gatewayProxy.podTemplate.nodeName|string||name of node to run on.|
|gatewayProxies.gatewayProxy.podTemplate.nodeSelector.NAME|string||label selector for nodes.|
|gatewayProxies.gatewayProxy.podTemplate.tolerations[].key|string|||
|gatewayProxies.gatewayProxy.podTemplate.tolerations[].operator|string|||
|gatewayProxies.gatewayProxy.podTemplate.tolerations[].value|string|||
|gatewayProxies.gatewayProxy.podTemplate.tolerations[].effect|string|||
|gatewayProxies.gatewayProxy.podTemplate.tolerations[].tolerationSeconds|int64|||
|gatewayProxies.gatewayProxy.podTemplate.probes|bool|false|Set to true to enable a readiness probe (default is false). Then, you can also enable a liveness probe.|
|gatewayProxies.gatewayProxy.podTemplate.livenessProbeEnabled|bool||Set to true to enable a liveness probe (default is false).|
|gatewayProxies.gatewayProxy.podTemplate.resources.limits.memory|string||amount of memory|
|gatewayProxies.gatewayProxy.podTemplate.resources.limits.cpu|string||amount of CPUs|
|gatewayProxies.gatewayProxy.podTemplate.resources.requests.memory|string||amount of memory|
|gatewayProxies.gatewayProxy.podTemplate.resources.requests.cpu|string||amount of CPUs|
|gatewayProxies.gatewayProxy.podTemplate.disableNetBind|bool|true|don't add the NET_BIND_SERVICE capability to the pod. This means that the gateway proxy will not be able to bind to ports below 1024. If podSecurityContext is defined, this value is not applied.|
|gatewayProxies.gatewayProxy.podTemplate.runUnprivileged|bool|true|run Envoy as an unprivileged user. If a SecurityContext is defined for the pod or container, this value is not applied for the pod/container.|
|gatewayProxies.gatewayProxy.podTemplate.floatingUserId|bool||If true, allows the cluster to dynamically assign a user ID for the processes running in the container. If podSecurityContext is defined, this value is not applied.|
|gatewayProxies.gatewayProxy.podTemplate.runAsUser|float64||Explicitly set the user ID for the processes in the container to run as. Default is 10101. If a SecurityContext is defined for the pod or container, this value is not applied for the pod/container.|
|gatewayProxies.gatewayProxy.podTemplate.fsGroup|float64||Explicitly set the group ID for volume ownership. Default is 10101. If podSecurityContext is defined, this value is not applied.|
|gatewayProxies.gatewayProxy.podTemplate.gracefulShutdown.enabled|bool|false|Enable grace period before shutdown to finish current requests while Envoy health checks fail to e.g. notify external load balancers. *NOTE:* This will not have any effect if you have not defined health checks via the health check filter|
|gatewayProxies.gatewayProxy.podTemplate.gracefulShutdown.sleepTimeSeconds|int|25|Time (in seconds) for the preStop hook to wait before allowing Envoy to terminate|
|gatewayProxies.gatewayProxy.podTemplate.terminationGracePeriodSeconds|int||Time in seconds to wait for the pod to terminate gracefully. See [kubernetes docs](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#istio-lifecycle) for more info.|
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.exec.command[]|string|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.httpGet.path|string|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.httpGet.port|int64|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.httpGet.port|int32|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.httpGet.port|string|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.httpGet.host|string|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.httpGet.scheme|string|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.httpGet.httpHeaders[].name|string|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.httpGet.httpHeaders[].value|string|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.tcpSocket.port|int64|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.tcpSocket.port|int32|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.tcpSocket.port|string|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.tcpSocket.host|string|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.grpc.port|int32|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.grpc.service|string|||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.initialDelaySeconds|int32|0||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.timeoutSeconds|int32|0||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.periodSeconds|int32|0||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.successThreshold|int32|0||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.failureThreshold|int32|0||
|gatewayProxies.gatewayProxy.podTemplate.customReadinessProbe.terminationGracePeriodSeconds|int64|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.exec.command[]|string|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.httpGet.path|string|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.httpGet.port|int64|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.httpGet.port|int32|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.httpGet.port|string|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.httpGet.host|string|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.httpGet.scheme|string|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.httpGet.httpHeaders[].name|string|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.httpGet.httpHeaders[].value|string|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.tcpSocket.port|int64|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.tcpSocket.port|int32|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.tcpSocket.port|string|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.tcpSocket.host|string|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.grpc.port|int32|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.grpc.service|string|||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.initialDelaySeconds|int32|0||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.timeoutSeconds|int32|0||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.periodSeconds|int32|0||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.successThreshold|int32|0||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.failureThreshold|int32|0||
|gatewayProxies.gatewayProxy.podTemplate.customLivenessProbe.terminationGracePeriodSeconds|int64|||
|gatewayProxies.gatewayProxy.podTemplate.extraGatewayProxyLabels.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.labels data of the gloo edge gateway-proxy deployment.|
|gatewayProxies.gatewayProxy.podTemplate.extraContainers[]|interface||Extra [containers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of containers on the gateway proxy deployment.|
|gatewayProxies.gatewayProxy.podTemplate.extraInitContainers[]|interface||Extra [initContainers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of initContainers on the gateway proxy deployment.|
|gatewayProxies.gatewayProxy.podTemplate.enablePodSecurityContext|bool|true|Whether or not to render the pod security context. Default is true.|
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.seLinuxOptions.user|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.seLinuxOptions.role|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.seLinuxOptions.type|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.seLinuxOptions.level|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.windowsOptions.runAsUserName|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.windowsOptions.hostProcess|bool|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.runAsUser|int64|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.runAsGroup|int64|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.runAsNonRoot|bool|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.supplementalGroups[]|int64|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.supplementalGroupsPolicy|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.fsGroup|int64|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.sysctls[].name|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.sysctls[].value|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.fsGroupChangePolicy|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.seccompProfile.type|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.seccompProfile.localhostProfile|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.appArmorProfile.type|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.appArmorProfile.localhostProfile|string|||
|gatewayProxies.gatewayProxy.podTemplate.podSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|gatewayProxies.gatewayProxy.podTemplate.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|gatewayProxies.gatewayProxy.podTemplate.image.repository|string|gloo-envoy-wrapper|The image repository (name) for the container.|
|gatewayProxies.gatewayProxy.podTemplate.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|gatewayProxies.gatewayProxy.podTemplate.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|gatewayProxies.gatewayProxy.podTemplate.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|gatewayProxies.gatewayProxy.podTemplate.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|gatewayProxies.gatewayProxy.podTemplate.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|gatewayProxies.gatewayProxy.podTemplate.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|gatewayProxies.gatewayProxy.podTemplate.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|gatewayProxies.gatewayProxy.podTemplate.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|gatewayProxies.gatewayProxy.podTemplate.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.capabilities.add[]|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.capabilities.drop[]|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.privileged|bool|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.seLinuxOptions.user|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.seLinuxOptions.role|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.seLinuxOptions.type|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.seLinuxOptions.level|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.windowsOptions.runAsUserName|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.windowsOptions.hostProcess|bool|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.runAsUser|int64|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.runAsGroup|int64|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.runAsNonRoot|bool|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.readOnlyRootFilesystem|bool|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.allowPrivilegeEscalation|bool|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.procMount|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.seccompProfile.type|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.seccompProfile.localhostProfile|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.appArmorProfile.type|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.appArmorProfile.localhostProfile|string|||
|gatewayProxies.gatewayProxy.podTemplate.glooContainerSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|gatewayProxies.gatewayProxy.configMap.data.NAME|string|||
|gatewayProxies.gatewayProxy.configMap.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.gatewayProxy.customStaticLayer|interface||Configure the static layer for global overrides to Envoy behavior, as defined in the Envoy bootstrap YAML. You cannot use this setting to set overload or upstream layers. For more info, see the Envoy docs. https://www.envoyproxy.io/docs/envoy/latest/configuration/operations/runtime#config-runtime|
|gatewayProxies.gatewayProxy.globalDownstreamMaxConnections|uint32|250000|the number of concurrent connections needed. limit used to protect against exhausting file descriptors on host machine|
|gatewayProxies.gatewayProxy.healthyPanicThreshold|int8|50|the percentage of healthy hosts required to load balance based on health status of hosts|
|gatewayProxies.gatewayProxy.service.type|string|LoadBalancer|gateway [service type](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types). default is `LoadBalancer`|
|gatewayProxies.gatewayProxy.service.httpPort|int|80|HTTP port for the gateway service|
|gatewayProxies.gatewayProxy.service.httpsPort|int|443|HTTPS port for the gateway service|
|gatewayProxies.gatewayProxy.service.httpNodePort|int||HTTP nodeport for the gateway service if using type NodePort|
|gatewayProxies.gatewayProxy.service.httpsNodePort|int||HTTPS nodeport for the gateway service if using type NodePort|
|gatewayProxies.gatewayProxy.service.clusterIP|string||static clusterIP (or `None`) when `gatewayProxies[].gatewayProxy.service.type` is `ClusterIP`|
|gatewayProxies.gatewayProxy.service.extraAnnotations.NAME|string|||
|gatewayProxies.gatewayProxy.service.externalTrafficPolicy|string|||
|gatewayProxies.gatewayProxy.service.name|string||Custom name override for the service resource of the proxy|
|gatewayProxies.gatewayProxy.service.httpsFirst|bool||List HTTPS port before HTTP|
|gatewayProxies.gatewayProxy.service.loadBalancerIP|string||IP address of the load balancer|
|gatewayProxies.gatewayProxy.service.loadBalancerSourceRanges[]|string||List of IP CIDR ranges that are allowed to access the load balancer|
|gatewayProxies.gatewayProxy.service.customPorts[]|interface||List of custom port to expose in the Envoy proxy. Each element follows conventional port syntax (port, targetPort, protocol, name)|
|gatewayProxies.gatewayProxy.service.externalIPs[]|string||externalIPs is a list of IP addresses for which nodes in the cluster will also accept traffic for this service|
|gatewayProxies.gatewayProxy.service.configDumpService.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.gatewayProxy.service.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.gatewayProxy.antiAffinity|bool||configure anti affinity such that pods are preferably not co-located|
|gatewayProxies.gatewayProxy.affinity.NAME|interface|||
|gatewayProxies.gatewayProxy.topologySpreadConstraints[]|interface||configure topologySpreadConstraints for gateway proxy pods|
|gatewayProxies.gatewayProxy.tracing.provider.NAME|interface|||
|gatewayProxies.gatewayProxy.tracing.cluster[].NAME|interface|||
|gatewayProxies.gatewayProxy.gatewaySettings.enabled|bool|true|enable/disable default gateways|
|gatewayProxies.gatewayProxy.gatewaySettings.disableGeneratedGateways|bool||set to true to disable the gateway generation for a gateway proxy|
|gatewayProxies.gatewayProxy.gatewaySettings.disableHttpGateway|bool||Set to true to disable http gateway generation.|
|gatewayProxies.gatewayProxy.gatewaySettings.disableHttpsGateway|bool||Set to true to disable https gateway generation.|
|gatewayProxies.gatewayProxy.gatewaySettings.ipv4Only|bool||set to true if your network allows ipv4 addresses only. Sets the Gateway spec's bindAddress to 0.0.0.0 instead of ::|
|gatewayProxies.gatewayProxy.gatewaySettings.useProxyProto|bool|false|use proxy protocol|
|gatewayProxies.gatewayProxy.gatewaySettings.httpHybridGateway.NAME|interface||custom yaml to use for hybrid gateway settings for the http gateway|
|gatewayProxies.gatewayProxy.gatewaySettings.httpsHybridGateway.NAME|interface||custom yaml to use for hybrid gateway settings for the https gateway|
|gatewayProxies.gatewayProxy.gatewaySettings.customHttpGateway.NAME|interface||custom yaml to use for http gateway settings|
|gatewayProxies.gatewayProxy.gatewaySettings.customHttpsGateway.NAME|interface||custom yaml to use for https gateway settings|
|gatewayProxies.gatewayProxy.gatewaySettings.accessLoggingService.NAME|interface||custom yaml to use for access logging service (https://docs.solo.io/gloo-edge/latest/reference/api/github.com/solo-io/gloo/projects/gloo/api/v1/options/als/als.proto.sk/)|
|gatewayProxies.gatewayProxy.gatewaySettings.options.NAME|interface||custom options for http(s) gateways (https://docs.solo.io/gloo-edge/latest/reference/api/github.com/solo-io/gloo/projects/gloo/api/v1/options.proto.sk/#listeneroptions)|
|gatewayProxies.gatewayProxy.gatewaySettings.httpGatewayKubeOverride.NAME|interface|||
|gatewayProxies.gatewayProxy.gatewaySettings.httpsGatewayKubeOverride.NAME|interface|||
|gatewayProxies.gatewayProxy.gatewaySettings.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.gatewayProxy.extraEnvoyArgs[]|string||Envoy container args, (e.g. https://www.envoyproxy.io/docs/envoy/latest/operations/cli)|
|gatewayProxies.gatewayProxy.extraContainersHelper|string|||
|gatewayProxies.gatewayProxy.extraInitContainersHelper|string|||
|gatewayProxies.gatewayProxy.extraVolumes[].NAME|interface|||
|gatewayProxies.gatewayProxy.extraVolumeHelper|string|||
|gatewayProxies.gatewayProxy.extraListenersHelper|string|||
|gatewayProxies.gatewayProxy.stats.enabled|bool||Controls whether or not Envoy stats are enabled|
|gatewayProxies.gatewayProxy.stats.routePrefixRewrite|string||The Envoy stats endpoint to which the metrics are written|
|gatewayProxies.gatewayProxy.stats.setDatadogAnnotations|bool||Sets the default datadog annotations|
|gatewayProxies.gatewayProxy.stats.enableStatsRoute|bool||Enables an additional route to the stats cluster defaulting to /stats|
|gatewayProxies.gatewayProxy.stats.statsPrefixRewrite|string||The Envoy stats endpoint with general metrics for the additional stats route|
|gatewayProxies.gatewayProxy.stats.serviceMonitorEnabled|bool||Whether or not to expose an http-monitoring port that can be scraped by a Prometheus Service Monitor. Requires that 'enabled' is also true|
|gatewayProxies.gatewayProxy.stats.podMonitorEnabled|bool||Whether or not to expose an http-monitoring port that can be scraped by a Prometheus Pod Monitor. Requires that 'enabled' is also true|
|gatewayProxies.gatewayProxy.readConfig|bool||expose a read-only subset of the Envoy admin api|
|gatewayProxies.gatewayProxy.readConfigMulticluster|bool||expose a read-only subset of the Envoy admin api to gloo-fed|
|gatewayProxies.gatewayProxy.extraProxyVolumeMounts[].NAME|interface|||
|gatewayProxies.gatewayProxy.extraProxyVolumeMountHelper|string||name of custom made named template allowing for extra volume mounts on the proxy container|
|gatewayProxies.gatewayProxy.loopBackAddress|string|127.0.0.1|Name on which to bind the loop-back interface for this instance of Envoy. Defaults to 127.0.0.1, but other common values may be localhost or ::1|
|gatewayProxies.gatewayProxy.failover.enabled|bool|false|(Enterprise Only): Configure this proxy for failover|
|gatewayProxies.gatewayProxy.failover.port|uint|15443|(Enterprise Only): Port to use for failover Gateway Bind port, and service. Default is 15443|
|gatewayProxies.gatewayProxy.failover.nodePort|uint||(Enterprise Only): Optional NodePort for failover Service|
|gatewayProxies.gatewayProxy.failover.secretName|string|failover-downstream|(Enterprise Only): Secret containing downstream Ssl Secrets Default is failover-downstream|
|gatewayProxies.gatewayProxy.failover.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.gatewayProxy.disabled|bool||Skips creation of this gateway proxy. Used to turn off gateway proxies created by preceding configurations|
|gatewayProxies.gatewayProxy.envoyApiVersion|string|V3|Version of the Envoy API to use for the xDS transport and resources. Default is V3|
|gatewayProxies.gatewayProxy.envoyBootstrapExtensions[].NAME|interface||List of bootstrap extensions to add to Envoy bootstrap config. Examples include Wasm Service (https://www.envoyproxy.io/docs/envoy/latest/api-v3/extensions/wasm/v3/wasm.proto#extensions-wasm-v3-wasmservice).|
|gatewayProxies.gatewayProxy.envoyOverloadManager.NAME|interface||Overload Manager definition for Envoy bootstrap config. If enabled, a list of Resource Monitors MUST be defined in order to produce a valid Envoy config (https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/overload/v3/overload.proto#overload-manager).|
|gatewayProxies.gatewayProxy.envoyOverloadManager.actions|interface||Overload Manager definition for Envoy bootstrap config. If enabled, a list of Resource Monitors MUST be defined in order to produce a valid Envoy config (https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/overload/v3/overload.proto#overload-manager).|
|gatewayProxies.gatewayProxy.envoyOverloadManager.bufferFactoryConfig|interface||Overload Manager definition for Envoy bootstrap config. If enabled, a list of Resource Monitors MUST be defined in order to produce a valid Envoy config (https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/overload/v3/overload.proto#overload-manager).|
|gatewayProxies.gatewayProxy.envoyOverloadManager.enabled|interface||Overload Manager definition for Envoy bootstrap config. If enabled, a list of Resource Monitors MUST be defined in order to produce a valid Envoy config (https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/overload/v3/overload.proto#overload-manager).|
|gatewayProxies.gatewayProxy.envoyOverloadManager.refreshInterval|interface||Overload Manager definition for Envoy bootstrap config. If enabled, a list of Resource Monitors MUST be defined in order to produce a valid Envoy config (https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/overload/v3/overload.proto#overload-manager).|
|gatewayProxies.gatewayProxy.envoyOverloadManager.resourceMonitors|interface||Overload Manager definition for Envoy bootstrap config. If enabled, a list of Resource Monitors MUST be defined in order to produce a valid Envoy config (https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/overload/v3/overload.proto#overload-manager).|
|gatewayProxies.gatewayProxy.envoyStaticClusters[].NAME|interface||List of extra static clusters to be added to Envoy bootstrap config. https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/cluster/v3/cluster.proto#envoy-v3-api-msg-config-cluster-v3-cluster|
|gatewayProxies.gatewayProxy.horizontalPodAutoscaler.apiVersion|string||accepts autoscaling/v1, autoscaling/v2beta2 or autoscaling/v2. Note: autoscaling/v2beta2 is deprecated as of Kubernetes 1.26.|
|gatewayProxies.gatewayProxy.horizontalPodAutoscaler.minReplicas|int32||minReplicas is the lower limit for the number of replicas to which the autoscaler can scale down.|
|gatewayProxies.gatewayProxy.horizontalPodAutoscaler.maxReplicas|int32||maxReplicas is the upper limit for the number of replicas to which the autoscaler can scale up. It cannot be less that minReplicas.|
|gatewayProxies.gatewayProxy.horizontalPodAutoscaler.targetCPUUtilizationPercentage|int32||target average CPU utilization (represented as a percentage of requested CPU) over all the pods. Used only with apiVersion autoscaling/v1|
|gatewayProxies.gatewayProxy.horizontalPodAutoscaler.metrics[].NAME|interface||metrics contains the specifications for which to use to calculate the desired replica count (the maximum replica count across all metrics will be used). Used only with apiVersion autoscaling/v2beta2|
|gatewayProxies.gatewayProxy.horizontalPodAutoscaler.behavior.NAME|interface||behavior configures the scaling behavior of the target in both Up and Down directions (scaleUp and scaleDown fields respectively). Used only with apiVersion autoscaling/v2beta2|
|gatewayProxies.gatewayProxy.horizontalPodAutoscaler.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.gatewayProxy.podDisruptionBudget.minAvailable|string||Corresponds directly with the _minAvailable_ field in the [PodDisruptionBudgetSpec](https://kubernetes.io/docs/reference/kubernetes-api/policy-resources/pod-disruption-budget-v1/#PodDisruptionBudgetSpec). This value is mutually exclusive with _maxUnavailable_.|
|gatewayProxies.gatewayProxy.podDisruptionBudget.maxUnavailable|string||Corresponds directly with the _maxUnavailable_ field in the [PodDisruptionBudgetSpec](https://kubernetes.io/docs/reference/kubernetes-api/policy-resources/pod-disruption-budget-v1/#PodDisruptionBudgetSpec). This value is mutually exclusive with _minAvailable_.|
|gatewayProxies.gatewayProxy.podDisruptionBudget.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|gatewayProxies.gatewayProxy.istioMetaMeshId|string||ISTIO_META_MESH_ID Environment Variable. Defaults to "cluster.local"|
|gatewayProxies.gatewayProxy.istioMetaClusterId|string||ISTIO_META_CLUSTER_ID Environment Variable. Defaults to "Kubernetes"|
|gatewayProxies.gatewayProxy.istioDiscoveryAddress|string|istiod.istio-system.svc:15012|discoveryAddress field of the PROXY_CONFIG environment variable. Defaults to "istiod.istio-system.svc:15012"|
|gatewayProxies.gatewayProxy.istioSpiffeCertProviderAddress|string||Address of the spiffe certificate provider. Defaults to istioDiscoveryAddress|
|gatewayProxies.gatewayProxy.envoyLogLevel|string||Level at which the pod should log. Options include "trace", "info", "debug", "warn", "error", "critical" and "off". Default level is info|
|gatewayProxies.gatewayProxy.envoyStatsConfig.NAME|interface||Envoy statistics configuration, such as tagging. For more info, see https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/metrics/v3/stats.proto#config-metrics-v3-statsconfig|
|gatewayProxies.gatewayProxy.xdsServiceAddress|string||The k8s service name for the xds server. Defaults to gloo.|
|gatewayProxies.gatewayProxy.xdsServicePort|uint32||The k8s service port for the xds server. Defaults to the value from .Values.gloo.deployment.xdsPort, but can be overridden to use, for example, xds-relay.|
|gatewayProxies.gatewayProxy.tcpKeepaliveTimeSeconds|uint32|60|The amount of time in seconds for connections to be idle before sending keep-alive probes. Defaults to 60. See here: https://www.envoyproxy.io/docs/envoy/latest/api-v3/config/core/v3/address.proto#envoy-v3-api-msg-config-core-v3-tcpkeepalive|
|gatewayProxies.gatewayProxy.disableCoreDumps|bool|false|If set to true, Envoy will not generate core dumps in the event of a crash. Defaults to false|
|gatewayProxies.gatewayProxy.disableExtauthSidecar|bool|false|If set to true, this gateway proxy will not come up with an extauth sidecar container when global.extAuth.envoySidecar is enabled. This setting has no effect otherwise. Defaults to false|
|gatewayProxies.gatewayProxy.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|ingress.enabled|bool|false||
|ingress.deployment.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|ingress.deployment.image.repository|string|ingress|The image repository (name) for the container.|
|ingress.deployment.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|ingress.deployment.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|ingress.deployment.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|ingress.deployment.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|ingress.deployment.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|ingress.deployment.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|ingress.deployment.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|ingress.deployment.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|ingress.deployment.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|ingress.deployment.runAsUser|float64||Explicitly set the user ID for the processes in the container to run as. Default is 10101.|
|ingress.deployment.floatingUserId|bool||If true, allows the cluster to dynamically assign a user ID for the processes running in the container.|
|ingress.deployment.extraIngressLabels.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.labels data of the ingress deployment.|
|ingress.deployment.extraIngressAnnotations.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.annotations data of the ingress deployment.|
|ingress.deployment.stats|bool||Controls whether or not Envoy stats are enabled|
|ingress.deployment.ingressContainerSecurityContext.capabilities.add[]|string|||
|ingress.deployment.ingressContainerSecurityContext.capabilities.drop[]|string|||
|ingress.deployment.ingressContainerSecurityContext.privileged|bool|||
|ingress.deployment.ingressContainerSecurityContext.seLinuxOptions.user|string|||
|ingress.deployment.ingressContainerSecurityContext.seLinuxOptions.role|string|||
|ingress.deployment.ingressContainerSecurityContext.seLinuxOptions.type|string|||
|ingress.deployment.ingressContainerSecurityContext.seLinuxOptions.level|string|||
|ingress.deployment.ingressContainerSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|ingress.deployment.ingressContainerSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|ingress.deployment.ingressContainerSecurityContext.windowsOptions.runAsUserName|string|||
|ingress.deployment.ingressContainerSecurityContext.windowsOptions.hostProcess|bool|||
|ingress.deployment.ingressContainerSecurityContext.runAsUser|int64|||
|ingress.deployment.ingressContainerSecurityContext.runAsGroup|int64|||
|ingress.deployment.ingressContainerSecurityContext.runAsNonRoot|bool|||
|ingress.deployment.ingressContainerSecurityContext.readOnlyRootFilesystem|bool|||
|ingress.deployment.ingressContainerSecurityContext.allowPrivilegeEscalation|bool|||
|ingress.deployment.ingressContainerSecurityContext.procMount|string|||
|ingress.deployment.ingressContainerSecurityContext.seccompProfile.type|string|||
|ingress.deployment.ingressContainerSecurityContext.seccompProfile.localhostProfile|string|||
|ingress.deployment.ingressContainerSecurityContext.appArmorProfile.type|string|||
|ingress.deployment.ingressContainerSecurityContext.appArmorProfile.localhostProfile|string|||
|ingress.deployment.ingressContainerSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|ingress.deployment.replicas|int|1|number of instances to deploy|
|ingress.deployment.customEnv[].name|string|||
|ingress.deployment.customEnv[].value|string|||
|ingress.deployment.customEnv[].valueFrom.fieldRef.apiVersion|string|||
|ingress.deployment.customEnv[].valueFrom.fieldRef.fieldPath|string|||
|ingress.deployment.customEnv[].valueFrom.resourceFieldRef.containerName|string|||
|ingress.deployment.customEnv[].valueFrom.resourceFieldRef.resource|string|||
|ingress.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|int64|||
|ingress.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|int32|||
|ingress.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|bool|||
|ingress.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|uint|||
|ingress.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|int32|||
|ingress.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|ingress.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|ingress.deployment.customEnv[].valueFrom.configMapKeyRef.name|string|||
|ingress.deployment.customEnv[].valueFrom.configMapKeyRef.key|string|||
|ingress.deployment.customEnv[].valueFrom.configMapKeyRef.optional|bool|||
|ingress.deployment.customEnv[].valueFrom.secretKeyRef.name|string|||
|ingress.deployment.customEnv[].valueFrom.secretKeyRef.key|string|||
|ingress.deployment.customEnv[].valueFrom.secretKeyRef.optional|bool|||
|ingress.deployment.restartPolicy|string||restart policy to use when the pod exits|
|ingress.deployment.priorityClassName|string||name of a defined priority class|
|ingress.deployment.nodeName|string||name of node to run on|
|ingress.deployment.nodeSelector.NAME|string||label selector for nodes|
|ingress.deployment.tolerations[].key|string|||
|ingress.deployment.tolerations[].operator|string|||
|ingress.deployment.tolerations[].value|string|||
|ingress.deployment.tolerations[].effect|string|||
|ingress.deployment.tolerations[].tolerationSeconds|int64|||
|ingress.deployment.affinity.NAME|interface|||
|ingress.deployment.hostAliases[]|interface|||
|ingress.deployment.initContainers[]|interface||[InitContainers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of initContainers on the deployment.|
|ingress.deployment.resources.limits.memory|string||amount of memory|
|ingress.deployment.resources.limits.cpu|string||amount of CPUs|
|ingress.deployment.resources.requests.memory|string||amount of memory|
|ingress.deployment.resources.requests.cpu|string||amount of CPUs|
|ingress.deployment.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|ingress.requireIngressClass|bool||only serve traffic for Ingress objects with the Ingress Class annotation 'kubernetes.io/ingress.class'. By default the annotation value must be set to 'gloo', however this can be overridden via customIngressClass.|
|ingress.customIngressClass|bool||Only relevant when requireIngressClass is set to true. Setting this value will cause the Gloo Edge Ingress Controller to process only those Ingress objects which have their ingress class set to this value (e.g. 'kubernetes.io/ingress.class=SOMEVALUE').|
|ingressProxy.deployment.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|ingressProxy.deployment.image.repository|string|gloo-envoy-wrapper|The image repository (name) for the container.|
|ingressProxy.deployment.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|ingressProxy.deployment.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|ingressProxy.deployment.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|ingressProxy.deployment.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|ingressProxy.deployment.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|ingressProxy.deployment.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|ingressProxy.deployment.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|ingressProxy.deployment.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|ingressProxy.deployment.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|ingressProxy.deployment.httpPort|int|8080|HTTP port for the ingress container|
|ingressProxy.deployment.httpsPort|int|8443|HTTPS port for the ingress container|
|ingressProxy.deployment.extraPorts[]|interface|||
|ingressProxy.deployment.extraAnnotations.NAME|string|||
|ingressProxy.deployment.floatingUserId|bool||If true, allows the cluster to dynamically assign a user ID for the processes running in the container.|
|ingressProxy.deployment.runAsUser|float64||Explicitly set the user ID for the pod to run as. Default is 10101|
|ingressProxy.deployment.extraIngressProxyLabels.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.labels data of the ingress proxy deployment.|
|ingressProxy.deployment.stats|bool||Controls whether or not Envoy stats are enabled|
|ingressProxy.deployment.ingressProxyContainerSecurityContext.capabilities.add[]|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.capabilities.drop[]|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.privileged|bool|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.seLinuxOptions.user|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.seLinuxOptions.role|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.seLinuxOptions.type|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.seLinuxOptions.level|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.windowsOptions.runAsUserName|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.windowsOptions.hostProcess|bool|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.runAsUser|int64|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.runAsGroup|int64|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.runAsNonRoot|bool|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.readOnlyRootFilesystem|bool|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.allowPrivilegeEscalation|bool|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.procMount|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.seccompProfile.type|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.seccompProfile.localhostProfile|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.appArmorProfile.type|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.appArmorProfile.localhostProfile|string|||
|ingressProxy.deployment.ingressProxyContainerSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|ingressProxy.deployment.replicas|int|1|number of instances to deploy|
|ingressProxy.deployment.customEnv[].name|string|||
|ingressProxy.deployment.customEnv[].value|string|||
|ingressProxy.deployment.customEnv[].valueFrom.fieldRef.apiVersion|string|||
|ingressProxy.deployment.customEnv[].valueFrom.fieldRef.fieldPath|string|||
|ingressProxy.deployment.customEnv[].valueFrom.resourceFieldRef.containerName|string|||
|ingressProxy.deployment.customEnv[].valueFrom.resourceFieldRef.resource|string|||
|ingressProxy.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|int64|||
|ingressProxy.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|int32|||
|ingressProxy.deployment.customEnv[].valueFrom.resourceFieldRef.divisor|bool|||
|ingressProxy.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|uint|||
|ingressProxy.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|int32|||
|ingressProxy.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|ingressProxy.deployment.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|ingressProxy.deployment.customEnv[].valueFrom.configMapKeyRef.name|string|||
|ingressProxy.deployment.customEnv[].valueFrom.configMapKeyRef.key|string|||
|ingressProxy.deployment.customEnv[].valueFrom.configMapKeyRef.optional|bool|||
|ingressProxy.deployment.customEnv[].valueFrom.secretKeyRef.name|string|||
|ingressProxy.deployment.customEnv[].valueFrom.secretKeyRef.key|string|||
|ingressProxy.deployment.customEnv[].valueFrom.secretKeyRef.optional|bool|||
|ingressProxy.deployment.restartPolicy|string||restart policy to use when the pod exits|
|ingressProxy.deployment.priorityClassName|string||name of a defined priority class|
|ingressProxy.deployment.nodeName|string||name of node to run on|
|ingressProxy.deployment.nodeSelector.NAME|string||label selector for nodes|
|ingressProxy.deployment.tolerations[].key|string|||
|ingressProxy.deployment.tolerations[].operator|string|||
|ingressProxy.deployment.tolerations[].value|string|||
|ingressProxy.deployment.tolerations[].effect|string|||
|ingressProxy.deployment.tolerations[].tolerationSeconds|int64|||
|ingressProxy.deployment.affinity.NAME|interface|||
|ingressProxy.deployment.hostAliases[]|interface|||
|ingressProxy.deployment.initContainers[]|interface||[InitContainers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of initContainers on the deployment.|
|ingressProxy.deployment.resources.limits.memory|string||amount of memory|
|ingressProxy.deployment.resources.limits.cpu|string||amount of CPUs|
|ingressProxy.deployment.resources.requests.memory|string||amount of memory|
|ingressProxy.deployment.resources.requests.cpu|string||amount of CPUs|
|ingressProxy.deployment.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|ingressProxy.configMap.data.NAME|string|||
|ingressProxy.configMap.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|ingressProxy.tracing|string|||
|ingressProxy.loopBackAddress|string|127.0.0.1|Name on which to bind the loop-back interface for this instance of Envoy. Defaults to 127.0.0.1, but other common values may be localhost or ::1|
|ingressProxy.label|string|ingress-proxy|Value for label gloo. Use a unique value to use several ingress proxy instances in the same cluster. Default is ingress-proxy|
|ingressProxy.service.type|string|LoadBalancer|K8s service type|
|ingressProxy.service.extraAnnotations.NAME|string||extra annotations to add to the service|
|ingressProxy.service.loadBalancerIP|string||IP address of the load balancer|
|ingressProxy.service.httpPort|int|80|HTTP port for the knative/ingress proxy service|
|ingressProxy.service.httpsPort|int|443|HTTPS port for the knative/ingress proxy service|
|ingressProxy.service.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|k8s.clusterName|string|cluster.local|cluster name to use when referencing services.|
|accessLogger.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|accessLogger.image.repository|string|access-logger|The image repository (name) for the container.|
|accessLogger.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|accessLogger.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|accessLogger.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|accessLogger.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|accessLogger.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|accessLogger.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|accessLogger.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|accessLogger.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|accessLogger.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|accessLogger.port|uint|8083||
|accessLogger.serviceName|string|AccessLog||
|accessLogger.enabled|bool|false||
|accessLogger.stats.enabled|bool|true|Controls whether or not Envoy stats are enabled|
|accessLogger.stats.routePrefixRewrite|string||The Envoy stats endpoint to which the metrics are written|
|accessLogger.stats.setDatadogAnnotations|bool||Sets the default datadog annotations|
|accessLogger.stats.enableStatsRoute|bool||Enables an additional route to the stats cluster defaulting to /stats|
|accessLogger.stats.statsPrefixRewrite|string||The Envoy stats endpoint with general metrics for the additional stats route|
|accessLogger.stats.serviceMonitorEnabled|bool||Whether or not to expose an http-monitoring port that can be scraped by a Prometheus Service Monitor. Requires that 'enabled' is also true|
|accessLogger.stats.podMonitorEnabled|bool||Whether or not to expose an http-monitoring port that can be scraped by a Prometheus Pod Monitor. Requires that 'enabled' is also true|
|accessLogger.runAsUser|float64||Explicitly set the user ID for the processes in the container to run as. Default is 10101.|
|accessLogger.fsGroup|float64||Explicitly set the group ID for volume ownership. Default is 10101|
|accessLogger.extraAccessLoggerLabels.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.labels data of the access logger deployment.|
|accessLogger.extraAccessLoggerAnnotations.NAME|string||Optional extra key-value pairs to add to the spec.template.metadata.annotations data of the access logger deployment.|
|accessLogger.service.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|accessLogger.deployment.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|accessLogger.accessLoggerContainerSecurityContext.capabilities.add[]|string|||
|accessLogger.accessLoggerContainerSecurityContext.capabilities.drop[]|string|||
|accessLogger.accessLoggerContainerSecurityContext.privileged|bool|||
|accessLogger.accessLoggerContainerSecurityContext.seLinuxOptions.user|string|||
|accessLogger.accessLoggerContainerSecurityContext.seLinuxOptions.role|string|||
|accessLogger.accessLoggerContainerSecurityContext.seLinuxOptions.type|string|||
|accessLogger.accessLoggerContainerSecurityContext.seLinuxOptions.level|string|||
|accessLogger.accessLoggerContainerSecurityContext.windowsOptions.gmsaCredentialSpecName|string|||
|accessLogger.accessLoggerContainerSecurityContext.windowsOptions.gmsaCredentialSpec|string|||
|accessLogger.accessLoggerContainerSecurityContext.windowsOptions.runAsUserName|string|||
|accessLogger.accessLoggerContainerSecurityContext.windowsOptions.hostProcess|bool|||
|accessLogger.accessLoggerContainerSecurityContext.runAsUser|int64|||
|accessLogger.accessLoggerContainerSecurityContext.runAsGroup|int64|||
|accessLogger.accessLoggerContainerSecurityContext.runAsNonRoot|bool|||
|accessLogger.accessLoggerContainerSecurityContext.readOnlyRootFilesystem|bool|||
|accessLogger.accessLoggerContainerSecurityContext.allowPrivilegeEscalation|bool|||
|accessLogger.accessLoggerContainerSecurityContext.procMount|string|||
|accessLogger.accessLoggerContainerSecurityContext.seccompProfile.type|string|||
|accessLogger.accessLoggerContainerSecurityContext.seccompProfile.localhostProfile|string|||
|accessLogger.accessLoggerContainerSecurityContext.appArmorProfile.type|string|||
|accessLogger.accessLoggerContainerSecurityContext.appArmorProfile.localhostProfile|string|||
|accessLogger.accessLoggerContainerSecurityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|accessLogger.replicas|int|1|number of instances to deploy|
|accessLogger.customEnv[].name|string|||
|accessLogger.customEnv[].value|string|||
|accessLogger.customEnv[].valueFrom.fieldRef.apiVersion|string|||
|accessLogger.customEnv[].valueFrom.fieldRef.fieldPath|string|||
|accessLogger.customEnv[].valueFrom.resourceFieldRef.containerName|string|||
|accessLogger.customEnv[].valueFrom.resourceFieldRef.resource|string|||
|accessLogger.customEnv[].valueFrom.resourceFieldRef.divisor|int64|||
|accessLogger.customEnv[].valueFrom.resourceFieldRef.divisor|int32|||
|accessLogger.customEnv[].valueFrom.resourceFieldRef.divisor|bool|||
|accessLogger.customEnv[].valueFrom.resourceFieldRef.divisor[]|uint|||
|accessLogger.customEnv[].valueFrom.resourceFieldRef.divisor[]|int32|||
|accessLogger.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|accessLogger.customEnv[].valueFrom.resourceFieldRef.divisor[]|string|||
|accessLogger.customEnv[].valueFrom.configMapKeyRef.name|string|||
|accessLogger.customEnv[].valueFrom.configMapKeyRef.key|string|||
|accessLogger.customEnv[].valueFrom.configMapKeyRef.optional|bool|||
|accessLogger.customEnv[].valueFrom.secretKeyRef.name|string|||
|accessLogger.customEnv[].valueFrom.secretKeyRef.key|string|||
|accessLogger.customEnv[].valueFrom.secretKeyRef.optional|bool|||
|accessLogger.restartPolicy|string||restart policy to use when the pod exits|
|accessLogger.priorityClassName|string||name of a defined priority class|
|accessLogger.nodeName|string||name of node to run on|
|accessLogger.nodeSelector.NAME|string||label selector for nodes|
|accessLogger.tolerations[].key|string|||
|accessLogger.tolerations[].operator|string|||
|accessLogger.tolerations[].value|string|||
|accessLogger.tolerations[].effect|string|||
|accessLogger.tolerations[].tolerationSeconds|int64|||
|accessLogger.affinity.NAME|interface|||
|accessLogger.hostAliases[]|interface|||
|accessLogger.initContainers[]|interface||[InitContainers](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/#containers) to be added to the array of initContainers on the deployment.|
|accessLogger.resources.limits.memory|string||amount of memory|
|accessLogger.resources.limits.cpu|string||amount of CPUs|
|accessLogger.resources.requests.memory|string||amount of memory|
|accessLogger.resources.requests.cpu|string||amount of CPUs|
|accessLogger.kubeResourceOverride.NAME|interface||override fields in the generated resource by specifying the yaml structure to override under the top-level key.|
|global.image.tag|string||The image tag for the container.|
|global.image.repository|string||The image repository (name) for the container.|
|global.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|global.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|global.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|global.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|global.image.registry|string|quay.io/solo-io|The image hostname prefix and registry, such as quay.io/solo-io.|
|global.image.pullPolicy|string|IfNotPresent|The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|global.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|global.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|global.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|global.extensions|interface|||
|global.glooRbac.create|bool|true|create rbac rules for the gloo-system service account|
|global.glooRbac.namespaced|bool|false|use Roles instead of ClusterRoles|
|global.glooRbac.nameSuffix|string||When nameSuffix is nonempty, append '-$nameSuffix' to the names of Gloo Edge RBAC resources; e.g. when nameSuffix is 'foo', the role 'gloo-resource-reader' will become 'gloo-resource-reader-foo'|
|global.glooStats.enabled|bool|true|Controls whether or not Envoy stats are enabled|
|global.glooStats.routePrefixRewrite|string|/stats/prometheus|The Envoy stats endpoint to which the metrics are written|
|global.glooStats.setDatadogAnnotations|bool|false|Sets the default datadog annotations|
|global.glooStats.enableStatsRoute|bool|false|Enables an additional route to the stats cluster defaulting to /stats|
|global.glooStats.statsPrefixRewrite|string|/stats|The Envoy stats endpoint with general metrics for the additional stats route|
|global.glooStats.serviceMonitorEnabled|bool||Whether or not to expose an http-monitoring port that can be scraped by a Prometheus Service Monitor. Requires that 'enabled' is also true|
|global.glooStats.podMonitorEnabled|bool||Whether or not to expose an http-monitoring port that can be scraped by a Prometheus Pod Monitor. Requires that 'enabled' is also true|
|global.glooMtls.enabled|bool|false|Enables internal mtls authentication|
|global.glooMtls.sds.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|global.glooMtls.sds.image.repository|string|sds|The image repository (name) for the container.|
|global.glooMtls.sds.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|global.glooMtls.sds.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|global.glooMtls.sds.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|global.glooMtls.sds.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|global.glooMtls.sds.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|global.glooMtls.sds.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|global.glooMtls.sds.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|global.glooMtls.sds.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|global.glooMtls.sds.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|global.glooMtls.sds.securityContext.capabilities.add[]|string|||
|global.glooMtls.sds.securityContext.capabilities.drop[]|string|||
|global.glooMtls.sds.securityContext.privileged|bool|||
|global.glooMtls.sds.securityContext.seLinuxOptions.user|string|||
|global.glooMtls.sds.securityContext.seLinuxOptions.role|string|||
|global.glooMtls.sds.securityContext.seLinuxOptions.type|string|||
|global.glooMtls.sds.securityContext.seLinuxOptions.level|string|||
|global.glooMtls.sds.securityContext.windowsOptions.gmsaCredentialSpecName|string|||
|global.glooMtls.sds.securityContext.windowsOptions.gmsaCredentialSpec|string|||
|global.glooMtls.sds.securityContext.windowsOptions.runAsUserName|string|||
|global.glooMtls.sds.securityContext.windowsOptions.hostProcess|bool|||
|global.glooMtls.sds.securityContext.runAsUser|int64|||
|global.glooMtls.sds.securityContext.runAsGroup|int64|||
|global.glooMtls.sds.securityContext.runAsNonRoot|bool|||
|global.glooMtls.sds.securityContext.readOnlyRootFilesystem|bool|||
|global.glooMtls.sds.securityContext.allowPrivilegeEscalation|bool|||
|global.glooMtls.sds.securityContext.procMount|string|||
|global.glooMtls.sds.securityContext.seccompProfile.type|string|||
|global.glooMtls.sds.securityContext.seccompProfile.localhostProfile|string|||
|global.glooMtls.sds.securityContext.appArmorProfile.type|string|||
|global.glooMtls.sds.securityContext.appArmorProfile.localhostProfile|string|||
|global.glooMtls.sds.securityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|global.glooMtls.sds.logLevel|string|info|Log level for sds.  Options include "info", "debug", "warn", "error", "panic" and "fatal". Default level is info.|
|global.glooMtls.sds.sdsResources.limits.memory|string||amount of memory|
|global.glooMtls.sds.sdsResources.limits.cpu|string||amount of CPUs|
|global.glooMtls.sds.sdsResources.requests.memory|string||amount of memory|
|global.glooMtls.sds.sdsResources.requests.cpu|string||amount of CPUs|
|global.glooMtls.envoy.image.tag|string|<release_version, ex: 1.2.3>|The image tag for the container.|
|global.glooMtls.envoy.image.repository|string|gloo-envoy-wrapper|The image repository (name) for the container.|
|global.glooMtls.envoy.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|global.glooMtls.envoy.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|global.glooMtls.envoy.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|global.glooMtls.envoy.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|global.glooMtls.envoy.image.registry|string||The image hostname prefix and registry, such as quay.io/solo-io.|
|global.glooMtls.envoy.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|global.glooMtls.envoy.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|global.glooMtls.envoy.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|global.glooMtls.envoy.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|global.glooMtls.envoy.securityContext.capabilities.add[]|string|||
|global.glooMtls.envoy.securityContext.capabilities.drop[]|string|||
|global.glooMtls.envoy.securityContext.privileged|bool|||
|global.glooMtls.envoy.securityContext.seLinuxOptions.user|string|||
|global.glooMtls.envoy.securityContext.seLinuxOptions.role|string|||
|global.glooMtls.envoy.securityContext.seLinuxOptions.type|string|||
|global.glooMtls.envoy.securityContext.seLinuxOptions.level|string|||
|global.glooMtls.envoy.securityContext.windowsOptions.gmsaCredentialSpecName|string|||
|global.glooMtls.envoy.securityContext.windowsOptions.gmsaCredentialSpec|string|||
|global.glooMtls.envoy.securityContext.windowsOptions.runAsUserName|string|||
|global.glooMtls.envoy.securityContext.windowsOptions.hostProcess|bool|||
|global.glooMtls.envoy.securityContext.runAsUser|int64|||
|global.glooMtls.envoy.securityContext.runAsGroup|int64|||
|global.glooMtls.envoy.securityContext.runAsNonRoot|bool|||
|global.glooMtls.envoy.securityContext.readOnlyRootFilesystem|bool|||
|global.glooMtls.envoy.securityContext.allowPrivilegeEscalation|bool|||
|global.glooMtls.envoy.securityContext.procMount|string|||
|global.glooMtls.envoy.securityContext.seccompProfile.type|string|||
|global.glooMtls.envoy.securityContext.seccompProfile.localhostProfile|string|||
|global.glooMtls.envoy.securityContext.appArmorProfile.type|string|||
|global.glooMtls.envoy.securityContext.appArmorProfile.localhostProfile|string|||
|global.glooMtls.envoy.securityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|global.glooMtls.istioProxy.image.tag|string|1.22.0|The image tag for the container.|
|global.glooMtls.istioProxy.image.repository|string|proxyv2|The image repository (name) for the container.|
|global.glooMtls.istioProxy.image.digest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=standard.|
|global.glooMtls.istioProxy.image.fipsDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips. If the image does not have a fips variant, this field will contain the digest for the standard image variant.|
|global.glooMtls.istioProxy.image.distrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=distroless. If the image does not have a distroless variant, this field will contain the digest for the standard image variant.|
|global.glooMtls.istioProxy.image.fipsDistrolessDigest|string||The container image's hash digest (e.g. 'sha256:12345...'), consumed when variant=fips-distroless. If the image does not have a fips-distroless variant, this field will contain either the fips variant's digest (if supported), else the distroless variant's digest (if supported), else the standard variant's digest.|
|global.glooMtls.istioProxy.image.registry|string|docker.io/istio|The image hostname prefix and registry, such as quay.io/solo-io.|
|global.glooMtls.istioProxy.image.pullPolicy|string||The image pull policy for the container. For default values, see the Kubernetes docs: https://kubernetes.io/docs/concepts/containers/images/#imagepullpolicy-defaulting|
|global.glooMtls.istioProxy.image.pullSecret|string||The image pull secret to use for the container, in the same namespace as the container pod.|
|global.glooMtls.istioProxy.image.variant|string||Specifies the variant of the control plane and data plane containers to deploy. Can take the values 'standard', 'fips', 'distroless', 'fips-distroless'. Defaults to standard. (The 'fips' and 'fips-distroless' variants are an Enterprise-only feature)|
|global.glooMtls.istioProxy.image.fips|bool||[Deprecated] Use 'variant=fips' instead. If true, deploys a version of the control plane and data plane containers that is built with FIPS-compliant crypto libraries. (Enterprise-only feature)|
|global.glooMtls.istioProxy.securityContext.capabilities.add[]|string|||
|global.glooMtls.istioProxy.securityContext.capabilities.drop[]|string|||
|global.glooMtls.istioProxy.securityContext.privileged|bool|||
|global.glooMtls.istioProxy.securityContext.seLinuxOptions.user|string|||
|global.glooMtls.istioProxy.securityContext.seLinuxOptions.role|string|||
|global.glooMtls.istioProxy.securityContext.seLinuxOptions.type|string|||
|global.glooMtls.istioProxy.securityContext.seLinuxOptions.level|string|||
|global.glooMtls.istioProxy.securityContext.windowsOptions.gmsaCredentialSpecName|string|||
|global.glooMtls.istioProxy.securityContext.windowsOptions.gmsaCredentialSpec|string|||
|global.glooMtls.istioProxy.securityContext.windowsOptions.runAsUserName|string|||
|global.glooMtls.istioProxy.securityContext.windowsOptions.hostProcess|bool|||
|global.glooMtls.istioProxy.securityContext.runAsUser|int64|||
|global.glooMtls.istioProxy.securityContext.runAsGroup|int64|||
|global.glooMtls.istioProxy.securityContext.runAsNonRoot|bool|||
|global.glooMtls.istioProxy.securityContext.readOnlyRootFilesystem|bool|||
|global.glooMtls.istioProxy.securityContext.allowPrivilegeEscalation|bool|||
|global.glooMtls.istioProxy.securityContext.procMount|string|||
|global.glooMtls.istioProxy.securityContext.seccompProfile.type|string|||
|global.glooMtls.istioProxy.securityContext.seccompProfile.localhostProfile|string|||
|global.glooMtls.istioProxy.securityContext.appArmorProfile.type|string|||
|global.glooMtls.istioProxy.securityContext.appArmorProfile.localhostProfile|string|||
|global.glooMtls.istioProxy.securityContext.mergePolicy|string||How to combine the defined security policy with the default security policy. Valid values are "", "no-merge", and "helm-merge". If defined as an empty string or "no-merge", use the defined security context as is.  If "helm-merge", merge this security context with the default security context according to the logic of [the helm 'merge' function](https://helm.sh/docs/chart_template_guide/function_list/#merge-mustmerge). This is intended to be used to modify a field in a security context, while using all other default values. Please note that due to how helm's 'merge' function works, you can not override a 'true' value with a 'false' value, and for that case you will need to define the entire security context and set this value to false. Default value is "".|
|global.glooMtls.istioProxy.logLevel|string|warning|Log level for istio-proxy. Options include "info", "debug", "warning", and "error". Default level is info Default is 'warning'.|
|global.glooMtls.istioProxy.istioMetaMeshId|string||ISTIO_META_MESH_ID Environment Variable. Warning: this value is only supported with {{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} proxy. Defaults to "cluster.local"|
|global.glooMtls.istioProxy.istioMetaClusterId|string||ISTIO_META_CLUSTER_ID Environment Variable. Warning: this value is only supported with {{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} proxy. Defaults to "Kubernetes"|
|global.glooMtls.istioProxy.istioDiscoveryAddress|string||discoveryAddress field of the PROXY_CONFIG environment variable. Warning: this value is only supported with {{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} proxy. Defaults to "istiod.istio-system.svc:15012"|
|global.glooMtls.envoySidecarResources.limits.memory|string||amount of memory|
|global.glooMtls.envoySidecarResources.limits.cpu|string||amount of CPUs|
|global.glooMtls.envoySidecarResources.requests.memory|string||amount of memory|
|global.glooMtls.envoySidecarResources.requests.cpu|string||amount of CPUs|
|global.glooMtls.sdsResources.limits.memory|string||amount of memory|
|global.glooMtls.sdsResources.limits.cpu|string||amount of CPUs|
|global.glooMtls.sdsResources.requests.memory|string||amount of memory|
|global.glooMtls.sdsResources.requests.cpu|string||amount of CPUs|
|global.istioSDS.enabled|bool|false|Enables SDS cert-rotator sidecar for istio mTLS cert rotation. Warning: this value is deprecated and will be removed in a future release. Use global.istioIntegration.enabled instead.|
|global.istioSDS.customSidecars[]|interface||Override the default Istio sidecar in gateway-proxy with a custom container. Ignored if IstioSDS.enabled is false|
|global.istioIntegration.enabled|bool|false|Enables Istio integration for Gloo Edge, adding the sds and istio-proxy containers to gateways for Istio mTLS cert rotation.|
|global.istioIntegration.enableAutoMtls|bool|false|Enables Istio auto mtls configuration for Gloo Edge upstreams.|
|global.istioIntegration.disableAutoinjection|bool|false|Annotate all pods (excluding those whitelisted by other config values) to with an explicit 'do not inject' annotation to prevent Istio from adding sidecars to all pods. It's recommended that this be set to true, as some pods do not immediately work with an Istio sidecar without extra manual configuration. Warning: this value is not supported with {{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} proxy. |
|global.istioIntegration.labelInstallNamespace|bool|false|Warning: This value is deprecated and will be removed in a future release. Also, you cannot use this value with a {{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} proxy. If creating a namespace for Gloo, include the 'istio-injection: enabled' label (or 'istio.io/rev=' if 'istioSidecarRevTag' field is also set) to allow Istio sidecar injection for Gloo pods. Be aware that Istio's default injection behavior will auto-inject a sidecar into all pods in such a marked namespace. Disabling this behavior in Istio's configs or using gloo's global.istioIntegration.disableAutoinjection flag is recommended.|
|global.istioIntegration.whitelistDiscovery|bool|false|Warning: This value is deprecated and will be removed in a future release. Also, you cannot use this value with a {{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} proxy. Annotate the discovery pod for Istio sidecar injection to ensure that it gets a sidecar even when namespace-wide auto-injection is disabled. Generally only needed for FDS is enabled.|
|global.istioIntegration.enableIstioSidecarOnGateway|bool|false|Warning: This value is deprecated and will be removed in a future release. Also, you cannot use this value with a {{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} proxy. Enable Istio sidecar injection on the gateway-proxy deployment. Ignored if LabelInstallNamespace is not 'true'. Ignored if disableAutoinjection is 'true'.|
|global.istioIntegration.istioSidecarRevTag|string||Warning: This value is deprecated and will be removed in a future release. Also, you cannot use this value with a {{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} proxy. Value of revision tag for Istio sidecar injection on the gateway-proxy and discovery deployments (when enabled with LabelInstallNamespace, WhitelistDiscovery or EnableIstioSidecarOnGateway). If set, applies the label 'istio.io/rev:<rev>' instead of 'sidecar.istio.io/inject' or 'istio-injection:enabled'. Ignored if disableAutoinjection is 'true'.|
|global.istioIntegration.appendXForwardedHost|bool|true|Warning: This value is deprecated and will be removed in a future release. Also, you cannot use this value with a {{< reuse "docs/snippets/k8s-gateway-api-name.md" >}} proxy. Enable appending the X-Forwarded-Host header with the Istio-provided value. Default: true.|
|global.extraSpecs|bool||Add additional specs to include in the settings manifest, as defined by a helm partial. Defaults to false in open source, and true in enterprise.|
|global.extauthCustomYaml|bool|true|Inject whatever yaml exists in .Values.global.extensions.extAuth into settings.spec.extauth, instead of structured yaml (which is enterprise only). Defaults to true in open source, and false in enterprise|
|global.console|interface||Configuration options for the Enterprise Console (UI).|
|global.graphql|interface||(Enterprise Only): GraphQL configuration options.|
|global.configMaps[].name|string||Name of the ConfigMap to create (required).|
|global.configMaps[].namespace|string||Namespace in which to create the ConfigMap. If empty, defaults to Gloo Edge install namespace.|
|global.configMaps[].data.NAME|string||Key-value pairs of ConfigMap data.|
|global.extraCustomResources|bool||Add additional custom resources to create, as defined by a helm partial. Defaults to false in open source, and true in enterprise.|
|global.additionalLabels.NAME|string||Additional labels to add to all gloo resources.|
|global.podSecurityStandards.container.enableRestrictedContainerDefaults|bool||Set to true to default all containers to a security policy that minimally conforms to a [restricted container security policy](https://kubernetes.io/docs/concepts/security/pod-security-standards/#restricted). |
|global.podSecurityStandards.container.defaultSeccompProfileType|string||The seccomp profile type to use for default restricted container securityContexts. Valid values are 'RuntimeDefault' and 'Localhost'. Default is 'RuntimeDefault'. Has no effect if enableRestrictedContainerDefaults is false.|
|global.securitySettings.floatingUserId|bool||If true, use 'true' as default value for all instances of floatingUserId. In OSS, has the additional effects of rendering charts as if 'discovery.deployment.enablePodSecurityContext=false' and 'gatewayProxies.gatewayProxy.podTemplate.enablePodSecurityContext=false'. In EE templates  has the additional effects of rendering charts as if 'redis.deployment.enablePodSecurityContext=false', and in the ExtAuth deployment's podSecurityContext, behavior will match the local 'floatingUserId' and fsGroup will not be rendered.|

