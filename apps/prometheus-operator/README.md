# Generate CRDs tips


Issue with CRDs - https://github.com/argoproj/argo-cd/issues/820
Deployment splitted to CRDs deployment and helm chart deployment without CRDs.
In order to prevent too large error use the following annotation in CRDs
`argocd.argoproj.io/sync-options: Replace=true` [See doc](https://argo-cd.readthedocs.io/en/stable/user-guide/sync-options/#replace-resource-instead-of-applying-changes)

Generate CRDs:
```
helm show crds prometheus-community/kube-prometheus-stack > crds.yaml
```
