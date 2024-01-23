---
description: Upload a package in Chart Museum
---

# Chart Museum

```bash
# Create a namespace
kubectl create ns chartmuseum

# Use this namespace
kubectl config set-context --current --namespace=chartmuseum

# Port Forwarding
kubectl port-forward --namespace chartmuseum-ns service/chartmuseum-svc 8080:8080

# Create the package
## From the Helm Chart folder
helm package .

# Set Credentials
$credentials=<USER>:<PASSWORD>

# Push the package to the Chart Museum
curl -u $credentials --data-binary "@example-0.1.1.tgz" https://localhost:8080/api/charts
```
