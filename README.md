# kubernetes-pv-consul-vault


# Deploy helm for consul and vault
```
helm repo add hashicorp https://helm.releases.hashicorp.com

helm install consul hashicorp/consul --set global.name=consul --create-namespace --namespace consul
helm install vault hashicorp/vault --set global.name=vault --create-namespace --namespace vault
```
# SC and pvs

```
kubectl apply -f sc.yaml

kubens vault

kubectl get pvc

kubectl edit pvc

	storageClassName: local-storage

kubectl apply -f vault-pv.yaml
```


# WARNING

change the hostname from `*-pv.yaml` it is set to acer only


#init vault
```
kubectl exec -ti <name of vault pod> -- vault operator init
kubectl exec -ti <name of vault pod> -- vault operator unseal
```
