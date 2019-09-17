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
