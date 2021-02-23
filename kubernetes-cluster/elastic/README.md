# cws-elastic-k8s
 
# Temp Setup Doccumentation

kubectl create secret generic cloudflare-api-token-secret
 --from-literal=api-token=<CLOUDFLARE_API_TOKEN>

kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v1.2.0/cert-manager.yaml

kubectl apply -f /Users/coreysabia/Documents/GitHub/cws-elastic-k8s/letsencrypt.yaml

kubectl get ns

kubectl describe certificate $(echo *.2edgy4.me | tr . -) -n cert-manager

kubectl apply -f https://download.elastic.co/downloads/eck/1.4.0/all-in-one.yaml

kubectl -n elastic-system logs -f statefulset.apps/elastic-operator

kubectl -n elastic-system get pods


kubectl apply -f /Users/coreysabia/Documents/GitHub/cws/kubernetes-cluster/elastic/elasticsearch.yaml

kubectl get elasticsearch

kubectl get pods

kubectl apply -f /Users/coreysabia/Documents/GitHub/cws/kubernetes-cluster/elastic/kibana.yaml

kubectl get kibana
kubectl get pods

PASSWORD=$(kubectl get secret cws-es-elastic-user -o go-template='{{.data.elastic | base64decode}}')
