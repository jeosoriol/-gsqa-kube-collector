# GSQA Kube Collector
GreenSQA Performance Metrics Collector package for K8s.

## Dependencies
This package depends on **cert-manager >= v1.0**.

If you already have **cert-manager** installed you can ignore this step.

Use the package manager [Helm](https://helm.sh/) to install **cert-manager**  with the following steps:

```bash
helm repo add jetstack https://charts.jetstack.io 
helm repo update 
helm install cert-manager jetstack/cert-manager --namespace cert-manager --set installCRDs=true --create-namespace
```

## Installation

Use the package manager [Helm](https://helm.sh/) to install **GSQA Kube Collector** with the following steps:

**Option 1** - If you **don't have** *ingress-nginx* controller installed yet:

```bash
helm repo add gsqa-kube-collector https://greensqa.github.io/gsqa-kube-collector/
helm repo update
helm install -n gsqa-kube-collector gsqa-kube-collector gsqa-kube-collector/gsqa-kube-collector --set ingress.host=<host domain> --create-namespace
```

**Option 2** - If you **already have** *ingress-nginx* controller installed:
```bash
helm repo add gsqa-kube-collector https://greensqa.github.io/gsqa-kube-collector/
helm repo update
helm install -n gsqa-kube-collector gsqa-kube-collector gsqa-kube-collector/gsqa-kube-collector --set ingress.host=<host domain> --set ingress-nginx.enabled=false --create-namespace 
```

**Note:** This installion was tested in a local K8s and AKS (Azure Kubernetes Service) environments only.

# Authors ✒️

[TIA Team @GreenSQA](https://greensqa.com/)
