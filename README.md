# Deployment

1. Create Kubernetes secret for PGHERO

```bash
kubectl create secret generic pghero \
  --from-literal=database_url='postgres://user:password@hostname:5432/dbname' \
  --from-literal=username='admin' \
  --from-literal=password='StrongPassword123'
```

2. Add custom Helm repository repository

```bash
helm repo add custom-pghero https://cyberglamdring.github.io/pghero-helmchart/ && helm repo update 
```

3. Fill values.yaml

4. Install PGHERO helm chart

```bash
helm install pghero -f pghero-helmchart-values.yaml pghero/pghero 
```

# Removal

To remove PGHERO use following command: 

```bash
helm unistall pghero
```
