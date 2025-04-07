## doc

https://argo-cd.readthedocs.io/en/stable/getting_started/

## Install Argo CD

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# after running above command, we see argo cd API available
kubectl api-versions           
...
argoproj.io/v1alpha1

## login

# get password for admin

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

kubectl port-forward svc/argocd-server -n argocd 8080:443

argocd login localhost:8080

# change password
argocd account update-password


