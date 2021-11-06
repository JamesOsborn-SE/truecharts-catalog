# Default Helm-Values

TrueCharts is primarily build to supply TrueNAS SCALE Apps.
However, we also supply all Apps as standard Helm-Charts. In this document we aim to document the default values in our values.yaml file.

Most of our Apps also consume our "common" Helm Chart.
If this is the case, this means that all values.yaml values are set to the common chart values.yaml by default. This values.yaml file will only contain values that deviate from the common chart.
You will, however, be able to use all values referenced in the common chart here, besides the values listed in this document.

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env.PUID | int | `568` |  |
| git.deployKey | string | `""` |  |
| git.deployKeyBase64 | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"ghcr.io/truecharts/home-assistant"` |  |
| image.tag | string | `"v2021.10.7@sha256:28a83c183e94a8e9ba8b6242f72a1d45fc2b3c88c1fe1a72fc03f9d6beb40919"` |  |
| influxdb.architecture | string | `"standalone"` |  |
| influxdb.authEnabled | bool | `false` |  |
| influxdb.database | string | `"home_assistant"` |  |
| influxdb.enabled | bool | `false` |  |
| influxdb.persistence.enabled | bool | `false` |  |
| initContainers.init.command[0] | string | `"/config/init/init.sh"` |  |
| initContainers.init.image | string | `"{{ .Values.image.repository }}:{{ .Values.image.tag }}"` |  |
| initContainers.init.volumeMounts[0].mountPath | string | `"/config/init"` |  |
| initContainers.init.volumeMounts[0].name | string | `"init"` |  |
| initContainers.init.volumeMounts[1].mountPath | string | `"/config"` |  |
| initContainers.init.volumeMounts[1].name | string | `"config"` |  |
| persistence.config.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.config.enabled | bool | `true` |  |
| persistence.config.mountPath | string | `"/config"` |  |
| persistence.config.size | string | `"100Gi"` |  |
| persistence.config.type | string | `"pvc"` |  |
| podSecurityContext.runAsGroup | int | `0` |  |
| podSecurityContext.runAsUser | int | `0` |  |
| postgresql | object | See values.yaml | Enable and configure postgresql database subchart under this key.    For more options see [postgresql chart documentation](https://github.com/bitnami/charts/tree/master/bitnami/postgresql) |
| prometheus.serviceMonitor.enabled | bool | `false` |  |
| securityContext.readOnlyRootFilesystem | bool | `false` |  |
| securityContext.runAsNonRoot | bool | `false` |  |
| service.main.ports.main.port | int | `8123` |  |

All Rights Reserved - The TrueCharts Project