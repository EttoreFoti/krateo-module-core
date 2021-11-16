# Krateo core composition

This composition represents the Krateo core architecture that has the following components:
- Krateo Dashboard
- Krateo Runtime

# Steps to install the Krateo Core module

```text
kubectl apply -f examples/krateo-package-module-core.yaml

SA=$(kubectl -n crossplane-system get sa -o name | grep provider-helm | sed -e 's|serviceaccount\/|crossplane-system:|g')

kubectl create clusterrolebinding provider-helm-admin-binding --clusterrole cluster-admin --serviceaccount="${SA}"

kubectl apply -f krateo-module-core.yaml
```
