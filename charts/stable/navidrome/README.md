# navidrome

![Version: 6.4.2](https://img.shields.io/badge/Version-6.4.2-informational?style=flat-square) ![AppVersion: 0.43.0](https://img.shields.io/badge/AppVersion-0.43.0-informational?style=flat-square)

Navidrome is an open source web-based music collection server and streamer

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/geek-cookbook/charts/issues/new/choose)**

## Source Code

* <https://github.com/deluan/navidrome>
* <https://hub.docker.com/r/deluan/navidrome>

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
helm install navidrome geek-cookbook/navidrome
```

## Installing the Chart

To install the chart with the release name `navidrome`

```console
helm install navidrome geek-cookbook/navidrome
```

## Uninstalling the Chart

To uninstall the `navidrome` deployment

```console
helm uninstall navidrome
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install navidrome \
  --set env.TZ="America/New York" \
    geek-cookbook/navidrome
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install navidrome geek-cookbook/navidrome -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See [navidrome docs](https://www.navidrome.org/docs/usage/configuration-options/#environment-variables) for more details. |
| env.ND_ENABLETRANSCODINGCONFIG | string | `"true"` | Enables transcoding configuration in the UI |
| env.ND_LOGLEVEL | string | `"info"` | Log level. Useful for troubleshooting. |
| env.ND_MUSICFOLDER | string | `"/music"` | Folder where your music library is stored. |
| env.ND_SESSIONTIMEOUT | string | `"24h"` | How long Navidrome will wait before closing web ui idle sessions |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"deluan/navidrome"` | image repository |
| image.tag | string | `"0.43.0"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 6.4.2

#### Added

N/A

#### Changed

* Upgraded `common` chart dependency to version 4.5.2

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/geek-cookbook/navidrome?modal=changelog)

## Support

- See the [Docs](https://geek-cookbook.funkypenguin.co.nz/)
- Open an [issue](https://github.com/geek-cookbook/charts/issues/new/choose)
- Ask a [question](https://github.com/geek-cookbook/organization/discussions)
- Join our [Discord](http://chat.funkypenguin.co.nz) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/geek-cookbook/helm-docs/releases/v0.1.1)
