# my-artifactory
```
helm repo add jfrog https://charts.jfrog.io
helm repo update
helm upgrade --install artifactory-oss --set artifactory.postgresql.auth.password=<pwd> jfrog/artifactory-oss --namespace artifactory-oss --create-namespace
```

https://artifactory.gpu02.lysdemolab.fr/ui/login
