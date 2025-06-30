# start

# Instalar Argo CD
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# Ver Argo CD rodando
kubectl get pods -n argocd

# Expor UI localmente
kubectl port-forward svc/argocd-server -n argocd 8080:443

# Pega senha (user: admin)
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d
