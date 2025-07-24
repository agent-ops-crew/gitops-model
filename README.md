# Model Deployment with GitOps

This repository contains a Helm chart for deploying AI models on Red Hat OpenShift AI (RHOAI) using GitOps practices.

## Getting Started

1. Install the chart:
   ```bash
   helm install my-model ./chart -n <namespace>
   ```

2. Customize the deployment by updating `chart/values.yaml`

## Deploy With ArgoCD

Apply the `application.yaml` file to your cluster:

```bash
kubectl apply -f application.yaml
```

## Documentation

- [RHOAI GitOps Documentation](https://ai-on-openshift.io/odh-rhoai/gitops/)
- [vLLM Tool Calling](https://docs.vllm.ai/en/stable/features/tool_calling.html)