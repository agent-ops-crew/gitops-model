# Model Serving Helm Chart

This Helm chart deploys an InferenceService for serving AI models using KServe.

## Prerequisites

- Kubernetes 1.16+
- Helm 3.0+
- KServe installed on the cluster
- NVIDIA GPU support if using GPU acceleration

## Installation

1. Install the chart:
   ```bash
   helm install my-model . -n <namespace>
   ```

## Configuration

The following table lists the configurable parameters of the chart and their default values.

| Parameter | Description | Default |
|-----------|-------------|---------|
| `inferenceService.name` | Name of the InferenceService | `qwen-instruct` |
| `inferenceService.predictor.minReplicas` | Minimum number of replicas | `1` |
| `inferenceService.predictor.maxReplicas` | Maximum number of replicas | `1` |
| `inferenceService.predictor.model.resources` | Resource requests/limits | See values.yaml |
| `inferenceService.predictor.model.storage` | Model storage configuration | See values.yaml |

## Customizing the Deployment

You can customize the deployment by creating a `values.yaml` file:

```yaml
inferenceService:
  name: my-model
  predictor:
    minReplicas: 1
    maxReplicas: 3
    model:
      resources:
        limits:
          cpu: '4'
          memory: 16Gi
          nvidia.com/gpu: '1'
```

Then install with:

```bash
helm install my-model . -f values.yaml -n <namespace>
```

## Uninstalling the Chart

To uninstall/delete the deployment:

```bash
helm delete my-model -n <namespace>
```
