# Services

```bash
kubectl create -f deployments/frontend-dp.yaml --save-config --record
```

```bash
kubectl create -f services/frontend-svc.yaml --save-config --record
```

Agora, vamos visualizar tudo o que foi criado:

```bash
kubectl get all
```

Vamos pegar o IP do cluster:

```bash
minikube ip
# Ou, podemos utilizar o comando com o nome do service:
minikube service frontend-svc --url
```