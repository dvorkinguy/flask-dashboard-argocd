#### Guy

#### Create Cluster

mr.wolf@devops:njd-2007-argocd-app-config$ 

eksctl create cluster --name njd-2007-agrocd-app-config --version 1.27 --region us-west-2 -
-nodegroup-name njd-2007-agrocd-app-config --node-type t2.small --n
odes 3

------------
LENS
----------------
login

admin

k get secret argocd-initial-admin-secret -n argocd -o yaml

apiVersion: v1
data:
  password: SWE5************************
kind: Secret
metadata:
  creationTimestamp: "2023-07-20T19:37:03Z"
  name: argocd-initial-admin-secret
  namespace: argocd
  resourceVersion: "2565"
  uid: 901d4769-a8e7-4260-8894-a1780ae49f73
type: Opaque

--------------

echo SWE5************************ | base64 --decode





#### Commands

```bash
# install ArgoCD in k8s
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# access ArgoCD UI
kubectl get svc -n argocd
kubectl port-forward svc/argocd-server 8080:443 -n argocd

# login with admin user and below token (as in documentation):
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo

# you can change and delete init password

```
</br>

#### Links

* Config repo: [https://gitlab.com/nanuchi/argocd-app-config](https://gitlab.com/nanuchi/argocd-app-config)

* Docker repo: [https://hub.docker.com/repository/docker/nanajanashia/argocd-app](https://hub.docker.com/repository/docker/nanajanashia/argocd-app)

* Install ArgoCD: [https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd](https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd)

* Login to ArgoCD: [https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli](https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli)

* ArgoCD Configuration: [https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/](https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/)
