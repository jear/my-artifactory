# my-artifactory
```
export MASTER_KEY=$(openssl rand -hex 32)
echo ${MASTER_KEY}
export JOIN_KEY=$(openssl rand -hex 32)
echo ${JOIN_KEY}

k create ns artifactory
kubectl create secret generic my-masterkey-secret -n artifactory --from-literal=master-key=${MASTER_KEY}
kubectl create secret generic my-joinkey-secret -n artifactory --from-literal=join-key=${JOIN_KEY}

helm repo add jfrog https://charts.jfrog.io
helm repo update

#helm upgrade --install artifactory   --set artifactory.masterKey=${MASTER_KEY}   --set artifactory.joinKey=${JOIN_KEY}   --namespace artifactory --create-namespace   jfrog/artifactory

helm upgrade --install artifactory --set artifactory.postgresql.auth.password=<pwd>                                --namespace artifactory-oss --create-namespace jfrog/artifactory-oss
helm upgrade --install artifactory --set artifactory.masterKey=${MASTER_KEY} --set artifactory.joinKey=${JOIN_KEY} --namespace artifactory --create-namespace jfrog/artifactory



```

https://artifactory.gpu02.lysdemolab.fr/ui/login
