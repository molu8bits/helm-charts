# Prometheus S3 Bucket Exporter

A Prometheus exporter for [S3 Bucket Exporter](https://github.com/molu8bits/s3bucket_exporter) metrics.

This chart bootstraps a Prometheus [S3 Bucket Exporter](https://github.com/molu8bits/s3bucket_exporter) deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

## Get Helm Repository Info

```console
helm repo add molu8bits https://molu8bits.github.io/helm-charts
helm repo update
```

_See [`helm repo`](https://helm.sh/docs/helm/helm_repo/) for command documentation._

## Install Chart

### General installation

```console
helm install [RELEASE_NAME] molu8bits/prometheus-s3bucket-exporter
```

### Minio endpoint example

```console
helm install prometheus-s3bucket-exporter --namespace prometheus-s3bucket-exporter --create-namespace \
  --set s3bucket.s3Endpoint="192.168.0.1:9000" --set s3bucket.s3AccessKey="access" --set s3bucket.s3SecretKey="supersecret" \
  prometheus-s3bucket-exporter --set s3bucket.s3DisableSSL=true
```

### AWS S3 endpoint example - region "eu-west-1"

```console
helm install prometheus-s3bucket-exporter --namespace prometheus-s3bucket-exporter --create-namespace \
  --set s3bucket.s3Endpoint="s3.eu-west-1.amazonaws.com" --set s3bucket.s3Region="eu-west-1" --set s3bucket.s3AccessKey="access" --set s3bucket.s3SecretKey="supersecret" \
  --set s3bucket.s3Region="us-east-1" prometheus-s3bucket-exporter
```

_See [configuration](#configuration) below._

_See [helm install](https://helm.sh/docs/helm/helm_install/) for command documentation._

## Uninstall Chart

```console
helm uninstall [RELEASE_NAME]
```

This removes all the Kubernetes components associated with the chart and deletes the release.

_See [helm uninstall](https://helm.sh/docs/helm/helm_uninstall/) for command documentation._

_See [helm upgrade](https://helm.sh/docs/helm/helm_upgrade/) for command documentation._

## Upgrading Chart

```console
helm upgrade [RELEASE_NAME] [CHART] --install
```

### Version 0.1.0

prometheus-s3bucket-exported has been set to [v1.0.2](https://github.com/molu8bits/s3bucket_exporter/releases/tag/v1.0.2).

## Configuration

See [Customizing the Chart Before Installing](https://helm.sh/docs/intro/using_helm/#customizing-the-chart-before-installing). To see all configurable options with detailed comments, visit the chart's [values.yaml](https://github.com/molu8bits/helm-charts/blob/main/charts/prometheus-s3bucket-exporter/values.yaml), or run these configuration commands:

```console
helm show values molu8bits/prometheus-s3bucket-exporter
```

### S3 Bucket Connection

The exporter connects to S3 using http or https.

- To configure S3 connection credentials by value, set `s3bucket.s3AccessKey` and `s3bucket.s3SecretKey`
- To configure S3 connection credentials by existing secret, you must store above connection variables in a secret, and set `s3bucket.existingSecret` to `[SECRET_NAME]`
- Additional mandatory values to set `s3bucket.s3name` and `s3bucket.s3Endpoint`
- Optional S3 connection parameters: `s3bucket.s3Region`, `s3bucket.s3DisableSSL`, `s3bucket.s3DisableEndpointHostPrefix` and `s3bucket.s3ForcePathStyle`
  
### Exporter Documentation and Params

Documentation for the S3 Bucket Exporter can be found here: (<https://github.com/molu8bits/s3bucket_exporter>)

### Collector Flags

Available collector flags can be found in the [values.yaml](https://github.com/molu8bits/helm-charts/blob/main/charts/prometheus-s3bucket-exporter/values.yaml) and a description of each flag can be found in the [prometheus-s3bucket-exporter](https://github.com/molu8bits/s3bucket_exporter) repository.
