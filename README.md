# ArgoCD-Test
Created this repository to play with ArgoCD

1) Install ArgoCD on Kubernetes
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

2) Wait for the pods to come up. Use this to confirm.
kubectl get pod -n argocd

3) When the pods are up, port forward the argocd-server service to allow us access the ui.
  `` kubectl get svc -n argocd ``                          
```
NAME                                      TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)                      AGE
argocd-applicationset-controller          ClusterIP   10.98.24.143     <none>        7000/TCP,8080/TCP            8m13s
argocd-dex-server                         ClusterIP   10.97.52.46      <none>        5556/TCP,5557/TCP,5558/TCP   8m13s
argocd-metrics                            ClusterIP   10.100.71.94     <none>        8082/TCP                     8m13s
argocd-notifications-controller-metrics   ClusterIP   10.101.223.100   <none>        9001/TCP                     8m13s
argocd-redis                              ClusterIP   10.97.119.123    <none>        6379/TCP                     8m13s
argocd-repo-server                        ClusterIP   10.111.231.245   <none>        8081/TCP,8084/TCP            8m13s
argocd-server                             ClusterIP   10.105.121.128   <none>        80/TCP,443/TCP               8m13s
argocd-server-metrics                     ClusterIP   10.101.187.14    <none>        8083/TCP                     8m13s
```

To port forward, run the command below
```kubectl port-forward -n argocd svc/argocd-server 8080:443```
