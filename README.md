

```sh

➜  minikube kubectl apply -f echo.kube.yaml

deployment.apps/echo-deployment created
service/echo-service created
➜  minikube # Deployment 상태 확인
kubectl get deployments

# Pod 상태 확인
kubectl get pods

# Service 상태 확인
kubectl get svc
NAME                  READY   UP-TO-DATE   AVAILABLE   AGE
echo-deployment       2/2     2            2           13s
hello-minikube        1/1     1            1           38m
kubernetes-bootcamp   1/1     1            1           18m
NAME                                   READY   STATUS    RESTARTS   AGE
echo-deployment-64fdd4df8-k5k2c        1/1     Running   0          13s
echo-deployment-64fdd4df8-kmcz5        1/1     Running   0          13s
hello-minikube-59d4768566-t5m9x        1/1     Running   0          38m
kubernetes-bootcamp-855d5cc575-ctj7b   1/1     Running   0          18m
NAME             TYPE           CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
echo-service     LoadBalancer   10.101.195.10   <pending>     80:32735/TCP     13s
hello-minikube   NodePort       10.96.178.243   <none>        8080:30137/TCP   38m
kubernetes       ClusterIP      10.96.0.1       <none>        443/TCP          40m


kubectl expose deployment echo-deployment  --type=LoadBalancer --name=echo-deployment

kubectl expose pod [pod 이름] --type=Nodeport --port=포트번호


```


https://kim-dragon.tistory.com/52

https://nearhome.tistory.com/95

kubectl delete all --all

kubectl delete all --all --all-namespaces


https://velog.io/@pinion7/Kubernetes-%EB%A6%AC%EC%86%8C%EC%8A%A4-NodeSelector%EC%97%90-%EB%8C%80%ED%95%B4-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B3%A0-%EC%8B%A4%EC%8A%B5%ED%95%B4%EB%B3%B4%EA%B8%B0

https://hub.docker.com/r/ealen/echo-server# minikube-helloworld
