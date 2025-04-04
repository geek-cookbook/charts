# webtrees

![Version: 2.1.2](https://img.shields.io/badge/Version-2.1.2-informational?style=flat-square) ![AppVersion: 2.0.19](https://img.shields.io/badge/AppVersion-2.0.19-informational?style=flat-square)

Open-source online collaborative genealogy application

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/geek-cookbook/charts/issues/new/choose)**

## Source Code

* <https://github.com/fisharebest/webtrees>
* <https://github.com/NathanVaughn/webtrees-docker>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | mariadb | 11.0.14 |
| https://library-charts.k8s-at-home.com | common | 4.5.2 |

## TL;DR

```console
helm repo add geek-cookbook https://geek-cookbook.github.io/charts/
helm repo update
helm install webtrees geek-cookbook/webtrees
```

## Installing the Chart

To install the chart with the release name `webtrees`

```console
helm install webtrees geek-cookbook/webtrees
```

## Uninstalling the Chart

To uninstall the `webtrees` deployment

```console
helm uninstall webtrees
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install webtrees \
  --set env.TZ="America/New York" \
    geek-cookbook/webtrees
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install webtrees geek-cookbook/webtrees -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See [webtrees-docker documentation](https://github.com/NathanVaughn/webtrees-docker#environment-variables) for more details. |
| env.BASE_URL | string | `"https://webtrees.geek-cookbook.com"` | Base URL of the installation, with protocol. This needs to be in the form of http://webtrees.example.com |
| env.DB_HOST | string | `nil` | Database hostname |
| env.DB_NAME | string | `nil` | Database to connect to |
| env.DB_PASS | string | `nil` | Database password |
| env.DB_PORT | string | `"3306"` | Database server port |
| env.DB_PREFIX | string | `"wt_"` | Prefix to give all tables in the database. Set this to a value of "" to have no table prefix. |
| env.DB_TYPE | string | `"mysql"` | Database server type |
| env.DB_USER | string | `nil` | Database username |
| env.LANG | string | `"en-US"` | webtrees localization setting |
| env.PRETTY_URLS | string | `"TRUE"` | Enable pretty URLs |
| env.TZ | string | `"UTC"` | Set the container timezone |
| env.WT_EMAIL | string | `nil` | Admin account email |
| env.WT_NAME | string | `nil` | Admin account full name |
| env.WT_PASS | string | `nil` | Admin account password |
| env.WT_USER | string | `nil` | Admin account username |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/nathanvaughn/webtrees"` | image repository |
| image.tag | string | `"2.0.19"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| mariadb | object | See values.yaml | Enable and configure mariadb database subchart under this key.    For more options see [mariadb chart documentation](https://github.com/bitnami/charts/tree/master/bitnami/mariadb) |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 2.1.2

#### Added

N/A

#### Changed

* Upgraded `common` chart dependency to version 4.5.2

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/geek-cookbook/webtrees?modal=changelog)

## Support

- See the [Docs](https://geek-cookbook.funkypenguin.co.nz/)
- Open an [issue](https://github.com/geek-cookbook/charts/issues/new/choose)
- Ask a [question](https://github.com/geek-cookbook/organization/discussions)
- Join our [Discord](http://chat.funkypenguin.co.nz) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/geek-cookbook/helm-docs/releases/v0.1.1)
