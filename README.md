# argoCD-apps-cnfgrtn
# first initiated the cluster in terminal
# create namespace as argoCD

kubectl create namespace argocd

# to install argoCD in the cluster by using the following command

kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/v2.2.3/manifests/install.yaml

# all argoCD services are type of CLUSTER IP so we not able to access it outside so for that we need to convert to LOADBALANCER

kubectl -n argocd edit service/argocd-server

# to see the services and all 

kubectl -n argocd get all

# for argoCD default user name is admin and password will get by using the following cmnd

kubectl -n argocd get secret -o yaml

# and encoded the secret by following cmnd
 
 echo 'value' | base64 --decode
 
