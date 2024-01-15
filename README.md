# nextdns-exporter-helm-Chart

This is an unofficial Helm Chart for [nextdns-exporter](https://github.com/raylas/nextdns-exporter).
You can use this chart to deploy nextdns-exporter to your Kubernetes cluster.

## Configurations

The following table lists the configurable parameters of the nextdns-exporter chart and their default values.

| Parameter | Description | Default |
| --------- | ----------- | ------- |
| `app.image.repository` | Image repository | `ghcr.io/raylas/nextdns-exporter` |
| `app.image.tag` | Image tag | `latest` |
| `app.image.pullPolicy` | Image pull policy | `IfNotPresent` |
| `configurations.log_level` | Log level | `INFO` |
| `configurations.metrics.port` | Metrics port | `9948` |
| `configurations.metrics.path` | Metrics path | `/metrics` |
| `configurations.result.window` | Result window | `-5m` |
| `configurations.result.limit` | Result limit | `50` |
| `configurations.nextdns.profile` | Profile ID for the NextDNS | `default` |
| `configurations.nextdns.api_key` | API key for the NextDNS | `""` |

For NextDNS Profile, you can go to [NextDNS](https://my.nextdns.io) to get it under the `Endpoints` tab named `ID`. As for the API key, you can go to [NextDNS Account](https://my.nextdns.io/account) to get your API key.

For more information about the other configurations, please refer to the [official documentation](https://github.com/raylas/nextdns-exporter?tab=readme-ov-file#configuration).

## Installation

[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

```bash
helm repo add fawenyochart https://fawenyo.github.io/helm-charts
```

then prepare your own `overrides.yaml` file and then install the chart with the following command:

```bash
helm install nextdns-exporter \
--namespace ${namespace} \
--create-namespace \
-f overrides.yaml \
fawenyochart/nextdns-exporter
```

Be sure to replace `${namespace}` with your own namespace.
