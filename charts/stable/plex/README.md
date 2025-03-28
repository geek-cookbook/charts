# plex

![Version: 6.4.3](https://img.shields.io/badge/Version-6.4.3-informational?style=flat-square) ![AppVersion: v1.28.0.5999-97678ded3](https://img.shields.io/badge/AppVersion-v1.28.0.5999--97678ded3-informational?style=flat-square)

Plex Media Server

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/geek-cookbook/charts/issues/new/choose)**

## Source Code

* <https://github.com/geek-cookbook/charts/tree/master/charts/stable/plex>
* <https://github.com/geek-cookbook/container-images/>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 4.5.2 |

## TL;DR

```console
helm repo add geek-cookbook https://geek-cookbook.github.io/charts/
helm repo update
helm install plex geek-cookbook/plex
```

## Installing the Chart

To install the chart with the release name `plex`

```console
helm install plex geek-cookbook/plex
```

## Uninstalling the Chart

To uninstall the `plex` deployment

```console
helm uninstall plex
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install plex \
  --set env.TZ="America/New York" \
    geek-cookbook/plex
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install plex geek-cookbook/plex -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See [plex docs](https://support.plex.tv/articles/201105343-advanced-hidden-server-settings/) for more details. **NOTE:** Plex preference options are camelCase and CASE SENSITIVE! You can do horrible things to your Plex configuration if you are not careful |
| env.TZ | string | `"UTC"` | Set the container timezone |
| hostNetwork | bool | `false` | Enable devices to be discoverable |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/geek-cookbook/plex"` | image repository |
| image.tag | string | `nil` |  |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| podSecurityContext | object | `{}` | Configure the Security Context for the Pod |
| resources | object | `{}` | Configure the resource requests and/or limits for the Pod |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 6.4.3

#### Added

N/A

#### Changed

* Upgraded `common` chart dependency to version 4.5.2

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/geek-cookbook/plex?modal=changelog)

## Support

- See the [Docs](https://geek-cookbook.funkypenguin.co.nz/)
- Open an [issue](https://github.com/geek-cookbook/charts/issues/new/choose)
- Ask a [question](https://github.com/geek-cookbook/organization/discussions)
- Join our [Discord](http://chat.funkypenguin.co.nz) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/geek-cookbook/helm-docs/releases/v0.1.1)
