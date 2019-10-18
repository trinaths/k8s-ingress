#Create Login credentials
kubectl create serviceaccount bigip-ctlr -n kube-system
kubectl create secret generic bigip-login --namespace kube-system --from-literal=username=admin --from-literal=password=admin
kubectl apply -f rbac.yaml
kubectl apply -f deployment.yaml
kubectl create ns f5demo
