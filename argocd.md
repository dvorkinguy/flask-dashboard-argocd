https://www.youtube.com/watch?v=MeU5_k9ssrs&list=WL&index=13&t=1683s

# Lateast
https://github.com/argoproj/argo-cd/releases/tag/v2.7.8

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/core-install.yaml

https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli

kubectl get pods -n argocd -o wide
kubectl get svc -n argocd

argocd admin initial-password -n argocd
k get svc -n argocd

# Activate - Temp
k port-forward -n argocd svc/argocd-server 8080:443
# Activate - Constant
kubectl port-forward -n argocd svc/argocd-server 8080:443 &

https://127.0.0.1:8080/

# Login
admin

https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli


# Kill
ps aux | grep kubectl | grep "port-forward -n argocd svc/argocd-server"

# Password Extraction Tool
https://argo-cd.readthedocs.io/en/stable/cli_installation/

$ flask-dashboard-argocd
$ argocd admin initial-password -n argocd

****************
7fRVIsVE0qdyCnn0