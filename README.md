# Kubernetes Practice

Hands-on Kubernetes fundamentals running on k3s (WSL2).
Part of a DevOps/blockchain infrastructure learning path.

## What's covered

- **Pods** — basic container lifecycle and debugging loop
- **Deployments** — self-healing, scaling, rolling updates
- **Services** — ClusterIP and NodePort networking
- **ConfigMaps** — injecting non-sensitive config into pods
- **Secrets** — injecting sensitive data (JWT tokens, passwords)
- **StatefulSets** — persistent storage that survives pod crashes

## Key concept demonstrated

StatefulSet with PersistentVolumeClaim — simulating an Ethereum 
node that retains chain data across pod restarts. Data written 
to /data/ethereum survives pod deletion and rescheduling.

## Environment

- k3s v1.34.6 running in WSL2 (Ubuntu)
- Local-path storage provisioner
- Traefik ingress controller (k3s default)

## Next steps

- Ingress and Helm
- Real Ethereum node StatefulSet (Nethermind + Lighthouse)
- Prometheus/Grafana monitoring stack on Kubernetes
