#Aplicar los siguientes deployments
kubectl apply -f 00-namespaces.yaml
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
kubectl get pods -n argocd


#En otra terminal generar el port-forward
kubectl port-forward svc/argocd-server -n argocd 8080:443


#Obtener password de argocd-server
kubectl get pods -n argocd -l app.kubernetes.io/name=argocd-server -o name | cut -d'/' -f 2
OUTPUT: argocd-server-5d7d9b7f9c-85mrw

#Acceder a la URL
https://localhost:8080/
user: admin
password: (OUTPUT_POD)

 

