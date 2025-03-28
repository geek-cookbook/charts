# deepstack

![Version: 1.5.2](https://img.shields.io/badge/Version-1.5.2-informational?style=flat-square) ![AppVersion: cpu-2021.09.1](https://img.shields.io/badge/AppVersion-cpu--2021.09.1-informational?style=flat-square)

An AI API engine that serves pre-built models and custom models on multiple edge devices locally or on your private cloud

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/geek-cookbook/charts/issues/new/choose)**

## Source Code

* <https://deepstack.cc>
* <https://github.com/johnolafenwa/DeepStack>
* <https://github.com/robmarkcole/deepstack-ui>

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
helm install deepstack geek-cookbook/deepstack
```

## Installing the Chart

To install the chart with the release name `deepstack`

```console
helm install deepstack geek-cookbook/deepstack
```

## Uninstalling the Chart

To uninstall the `deepstack` deployment

```console
helm uninstall deepstack
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install deepstack \
  --set env.TZ="America/New York" \
    geek-cookbook/deepstack
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install deepstack geek-cookbook/deepstack -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | string | See below | environment variables. See more environment variables in the [deepstack documentation](https://docs.deepstack.cc). |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"deepquestai/deepstack"` | image repository |
| image.tag | string | `"cpu"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| securityContext | object | See values.yaml | security context. May be necessary when using GPU image |
| service | object | See values.yaml | Configures service settings for the chart. |
| ui | object | `{"enabled":true,"env":null,"image":{"pullPolicy":"Always","repository":"robmarkcole/deepstack-ui","tag":"latest"},"ingress":{"ui":{"enabled":false,"primary":false}}}` | Enable scene recognition VISION-SCENE: True -- Enable face detection VISION-FACE: True -- Enable object detection VISION-DETECTION: True -- Protect detection and recognition APIs with a key API-KEY: changeMe -- Protect admin APIs (such as managing models) with a key ADMIN-KEY: changeMe |
| ui.enabled | bool | `true` | enable web UI |
| ui.env | string | See below | environment variables. See more environment variables in the [deepstack-ui README](https://github.com/robmarkcole/deepstack-ui). |
| ui.image.pullPolicy | string | `"Always"` | image pull policy |
| ui.image.repository | string | `"robmarkcole/deepstack-ui"` | image repository for ui |
| ui.image.tag | string | `"latest"` | image tag |
| ui.ingress | object | `{"ui":{"enabled":false,"primary":false}}` |    value: the timeout to wait for deepstack, default 30 seconds - name: DEEPSTACK_CUSTOM_MODEL   value: the name of a custom model, if you wish to use one - name: DEEPSTACK_UI_DEBUG_MODE   value: options `True` or `False` (default). Lowers the minimum confidence threshold to 1% |
| ui.ingress.ui | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |

## Changelog

### Version 1.5.2

#### Added

N/A

#### Changed

* Upgraded `common` chart dependency to version 4.5.2

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/geek-cookbook/deepstack?modal=changelog)

## Support

- See the [Docs](https://geek-cookbook.funkypenguin.co.nz/)
- Open an [issue](https://github.com/geek-cookbook/charts/issues/new/choose)
- Ask a [question](https://github.com/geek-cookbook/organization/discussions)
- Join our [Discord](http://chat.funkypenguin.co.nz) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/geek-cookbook/helm-docs/releases/v0.1.1)
