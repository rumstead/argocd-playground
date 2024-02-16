# Examples
Taken from https://docs.radapp.io/tutorials/helm/#step-4-add-radius
## Assumptions
You have a basic understanding of Argo CD, Radius, and have them both installed. 
- https://argo-cd.readthedocs.io/en/stable/#quick-start
- https://docs.radapp.io/getting-started/

### More Advanced Argo CD install
- https://github.com/rumstead/gitops-toolkit

## Commands from root of project
```shell
cd radius/demo
rad init 
kubectl create namespace demo
kubectl create secret generic --namespace demo --from-literal=url=redis://fake-server redis-secret
```
### Radius
From here, edit the helm chart to include the radius annotations.
```yaml
  annotations:
    radapp.io/enabled: 'true'
```
### Create the Argo CD application
[see here](./argocd-config/)