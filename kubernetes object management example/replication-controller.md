```
// replication_controller_simple.yaml
apiVersion: v1
kind: ReplicationController
metadata:
  name: replication-controller-runs-pod
spec:
  replicas: 3
  selector:
    app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.19.0
```

```
// 创建 replication controller
kubectl create -f <replication controller 配置yaml文件>
eg. kubectl create -f replication_controller_simple.yaml

// 查看 replication controller
kubectl get replicationcontrollers

// 查看 replication controller 详细信息
kubectl describe replicationcontrollers <replication controller name>
eg. kubectl describe replicationcontrollers replication-controller-runs-pod

// 修改yaml配置文件 重新生效
kubectl apply -f <replication controller 配置yaml文件>
eg. kubectl apply -f replication_controller_simple.yaml

// 删除replication controller
kubectl delete -f <replication controller 配置yaml文件>
eg. kubectl delete -f replication_controller_simple.yaml
```

