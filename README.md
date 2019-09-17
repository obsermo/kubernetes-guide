# kubernetes-guide
《再也不踩坑的Kubernetes实战指南》代码及勘误

### 《再也不踩坑的Kubernetes实战指南》勘误


1. 书中大写K8S均为小写k8s

2. 96-98页缩进错误，具体缩进可以参考

````
格式参考如下：
apiVersion: v1
kind: Pod
metadata:
  name: dapi-test-pod
spec:
  containers:
    - name: test-container
      image: busybox
      command: [ "/bin/sh", "-c", "env" ]
      env:
        # Define the environment variable
        - name: SPECIAL_LEVEL_KEY
          valueFrom:
            configMapKeyRef:
              # The ConfigMap containing the value you want to assign to SPECIAL_LEVEL_KEY
              name: special-config
              # Specify the key associated with the value
              key: special.how
  restartPolicy: Never

````


3. 99页创建Secret，命令行为kubectl，错写成了kubelet

4. 3页，第二段：会造成Etcd（存储Kubernetes信息的键-值数据库）同步不正常

5. 53页，显示Docker信息，命令docker info

6. 59页， 第二段空格丢失，应该是docker build -t

7. 62页， 什么是Pod第二行头一个单词Pod

8. 64-65页，创建Pod的模板缩进错误

9. 71页，创建deployment为kubectl create，查看deployment为kubectl get 和 kubectl describe，空格丢失

10. 82页，StatefulSet扩容和缩容第一行空格丢失，应该是kubectl scale 和 kubectl patch
