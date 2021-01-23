
#Habilitar addons  ingress
minikube addons enable ingress

#Aplicar los deploys de 01 al 05
kubectl  apply -f 01-hello-app-deployment-v1.yaml
kubectl  apply -f 02-hello-app-deployment-v2.yaml 
kubectl  apply -f 03-hello-svc-v1.yaml 
kubectl  apply -f 04-hello-svc-v2.yaml 
kubectl  apply -f 05-ingress.yaml 

#Obtener ingress y setear el  host con la direccion IP en el /etc/hosts
kubectl  get ing
OUTPUT:
NAME              CLASS    HOSTS                                     ADDRESS        PORTS   AGE
example-ingress   <none>   v1.hello-world.info,v2.hello-world.info   192.168.49.2   80      36s



#Realizar peticion via curl

curl v1.hello-world.info
OUTPUT:
Hello, world!
Version: 1.0.0
Hostname: hello-v1-5bd6f947bb-9n9fq


curl v2.hello-world.info
OUTPUT:
Hello, world!
Version: 2.0.0
Hostname: hello-v2-6db4bdfb96-t2qvk

