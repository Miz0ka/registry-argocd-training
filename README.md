# registry-argocd-training

Registry deployment for ArgoCD training purposes

## Prerequisites

- Kubernetes cluster
- ArgoCD installed

## ArgoCD

- Add registry to ArgoCD

```bash
argocd repo add http://<registry-node>:30500 --username <username> --password <password>
```

- Create application

```bash
argocd app create <app-name> --repo http://<registry-node>:30500 --path <path> --dest-server https://kubernetes.default.svc --dest-namespace <namespace>
```

- Sync application

```bash
argocd app sync <app-name>
```
