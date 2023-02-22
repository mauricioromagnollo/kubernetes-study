# Acessando servidor MySQL de um pod

```sh
kubectl create -f pods/mysql.yaml --save-config --record
```

```sh
kubectl create -f deployments/webapp.yaml --save-config --record
```

```sh
# Vamos pegar o IP do nosso Pod de MySQL
kubectl describe pod mysql-pod
# 10.244.0.2
```

```sh
# Vamos pegar o nome que foi criado para o nosso pod webapp
kubect get pods
# webapp-5db44756bc-74l2q
```

```sh
# Acessando o bash do Pod
kubectl exec -it webapp-5db44756bc-74l2q -- bash
```

```sh
# De dentro do Pod, vamos dar um update
apt update
# Agora vamos instalar o MySQL
apt install default-mysql-client -y
# Agora vamos conectar via rede ao nosso pod de mysql
mysql -h 10.244.0.2 -uroot -ppassword geek
```

