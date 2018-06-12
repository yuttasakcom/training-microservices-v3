## Product service

```sh
# point your docker client to the VM's docker daemon
$ eval $(minikube docker-env)

$ npm run build

$ kubectl create -f ../k8s/user-secret.yml

$ kubectl create -f ../k8s/product-deployment.yml

$ kubectl get pods

$ kubectl expose deployment product-web --type=ClusterIP --port=3000
```

Access local machine from pod 
https://github.com/kubernetes/minikube/blob/master/docs/accessing_etcd.md

(db host: 10.0.2.15)

### Migrate db
```sh
$ eval $(minikube docker-env)

$ npm run db-start

$ kc exec user-web-67dd7f59c6-dv7vw -it sh

$ npm run db-migrate
```