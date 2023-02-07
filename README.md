# kubernetes-study

```bash
kubectl create -f deployments/frontend.yaml --save-config
kubectl create -f deployments/frontend.yaml --save-config --record # Essa flag record faz com que a revisão do rollout armazene as informações em CHANGE-CAUSE, como o último comando utilizado para criação, por exemplo.
kubectl get all
kubectl rollout status deployment/frontend-dp
kubectl delete deployments frontend-dp
kubectl rollout history deployment/frontend-dp
# Atualizando a versão da imagem do nosso container
kubectl set image deployment frontend-dp frontend-container=nginx:1.18 --record=true
# Fazendo rollback (desfaz a última alteração)
kubectl rollout undo deployment/frontend-dp
# Fazendo rollback para a revisão 1
kubectl rollout undo deployment/frontend-dp --to-revision=1
# Atualizando o número de réplicas
kubectl scale deployment/frontend-dp --replicas=10
```