# Default Helm-Values

TrueCharts is primarily build to supply TrueNAS SCALE Apps.
However, we also supply all Apps as standard Helm-Charts. In this document we aim to document the default values in our values.yaml file.

Most of our Apps also consume our "common" Helm Chart.
If this is the case, this means that all values.yaml values are set to the common chart values.yaml by default. This values.yaml file will only contain values that deviate from the common chart.
You will, however, be able to use all values referenced in the common chart here, besides the values listed in this document.

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"tccr.io/truecharts/ombi"` |  |
| image.tag | string | `"v4.14.4@sha256:ad5b0c3494f6f4cd6eb136eee664d08751bcf07e82d706932aeb92192cf491b7"` |  |
| mariadb.architecture | string | `"standalone"` |  |
| mariadb.auth.database | string | `"ombi"` |  |
| mariadb.auth.password | string | `"ombi"` |  |
| mariadb.auth.username | string | `"ombi"` |  |
| mariadb.enabled | bool | `false` |  |
| mariadb.primary.persistence.enabled | bool | `false` |  |
| persistence.config.enabled | bool | `true` |  |
| persistence.config.mountPath | string | `"/config"` |  |
| securityContext.readOnlyRootFilesystem | bool | `false` |  |
| service.main.ports.main.port | int | `3579` |  |
| service.main.ports.main.targetPort | int | `3579` |  |

All Rights Reserved - The TrueCharts Project