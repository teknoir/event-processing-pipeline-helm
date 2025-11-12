# Event Processing Pipeline Helm Chart

This chart deploys Event Processing Pipelines to a Kubernetes cluster.

> The implementation of the Helm chart is right now the bare minimum to get it to work.

## Usage in Teknoir platform
Use the HelmChart to deploy the Event Processing Pipeline.

```yaml
---
apiVersion: helm.cattle.io/v1
kind: HelmChart
metadata:
  name: event-processing-pipeline
  namespace: default
spec:
  repo: https://teknoir.github.io/event-processing-pipeline-helm
  chart: event-processing-pipeline
  targetNamespace: default
  valuesContent: |-
    # Example for minimal configuration
    streams:
      - stream: update-frame-rate-control

```

## Example values.yaml

```yaml
defaults:
  debugLevel: DEBUG

streams:
  - stream: update-frame-rate-control

```

## Adding the repository

```bash
helm repo add teknoir-event-processing-pipeline https://teknoir.github.io/event-processing-pipeline-helm/
```

## Installing the chart

```bash
helm install event-processing-pipeline teknoir-event-processing-pipeline/event-processing-pipeline -f values.yaml
```