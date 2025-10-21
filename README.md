# gabarnou-iot

Repository for IoT Part 3 - GitOps with ArgoCD

## Structure

```
manifests/
└── deployment.yaml  # Kubernetes deployment and service
```

## Usage

This repository is monitored by ArgoCD. Any changes pushed to the `main` branch will be automatically synchronized to the Kubernetes cluster.

## Version Updates

The application version is defined in `manifests/deployment.yaml`:

```yaml
image: wil42/playground:v1  # or v2
```

To update the application:
1. Edit `manifests/deployment.yaml`
2. Change `v1` to `v2` (or vice versa)
3. Commit and push
4. ArgoCD will automatically sync the changes

## Application Access

After deployment, access the application:

```bash
kubectl port-forward svc/wil-app-service -n dev 8888:8888
curl http://localhost:8888/
```
