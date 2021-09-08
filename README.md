# Deployment

Create Kubernetes secret for PGHERO

```bash
kubectl create secret generic pghero \
  --from-literal=database_url='postgres://user:password@hostname:5432/dbname' \
  --from-literal=username='admin' \
  --from-literal=password='StrongPassword123'
```

Deploy PGHERO

```bash
kubectl apply -f pghero-deployment.yaml
```

Expose servie for deployment:

```bash
kubectl expose deployment/pghero 
```

*Add flag `--type=NodePort` for expousing Kubernetes Node Port*


# Removal

To remove PGHERO use following command: 

```bash
kubectl delete deployment/pghero svc/pghero
```