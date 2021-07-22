kubectl apply -f mongo.yaml -n unifi

helm repo add k8s-at-home https://k8s-at-home.com/charts/
helm repo update
helm install -f values.yaml unifi k8s-at-home/unifi --namespace unifi
