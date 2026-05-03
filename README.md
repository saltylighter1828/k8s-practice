# Kubernetes Practice

Hands-on Kubernetes fundamentals running on k3s (WSL2).
Part of a DevOps/blockchain infrastructure learning path.

## What's covered

- **Pods** — basic container lifecycle and debugging loop
- **Deployments** — self-healing, scaling, rolling updates
- **Services** — ClusterIP and NodePort networking
- **Namespaces** — logical isolation within a cluster
- **ConfigMaps** — injecting non-sensitive config into pods
- **Secrets** — injecting sensitive data (JWT tokens, passwords)
- **StatefulSets** — persistent storage that survives pod crashes
- **Ingress** — Traefik-based routing by hostname
- **Helm** — deploying complex stacks with one command
- **Liveness & Readiness Probes** — real-world health check debugging
- **Resource Limits** — CPU/memory requests and limits tuning

## Key concepts demonstrated

**StatefulSet with PersistentVolumeClaim** — Ethereum node that retains
chain data across pod restarts. Data written to /data/ethereum survives
pod deletion and rescheduling.

**Full Ethereum node stack on Kubernetes** — Nethermind execution client
paired with Lighthouse consensus client, JWT authentication between
clients, ConfigMap-injected configuration, and persistent storage via PVCs.

**Helm-deployed Prometheus + Grafana** — full monitoring stack deployed
with one command, pre-built Kubernetes dashboards included.

**Real probe debugging** — worked through 5 failure scenarios including
WSL2 mount restrictions, localhost-only binding, minimal container
limitations, and interdependent service startup ordering.

## Structure

```
k8s-practice/
├── configmap.yaml
├── ingress.yaml
├── nginx-deployment.yaml
├── pod-with-config.yaml
├── secret.yaml
├── statefulset.yaml
└── ethereum-node/
    ├── 00-namespace.yaml
    ├── 01-secret.yaml
    ├── 02-configmap.yaml
    ├── 03-nethermind.yaml
    └── 04-lighthouse.yaml
```

## Environment

- k3s v1.34.6 running in WSL2 (Ubuntu)
- Local-path storage provisioner
- Traefik ingress controller (k3s default)
- Helm v3.20.2

## Next steps

- Terraform integration (provision Hetzner VPS for k3s)
- CI/CD pipeline with GitHub Actions
- CKA exam preparation
