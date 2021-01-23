
#Habilitar addons  ingress
minikube addons enable ingress

#Aplicar los deploys de 01 al 05
kubectl  apply -f 01-hello-app-deployment-v1.yaml
kubectl  apply -f 02-hello-app-deployment-v2.yaml 
kubectl  apply -f 03-hello-svc-v1.yaml 
kubectl  apply -f 04-hello-svc-v2.yaml 
kubectl  apply -f 05-ingress.yaml 



