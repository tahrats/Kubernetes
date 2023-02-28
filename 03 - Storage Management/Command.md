kubectl apply -f 01 - MySQL-Volume.yml
kubectl delete -f 01 - MySQL-Volume.yml

kubectl get persistentvolume /or/ kubectl get pv
kubectl describe persistentvolume pv /or/ kubectl describe pv pv

kubectl apply -f pvc.yml
kubectl get persistentvolumeclaims /or/ kubectl get pvc
kubectl describe persistentvolumeclaims pvc /or/ kubectl describe pvc pvc

kubectl apply -f mysql-pv.yml
kubectl get pods 