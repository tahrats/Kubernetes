Services:
NodePort = Utiliser pour l'extérieur = Expose à l'extérieur
ClusterIP = Utiliser pour l'intérieur
Loadbalancer = Vous devez être dans un cloud

*******************************

kubectl apply -f namespace.yml
kubectl get namespaces

kubectl apply -f pod-red.yml --namespace production /or/ kubectl apply -f pod-red.yml -n production
kubectl apply -f pod-blue.yml -n production

kubectl get pods -n production

kubectl apply -f service-nodeport-web.yml -n production
kubectl get service -n production /or/ kubectl get svc -n production
kubectl -n production describe svc service-nodeport-web
