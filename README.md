# freshrss

![Version: 6.4.6](https://img.shields.io/badge/Version-6.4.6-informational?style=flat-square) ![AppVersion: 1.21.0](https://img.shields.io/badge/AppVersion-1.21.0-informational?style=flat-square)

FreshRSS is a self-hosted RSS feed aggregator

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/p0l0/freshrss-helm-chart/issues/new/choose)**

## Source Code

* <https://github.com/FreshRSS/FreshRSS>
* <https://hub.docker.com/r/linuxserver/freshrss>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 4.5.2 |

## TL;DR

```console
helm repo add freshrss https://freshrss-helm.binware.dev/
helm repo update
helm install freshrss freshrss/freshrss
```

## Installing the Chart

To install the chart with the release name `freshrss`

```console
helm install freshrss freshrss/freshrss
```

## Uninstalling the Chart

To uninstall the `freshrss` deployment

```console
helm uninstall freshrss
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install freshrss \
  --set env.TZ="America/New York" \
    freshrss/freshrss
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install freshrss freshrss/freshrss -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See more environment variables in the [freshrss documentation](https://github.com/linuxserver/docker-freshrss#parameters). |
| env.PGID | string | `"1001"` | Set the container group id |
| env.PUID | string | `"1001"` | Set the container user id |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"linuxserver/freshrss"` | image repository |
| image.tag | string | `"version-1.21.0"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 6.4.6

#### Added

N/A

#### Changed

* Upgraded to FreshRSS 1.21.0

#### Fixed

N/A

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/p0l0/freshrss-helm-chart/issues/new/choose)

