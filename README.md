# edu-argocd-from-helm
Education purpose repo for ArgoCD deployment by community Helm chart


# Deploy instruction
1. Clone repo
2. Deploy Argocd to cluster
```
kubectl create ns argocd
kustomize build --enable-helm argocd | kubectl apply -f -
```
3. Get admin credentials
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```
4. Connect to Argocd webservice
```
kubectl port-forward service/argocd-server -n argocd 8090:443
```
5. Connect to Grafana
```
kubectl port-forward service/grafana -n grafana 3000:80
kubectl -n grafana get secret grafana -o jsonpath="{.data.admin-password}" | base64 -d
```
