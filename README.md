# My Helm Charts

## Repositories

- bitnami `helm repo add bitnami https://charts.bitnami.com/bitnami`

### CMS
- WordPress
- Drupal
- Joomla

### Classifieds
- Osclass


---


## Run using Minikube
```sh
minikube start

helm repo add bitnami https://charts.bitnami.com/bitnami

helm install my-wordpress bitnami/wordpress

kubectl get all

kubectl describe deploy/my-wordpress

curl $(minikube ip):$(kubectl get service/my-wordpress -o jsonpath='{.spec.ports[].nodePort}')
```


### Run Ingress using Minikube
```sh
minikube addons enable ingress

curl $(minikube ip):80
# <h1>404 Not Found</h1>
# <center>nginx</center>

curl $(minikube ip):8080
# curl: (7) Failed to connect to 192.168.99.101 port 8080: Connection refused
```
