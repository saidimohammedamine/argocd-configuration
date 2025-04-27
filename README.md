# argocd-configuration


Step #1:Install and setup ArgoCD

Now lets open another duplicate tab. Create a new namespace called argocd in your Kubernetes cluster.

     kubectl create namespace argocd
     
-Install ArgoCD in the argocd namespace by applying the YAML file from the provided URL.

     kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

-List all the resources in the argocd namespace. It provides an overview of the ArgoCD setup includes Pods, Services, Deployments, ReplicaSets, and more.

     kubectl -n argocd get all

-Now to login into argocd web : username ---> admin 
                                password ---> kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d
