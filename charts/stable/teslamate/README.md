# teslamate

![Version: 7.1.2](https://img.shields.io/badge/Version-7.1.2-informational?style=flat-square) ![AppVersion: v1.23.4](https://img.shields.io/badge/AppVersion-v1.23.4-informational?style=flat-square)

A self-hosted data logger for your Tesla 🚘

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/geek-cookbook/charts/issues/new/choose)**

## Source Code

* <https://github.com/adriankumpf/teslamate>
* <https://github.com/geek-cookbook/charts/tree/master/charts/stable/teslamate>

## Requirements

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | postgresql | 11.6.12 |
| https://library-charts.k8s-at-home.com | common | 4.5.2 |

## TL;DR

```console
helm repo add geek-cookbook https://geek-cookbook.github.io/charts/
helm repo update
helm install teslamate geek-cookbook/teslamate
```

## Installing the Chart

To install the chart with the release name `teslamate`

```console
helm install teslamate geek-cookbook/teslamate
```

## Uninstalling the Chart

To uninstall the `teslamate` deployment

```console
helm uninstall teslamate
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install teslamate \
  --set env.TZ="America/New York" \
    geek-cookbook/teslamate
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install teslamate geek-cookbook/teslamate -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See [teslamate docs](https://docs.teslamate.org/docs/configuration/environment_variables) for more details. |
| env.DATABASE_HOST | string | `"{{ include \"common.names.fullname\" .}}-postgresql"` | Postgres database hostname |
| env.DATABASE_NAME | string | `"{{ .Values.postgresql.auth.database }}"` | Postgres database password |
| env.DATABASE_PASS | string | `"{{ .Values.postgresql.auth.postgresPassword }}"` | Postgres database password |
| env.DATABASE_USER | string | `"postgres"` | Postgres database user name |
| env.DISABLE_MQTT | string | `"false"` | Disables the MQTT feature if `true` |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"teslamate/teslamate"` | image repository |
| image.tag | string | `"1.23.4"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| postgresql | object | See values.yaml | Enable and configure postgresql database subchart under this key.    For more options see [postgresql chart documentation](https://github.com/bitnami/charts/tree/master/bitnami/postgresql) |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 7.1.2

#### Added

N/A

#### Changed

* Upgraded `common` chart dependency to version 4.5.2

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/geek-cookbook/teslamate?modal=changelog)

## Support

- See the [Docs](https://geek-cookbook.funkypenguin.co.nz/)
- Open an [issue](https://github.com/geek-cookbook/charts/issues/new/choose)
- Ask a [question](https://github.com/geek-cookbook/organization/discussions)
- Join our [Discord](http://chat.funkypenguin.co.nz) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/geek-cookbook/helm-docs/releases/v0.1.1)
