# ArgoCD-Test
Created this repository to play with ArgoCD

1) Install ArgoCD on Kubernetes
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

2) Wait for the pods to come up. Use this to confirm.
kubectl get pod -n argocd
