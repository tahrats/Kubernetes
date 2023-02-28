apiVersion: v1
kind: Pod
metadata:
  name: simple-webapp-color
  labels:
    name: web
spec:
  containers:
  - name: web
    image: mmumshad/simple-webapp-color
    ports:
      - containerPort: 8080
    env:
      - name: APP_COLOR
        value: red


kubectl apply -f pod.yml
kubectl get pod
kubectl describe pod simple-webapp-color
kubectl port-forward simple-webapp-color 8080:8080 --address 0.0.0.0
kubectl delete -f pod.yml
kubectl get deploy
kubectl get replicaset
kubectl get deploy -o wide
kubectl get replicaset -o wide

Create manual
-----------------
kubectl run --image=mmumshad/simple-webapp-color \
--env="APP_COLOR=red" \
--restart=Never \
simple-webapp-color

kubectl port-forward simple-webapp-color 8080:8080 --address 0.0.0.0
kubectl delete pods simple-webapp-color

kubectl create deployment --image=nginx:1.18.0 nginx-deployment
kubectl scale --replicas=2 deployment/nginx-deployment
kubectl set image deployment/nginx-deployment nginx=nginx
