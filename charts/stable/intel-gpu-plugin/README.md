# intel-gpu-plugin

![Version: 4.4.2](https://img.shields.io/badge/Version-4.4.2-informational?style=flat-square) ![AppVersion: 0.20.0](https://img.shields.io/badge/AppVersion-0.20.0-informational?style=flat-square)

The Intel GPU plugin facilitates offloading the processing of computation intensive workloads to GPU hardware

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/geek-cookbook/charts/issues/new/choose)**

## Source Code

* <https://github.com/intel/intel-device-plugins-for-kubernetes/blob/master/cmd/gpu_plugin>

## Requirements

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 4.5.2 |

## TL;DR

```console
helm repo add geek-cookbook https://geek-cookbook.github.io/charts/
helm repo update
helm install intel-gpu-plugin geek-cookbook/intel-gpu-plugin
```

## Installing the Chart

To install the chart with the release name `intel-gpu-plugin`

```console
helm install intel-gpu-plugin geek-cookbook/intel-gpu-plugin
```

## Uninstalling the Chart

To uninstall the `intel-gpu-plugin` deployment

```console
helm uninstall intel-gpu-plugin
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install intel-gpu-plugin \
  --set env.TZ="America/New York" \
    geek-cookbook/intel-gpu-plugin
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install intel-gpu-plugin geek-cookbook/intel-gpu-plugin -f values.yaml
```

## Custom configuration

### Node Feature Discovery

If your cluster runs [Node Feature Discovery](https://github.com/geek-cookbook/charts/blob/master/charts/node-feature-discovery), you can deploy the device plugin only on nodes with Intel GPU by specifying the desired `nodeSelector` or `affinity` in your values. For example (make sure to update to your exact feature label):

```yaml
affinity:
  nodeAffinity:
    requiredDuringSchedulingIgnoredDuringExecution:
      nodeSelectorTerms:
        - matchExpressions:
            - key: feature.node.kubernetes.io/pci-0300_8086.present
              operator: In
              values:
                - "true"
```

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| args | list | `["-shared-dev-num","1"]` | Override the args for the default container Refer to the [plugin documentation](https://github.com/intel/intel-device-plugins-for-kubernetes/blob/main/cmd/gpu_plugin/README.md) for more information. |
| controller.type | string | `"daemonset"` | Run this chart as a daemonset. Do not modify unless you know what you are doing. |
| envValueFrom.NODE_NAME | object | `spec.nodeName` | Sets the NODE_NAME env var to the name of the node where the pod is running. Do not modify unless you know what you are doing. |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"intel/intel-gpu-plugin"` | image repository |
| image.tag | string | `"0.20.0"` | image tag |
| ingress.main.enabled | bool | `false` | Ingress is disabled for this chart. Do not modify unless you know what you are doing. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| probes | object | See values.yaml | Disable probes for this chart since there is no service. Do not modify unless you know what you are doing. |
| service.main.enabled | bool | `false` | Main service is disabled for this chart. Do not modify unless you know what you are doing. |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |

## Changelog

### Version 4.4.2

#### Added

N/A

#### Changed

* Upgraded `common` chart dependency to version 4.5.2

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/geek-cookbook/intel-gpu-plugin?modal=changelog)

## Support

- See the [Docs](https://geek-cookbook.funkypenguin.co.nz/)
- Open an [issue](https://github.com/geek-cookbook/charts/issues/new/choose)
- Ask a [question](https://github.com/geek-cookbook/organization/discussions)
- Join our [Discord](http://chat.funkypenguin.co.nz) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/geek-cookbook/helm-docs/releases/v0.1.1)
