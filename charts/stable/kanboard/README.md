# kanboard

![Version: 5.1.2](https://img.shields.io/badge/Version-5.1.2-informational?style=flat-square) ![AppVersion: v1.2.20](https://img.shields.io/badge/AppVersion-v1.2.20-informational?style=flat-square)

Kanboard is a free and open source Kanban project management software.

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/geek-cookbook/charts/issues/new/choose)**

## Source Code

* <https://github.com/kanboard/kanboard>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | postgresql | 11.6.12 |
| https://library-charts.k8s-at-home.com | common | 4.5.2 |

## TL;DR

```console
helm repo add geek-cookbook https://geek-cookbook.github.io/charts/
helm repo update
helm install kanboard geek-cookbook/kanboard
```

## Installing the Chart

To install the chart with the release name `kanboard`

```console
helm install kanboard geek-cookbook/kanboard
```

## Uninstalling the Chart

To uninstall the `kanboard` deployment

```console
helm uninstall kanboard
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install kanboard \
  --set env.TZ="America/New York" \
    geek-cookbook/kanboard
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install kanboard geek-cookbook/kanboard -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below (only deviations from the default settings are specified) | environment variables. See [image docs](https://docs.kanboard.org/en/latest/admin_guide/docker.html#environment-variables) and [application docs](# https://docs.kanboard.org/en/latest/admin_guide/config_file.html) for more details. |
| env.DB_DRIVER | string | `"sqlite"` | Database driver: sqlite, mysql or postgres |
| env.DB_HOSTNAME | string | `nil` | Mysql/Postgres hostname |
| env.DB_NAME | string | `nil` | Mysql/Postgres database name |
| env.DB_PASSWORD | string | `nil` | Mysql/Postgres password |
| env.DB_PORT | string | `nil` | Mysql/Postgres custom port (empty = default port) |
| env.DB_USERNAME | string | `nil` | Mysql/Postgres username |
| env.LOG_DRIVER | string | `"stdout"` | log driver: syslog, stderr, stdout or file |
| env.MAIL_CONFIGURATION | string | `"false"` | Enable/disable email configuration from the user interface |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"kanboard/kanboard"` | image repository |
| image.tag | string | `"v1.2.20"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| postgresql | object | See values.yaml | Enable and configure postgresql database subchart under this key.    For more options see [postgresql chart documentation](https://github.com/bitnami/charts/tree/master/bitnami/postgresql) |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 5.1.2

#### Added

N/A

#### Changed

* Upgraded `common` chart dependency to version 4.5.2

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/geek-cookbook/kanboard?modal=changelog)

## Support

- See the [Docs](https://geek-cookbook.funkypenguin.co.nz/)
- Open an [issue](https://github.com/geek-cookbook/charts/issues/new/choose)
- Ask a [question](https://github.com/geek-cookbook/organization/discussions)
- Join our [Discord](http://chat.funkypenguin.co.nz) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/geek-cookbook/helm-docs/releases/v0.1.1)
