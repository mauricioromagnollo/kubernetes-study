# Vote Microservice App

https://github.com/dockersamples/example-voting-app

```bash
kubectl create -f namespaces/vote.yaml --save-config --record
```

```bash
kubectl create -f deployments/ --save-config --record
```

```bash
kubectl create -f services/ --save-config --record
```

Listando tudo o que foi criado no namespace "vote":

```bash
kubectl get all -n vote
```

Pegando a URL do nosso service "result" que está dentro do namespace "vote":

```bash
minikube service result --url -n vote
```