---
title: Configuration Parameters of node-exporter Helm Chart
description: This tutorial explains about Configuration Parameters
---


### Configuration Parameters of node-exporter Helm Chart

The node-exporter Helm Chart can be customized by specifying configurable Parameters while installing the chart.

The detailed description of these lists of configurable parameters for node-exporter Helm chart with their default values per section/component can be checked at "Parameters" Section of following link:

https://github.com/bitnami/charts/tree/master/bitnami/node-exporter


## Parameters

The following table lists the configurable parameters of the Node Exporter chart and their default values.

| Parameter                               | Description                                                                                              | Default                                                                   |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------|
| `global.imageRegistry`                  | Global Docker image registry                                                                             | `nil`                                                                     |
| `global.imagePullSecrets`               | Global Docker registry secret names as an array                                                          | `[]` (does not add image pull secrets to deployed pods)                   |
| `global.storageClass`                   | Global storage class for dynamic provisioning                                                            | `nil`                                                                     |
| `global.labels`                         | Additional labels to apply to all resource                                                               | `{}`                                                                      |
| `nameOverride`                          | String to partially override `common.names.fullname` template with a string                              | `nil`                                                                     |
| `fullnameOverride`                      | String to fully override `common.names.fullname` template with a string                                  | `nil`                                                                     |
| `rbac.create`                           | Whether to create & use RBAC resources or not                                                             | `true`                                                                    |
| `rbac.apiVersion`                       | Version of the RBAC API                                                                                  | `v1beta1`                                                                 |
| `rbac.pspEnabled`                       | PodSecurityPolicy                                                                                        | `true`                                                                    |
| `serviceAccount.create`                 | Specify whether to create a ServiceAccount for Node Exporter                                             | `true`                                                                    |
| `serviceAccount.name`                   | The name of the ServiceAccount to create                                                                 | Generated using the `common.names.fullname` template                      |
| `image.registry`                        | Node Exporter image registry                                                                             | `docker.io`                                                               |
| `image.repository`                      | Node Exporter Image name                                                                                 | `bitnami/node-exporter`                                                   |
| `image.tag`                             | Node Exporter Image tag                                                                                  | `{TAG_NAME}`                                                              |
| `image.pullPolicy`                      | Node Exporter image pull policy                                                                          | `IfNotPresent`                                                            |
| `image.pullSecrets`                     | Specify docker-registry secret names as an array                                                         | `[]` (does not add image pull secrets to deployed pods)                   |
| `extraArgs`                             | Additional command line arguments to pass to node-exporter                                               | `{}`                                                                      |
| `extraVolumes`                          | Additional volumes to the node-exporter pods                                                             | `{}`                                                                      |
| `extraVolumeMounts`                     | Additional volumeMounts to the node-exporter container                                                   | `{}`                                                                      |
| `securityContext.enabled`               | Enable security context                                                                                  | `true`                                                                    |
| `securityContext.runAsUser`             | User ID for the container                                                                                | `1001`                                                                    |
| `securityContext.fsGroup`               | Group ID for the container filesystem                                                                    | `1001`                                                                    |
| `service.type`                          | Kubernetes service type                                                                                  | `ClusterIP`                                                               |
| `service.port`                          | Node Exporter service port                                                                               | `9100`                                                                    |
| `service.targetPort`                    | Node Exporter container target port                                                                      | `9100`                                                                    |
| `service.clusterIP`                     | Specific cluster IP when service type is cluster IP. Use `None` for headless service                     | `nil`                                                                     |
| `service.nodePort`                      | Kubernetes Service nodePort                                                                              | `nil`                                                                     |
| `service.loadBalancerIP`                | `loadBalancerIP` if service type is `LoadBalancer`                                                       | `nil`                                                                     |
| `service.loadBalancerSourceRanges`      | Address that are allowed when svc is `LoadBalancer`                                                      | `[]`                                                                      |
| `service.addPrometheusScrapeAnnotation` | Add the `prometheus.io/scrape: "true"` annotation to the service                                         | `true`                                                                    |
| `service.annotations`                   | Additional annotations for Node Exporter service                                                         | `{}`                                                                      |
| `service.labels`                        | Additional labels for Node Exporter service                                                              | `{}`                                                                      |
| `updateStrategy`                        | The update strategy to apply to the DaemonSet                                                            | `{ "type": "RollingUpdate", "rollingUpdate": { "maxUnavailable": "1" } }` |
| `hostNetwork`                           | Expose the service to the host network                                                                   | `true`                                                                    |
| `minReadySeconds`                       | `minReadySeconds` to avoid killing pods before we are ready                                              | `0`                                                                       |
| `priorityClassName`                     | Priority class assigned to the Pods                                                                      | `nil`                                                                     |
| `resources`                             | Resource requests/limit                                                                                  | `{}`                                                                      |
| `podLabels`                             | Pod labels                                                                                               | `{}`                                                                      |
| `podAnnotations`                        | Pod annotations                                                                                          | `{}`                                                                      |
| `podAffinityPreset`                     | Pod affinity preset. Ignored if `affinity` is set. Allowed values: `soft` or `hard`                      | `""`                                                                      |
| `podAntiAffinityPreset`                 | Pod anti-affinity preset. Ignored if `affinity` is set. Allowed values: `soft` or `hard`                 | `soft`                                                                    |
| `nodeAffinityPreset.type`               | Node affinity preset type. Ignored if `affinity` is set. Allowed values: `soft` or `hard`                | `""`                                                                      |
| `nodeAffinityPreset.key`                | Node label key to match Ignored if `affinity` is set.                                                    | `""`                                                                      |
| `nodeAffinityPreset.values`             | Node label values to match. Ignored if `affinity` is set.                                                | `[]`                                                                      |
| `affinity`                              | Affinity for pod assignment                                                                              | `{}` (evaluated as a template)                                            |
| `nodeSelector`                          | Node labels for pod assignment                                                                           | `{}` (evaluated as a template)                                            |
| `tolerations`                           | Tolerations for pod assignment                                                                           | `[]` (evaluated as a template)                                            |
| `livenessProbe.enabled`                 | Turn on and off liveness probe                                                                           | `true`                                                                    |
| `livenessProbe.initialDelaySeconds`     | Delay before liveness probe is initiated                                                                 | `120`                                                                     |
| `livenessProbe.periodSeconds`           | How often to perform the probe                                                                           | `10`                                                                      |
| `livenessProbe.timeoutSeconds`          | When the probe times out                                                                                 | `5`                                                                       |
| `livenessProbe.failureThreshold`        | Minimum consecutive failures for the probe                                                               | `6`                                                                       |
| `livenessProbe.successThreshold`        | Minimum consecutive successes for the probe                                                              | `1`                                                                       |
| `readinessProbe.enabled`                | Turn on and off readiness probe                                                                          | `true`                                                                    |
| `readinessProbe.initialDelaySeconds`    | Delay before readiness probe is initiated                                                                | `30`                                                                      |
| `readinessProbe.periodSeconds`          | How often to perform the probe                                                                           | `10`                                                                      |
| `readinessProbe.timeoutSeconds`         | When the probe times out                                                                                 | `5`                                                                       |
| `readinessProbe.failureThreshold`       | Minimum consecutive failures for the probe                                                               | `6`                                                                       |
| `readinessProbe.successThreshold`       | Minimum consecutive successes for the probe                                                              | `1`                                                                       |
| `serviceMonitor.enabled`                | Creates a ServiceMonitor to monitor Node Exporter                                                        | `false`                                                                   |
| `serviceMonitor.namespace`              | Namespace in which Prometheus is running                                                                 | `nil`                                                                     |
| `serviceMonitor.interval`               | Scrape interval (use by default, falling back to Prometheus' default)                                    | `nil`                                                                     |
| `serviceMonitor.jobLabel`               | The name of the label on the target service to use as the job name in prometheus.                        | `nil`                                                                     |
| `serviceMonitor.selector`               | ServiceMonitor selector labels                                                                           | `[]`                                                                      |
| `serviceMonitor.relabelings`            | ServiceMonitor relabelings                                                                               | `[]`                                                                      |
| `serviceMonitor.metricRelabelings`      | ServiceMonitor metricRelabelings                                                                         | `[]`                                                                      |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example the following command sets the `minReadySeconds` of the Node Exporter Pods to `120` seconds.

```bash
$ helm install node-exporter --set minReadySeconds=120 bitnami/node-exporter -n monitoring
```
