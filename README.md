# 超全面、超详细的Kubernetes视频教程，基于最新版K8s
https://ke.qq.com/course/2738602

# kubernetes-guide
《再也不踩坑的Kubernetes实战指南》代码及勘误

## 非常抱歉书中的错误给你带来的不便 QQ群：780043119

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

11. 86页，非级联删除第一行，空格丢失，应该是kubectl delete sts xxxx

12. 90页， 创建DaemonSet，第二段应该是nginx ingress，空格丢失。

13. 127页， 第4节更新Ingress， 应该是kubectl apply -f，空格丢失

14. 142页， 3.1.2标题为部署GFS集群

15. 156页，最上面空格丢失，helm fetch

16. 215页， docker项，docker run和docker pull 空格丢失，alwaysPull少了一个l

17. 255页，第二段第二行，最后一句是不同namespace

18. 257页，创建service的yaml的namespace是sc

19. 11页，master02配置，apiServerCertSANs，第一行是k8s-master01 

20. 书中标注开机内核加载可能有时候会不生效，可以采用如下方式
````
将需要加载的模块写入/etc/modules-load.d/ipvs.conf文件
cat /etc/modules-load.d/ipvs.conf 
ip_vs
ip_vs_rr
ip_vs_wrr
ip_vs_sh
nf_conntrack_ipv4
ip_tables
ip_set
xt_set
ipt_set
ipt_rpfilter
ipt_REJECT
ipip
然后执行systemctl enable --now systemd-modules-load.service即可
````
21. 5.6小结创建tls证书命令kubectl create secret tls ca-secret --key tls.key --cert tls.crt 

22. 二进制安装时，请注意更改haproxy的端口为8443

### 书中标注图片不清晰的，可以查看本网址的png
