# nextdns-exporter-helm-Chart

This is an unofficial Helm Chart for [nextdns-exporter](https://github.com/raylas/nextdns-exporter).
You can use this chart to deploy nextdns-exporter to your Kubernetes cluster.

## Configuration

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

For more information about the configuration, please refer to the [official documentation](https://github.com/raylas/nextdns-exporter?tab=readme-ov-file#configuration).

## Installation

You can first add the Helm repository with the following command:

```bash
helm repo add fawenyoChart https://fawenyo.github.io/helm-charts
```

then prepare your own `overrides.yaml` file and then install the chart with the following command:

```bash
helm install nextdns-exporter \
--namespace ${namespace} \
--create-namespace \
-f overrides.yaml \
fawenyoChart/nextdns-exporter
```

Be sure to replace `${namespace}` with your own namespace.
