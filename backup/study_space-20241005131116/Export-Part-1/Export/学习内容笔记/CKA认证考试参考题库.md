# CKA认证考试参考题库

![https://www.notion.so./【CKA认证考试参考题库及万字详解】_cka题库-CSDN博客_files/20201124032511.png](https://www.notion.so./【CKA认证考试参考题库及万字详解】_cka题库-CSDN博客_files/20201124032511.png)

![https://www.notion.so./【CKA认证考试参考题库及万字详解】_cka题库-CSDN博客_files/20210918025138.gif](https://www.notion.so./【CKA认证考试参考题库及万字详解】_cka题库-CSDN博客_files/20210918025138.gif)

[data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHN0eWxlPSJkaXNwbGF5OiBub25lOyI+CiAgICAgICAgICAgICAgICAgICAgICAgIDxwYXRoIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0iTTUsMCAwLDIuNSA1LDV6IiBpZD0icmFwaGFlbC1tYXJrZXItYmxvY2siIHN0eWxlPSItd2Via2l0LXRhcC1oaWdobGlnaHQtY29sb3I6IHJnYmEoMCwgMCwgMCwgMCk7IiAvPgogICAgICAgICAgICAgICAgICAgIDwvc3ZnPg==](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHN0eWxlPSJkaXNwbGF5OiBub25lOyI+CiAgICAgICAgICAgICAgICAgICAgICAgIDxwYXRoIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgZD0iTTUsMCAwLDIuNSA1LDV6IiBpZD0icmFwaGFlbC1tYXJrZXItYmxvY2siIHN0eWxlPSItd2Via2l0LXRhcC1oaWdobGlnaHQtY29sb3I6IHJnYmEoMCwgMCwgMCwgMCk7IiAvPgogICAgICAgICAgICAgICAgICAgIDwvc3ZnPg==)

# 目录

【CKA认证考试参考题库及详解】

# 说明

1. 考试前，提前 30 分钟点击“启动考试”，按照要求下载安装最新的“PSI 安全浏览器"，进入考试后，按照提示拍摄个人身份信息，摄像头环绕房间四周和桌面桌底，让考官确认考试环境是否符合考试要求；
2. 考试时，账户可能是student，或者candidate，且是在非master节点，均无root权限；
3. 考试时，每道题目会给一个参考链接，链接未必准确且网络较卡，建议平时练习最好习惯使用-h, 而不是参考[Kubernetes官网链接](https://kubernetes.io/)，记住，实操多练才是王道，，另外，考试时间尽量安排在中国大陆的非工作时间；（附上：[科@学@上@网@教@程](https://www.speeder.one/auth/register?code=Oolb)）
4. 考试时，如果涉及到复制粘贴强烈建议使用鼠标右键或者常规操作加上shift键，，另外，从官网复制YAML文件，在vim之后一定记得输入`:set paste`，避免格式错乱，多一个空格少一个空格都会报错；
5. 本题库仅为参考，不保证与真题有较高相似度，变量（Key）大概率类似，参数（Value）大概率不同，考试时请注意仔细审题；（如有雷同，纯属巧合！！！）
6. 本题库，主要是基于Kubernetes V1.28版本，其他Kubernetes版本，需要根据版本做相应调整；
7. 对于 CKA 考试，分数必须达到 66% 或以上才能通过，即及格分为66分，一般考完试24小时内出成绩（邮件通知）；
8. 注意事项：在开始做每道题之前，注意审题是否需要切换配置环境（`kubectl config use-context xxx`），只有极个别题目（ETCD那道题）不用，切记！！！否则题目白做；（即：考生完成每道题目后，必须返回基本节点）

# 题库总结

提示：本次的题库总结表格是按照“分值从高到低”和“难度从易到难”的逻辑进行排序，供各位朋友参考。

| 序号 | 考点 | 分值权重（%） | 难易程度 | 备注 |
| --- | --- | --- | --- | --- |
| 1 | **节点排障** | 13 | 低 | 先`systemctl start kubelet`后`systemctl start kubelet` |
| 2 | 服务暴露 | 7 | 低 | `kubectl edit XXX`和`kubectl expose XXX` |
| 3 | 创建Ingress | 7 | 中 | 需要复制粘贴官网的service/networking/minimal-ingress.yaml文件—— [Kubernetes Documentation](https://kubernetes.io/docs/) [Concepts](https://kubernetes.io/docs/concepts/) [Services, Load Balancing, and Networking](https://kubernetes.io/docs/concepts/services-networking/) [Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/)
官网搜索关键词：minimal-ingress.yaml |
| 4 | Network Policy | 7 | 中 | 需要复制粘贴官网的service/networking/networkpolicy.yaml文件—— [Kubernetes Documentation](https://kubernetes.io/docs/) [Concepts](https://kubernetes.io/docs/concepts/) [Services, Load Balancing, and Networking](https://kubernetes.io/docs/concepts/services-networking/) [Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/)
官网搜索关键词：networkpolicy.yaml |
| 5 | PVC | 7 | 中 | 需要复制粘贴官网的pods/storage/pv-claim.yaml文件和pods/storage/pv-pod.yaml文件—— [Kubernetes Documentation](https://kubernetes.io/docs/) [Tasks](https://kubernetes.io/docs/tasks/) [Configure Pods and Containers](https://kubernetes.io/docs/tasks/configure-pod-container/) [Configure a Pod to Use a PersistentVolume for Storage](https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/)
官网搜索关键词：pv-claim.yaml和pv-pod.yaml |
| 6 | Sidecar日志体系 | 7 | 中 | 先delete已有Pod后apply
官网搜索关键词：streaming-sidecar.yaml |
| 7 | ETCD的备份与恢复 | 7 | **高** | 注意：本题不需要切换环境，直接操作即可，但是需要在master上操作；使用命令：`etcdctl snapshot save`和`sudo etcdctl snapshot restore`等
官网搜索关键词：etcd cluster |
| 8 | Kubernetes集群版本升级 | 7 | **高** | 注意：部分步骤需要在master上操作，使用命令`apt-get upgrade XXX`和`apt-get install XXX`，注意题目要求的哪些组件不用升级
官网搜索关键词：`upgrade kubeadm clusters` |
| 9 | Pod日志 | 5 | 低 | `kubectl logs XXX` |
| 10 | Pod监控 | 5 | 低 | `kubectl top pod -h [-A]` |
| 11 | 节点维护 | 4 | 低 | `kubectl drain -h` |
| 12 | 节点污点 | 4 | 低 | `kubectl describe nodes` |
| 13 | NodeSelector | 4 | 低 | `kubectl run <pod_name> --image=nginx --dry-run=client -o yaml > pod-ssd.yaml` |
| 14 | Deployment的扩缩容 | 4 | 低 | `kubectl scale -h` |
| 15 | Pod内容器 | 4 | 低 | `vim <pod_name>.yaml` |
| 16 | PV | 4 | 中 | 复制粘贴官网的pods/storage/pv-volume.yaml文件—— [Kubernetes Documentation](https://kubernetes.io/docs/) [Tasks](https://kubernetes.io/docs/tasks/) [Configure Pods and Containers](https://kubernetes.io/docs/tasks/configure-pod-container/) [Configure a Pod to Use a PersistentVolume for Storage](https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/)
官网搜索关键词：pv-volume.yaml |
| 17 | RBAC | 4 | 中 | 注意区分是rolebinding还是clusterrolebinding |

# 第1题：节点排障

## 1. 分值权重：13%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context nk8s`

### 2.2 Context

无

### 2.3 Task

一台名为davidwatt-node02 的Kubernetes worker node处于NotReady状态，调查发生这种情况的原因，并采取相应措施将node恢复为Ready 状态，确保所做的任何修改永久有效。

提示：

- 可使用以下命令通过ssh 连接到故障node：[student@node01] $ `ssh davidwatt-node02`
- 可使用以下命令在该node上获取更高权限：[student@davidwatt-node02] $ `sudo -i`

## 3. 考点解析

节点排障

## 4. 考点参考链接

[使用 kubeadm 配置集群中的每个 kubelet](https://kubernetes.io/zh-cn/docs/setup/production-environment/tools/kubeadm/kubelet-integration/)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context nk8s
kubectl get nodes
ssh node02
sudo -i
systemctl start kubelet
systemctl enable kubelet
exit
exit
12345678
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context nk8s
kubectl get nodes
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
NAME       STATUS     ROLES           AGE    VERSION
master01   Ready      control-plane   239d   v1.28.0
node01     Ready      <none>          239d   v1.28.0
node02     NotReady   <none>          239d   v1.28.0
--------------------------------------------分割结束线-----------------------------------------------
ssh node02
sudo -i
systemctl status kubelet
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
● kubelet.service - kubelet: The Kubernetes Node Agent
     Loaded: loaded (/lib/systemd/system/kubelet.service; disabled; vendor preset: enabled)
    Drop-In: /etc/systemd/system/kubelet.service.d
             └─10-kubeadm.conf
     Active: inactive (dead) since Mon 2024-01-15 16:11:07 CST; 10min ago
       Docs: https://kubernetes.io/docs/home/
   Main PID: 1350 (code=exited, status=0/SUCCESS)

Jan 15 16:09:16 node02 kubelet[1350]: E0115 16:09:16.110524    1350 dns.go:153] "Nameserver limits exceeded" err="Nameserver l>
Jan 15 16:09:19 node02 kubelet[1350]: E0115 16:09:19.109178    1350 dns.go:153] "Nameserver limits exceeded" err="Nameserver l>
Jan 15 16:09:35 node02 kubelet[1350]: E0115 16:09:35.109001    1350 dns.go:153] "Nameserver limits exceeded" err="Nameserver l>
Jan 15 16:10:20 node02 kubelet[1350]: E0115 16:10:20.109275    1350 dns.go:153] "Nameserver limits exceeded" err="Nameserver l>
Jan 15 16:10:27 node02 kubelet[1350]: E0115 16:10:27.109093    1350 dns.go:153] "Nameserver limits exceeded" err="Nameserver l>
Jan 15 16:10:41 node02 kubelet[1350]: E0115 16:10:41.110387    1350 dns.go:153] "Nameserver limits exceeded" err="Nameserver l>
Jan 15 16:11:07 node02 kubelet[1350]: I0115 16:11:07.633604    1350 dynamic_cafile_content.go:171] "Shutting down controller" >
Jan 15 16:11:07 node02 systemd[1]: Stopping kubelet: The Kubernetes Node Agent...
Jan 15 16:11:07 node02 systemd[1]: kubelet.service: Succeeded.
Jan 15 16:11:07 node02 systemd[1]: Stopped kubelet: The Kubernetes Node Agent.
--------------------------------------------分割结束线-----------------------------------------------
#注意：先start后enable；
systemctl start kubelet
systemctl enable kubelet
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
Created symlink /etc/systemd/system/multi-user.target.wants/kubelet.service → /lib/systemd/system/kubelet.service.
--------------------------------------------分割结束线-----------------------------------------------
systemctl status kubelet
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
 kubelet.service - kubelet: The Kubernetes Node Agent
     Loaded: loaded (/lib/systemd/system/kubelet.service; enabled; vendor preset: enabled)
    Drop-In: /etc/systemd/system/kubelet.service.d
             └─10-kubeadm.conf
     Active: active (running) since Mon 2024-01-15 16:25:14 CST; 47s ago
       Docs: https://kubernetes.io/docs/home/
   Main PID: 17579 (kubelet)
      Tasks: 13 (limit: 2530)
     Memory: 40.9M
     CGroup: /system.slice/kubelet.service
             └─17579 /usr/bin/kubelet --bootstrap-kubeconfig=/etc/kubernetes/bootstrap-kubelet.conf --kubeconfig=/etc/kubernet>

Jan 15 16:25:23 node02 kubelet[17579]: I0115 16:25:23.679137   17579 reconciler_common.go:172] "operationExecutor.UnmountVolum>
Jan 15 16:25:23 node02 kubelet[17579]: I0115 16:25:23.679922   17579 reconciler_common.go:172] "operationExecutor.UnmountVolum>
Jan 15 16:25:23 node02 kubelet[17579]: I0115 16:25:23.681977   17579 operation_generator.go:878] UnmountVolume.TearDown succee>
Jan 15 16:25:23 node02 kubelet[17579]: I0115 16:25:23.707338   17579 operation_generator.go:878] UnmountVolume.TearDown succee>
Jan 15 16:25:23 node02 kubelet[17579]: I0115 16:25:23.781812   17579 reconciler_common.go:300] "Volume detached for volume \"k>
Jan 15 16:25:23 node02 kubelet[17579]: I0115 16:25:23.781860   17579 reconciler_common.go:300] "Volume detached for volume \"c>
Jan 15 16:25:24 node02 kubelet[17579]: I0115 16:25:24.897751   17579 kubelet_volumes.go:161] "Cleaned up orphaned pod volumes >
Jan 15 16:25:24 node02 kubelet[17579]: I0115 16:25:24.899980   17579 kubelet_volumes.go:161] "Cleaned up orphaned pod volumes >
Jan 15 16:25:24 node02 kubelet[17579]: I0115 16:25:24.900907   17579 kubelet_volumes.go:161] "Cleaned up orphaned pod volumes >
Jan 15 16:25:24 node02 kubelet[17579]: I0115 16:25:24.901948   17579 kubelet_volumes.go:161] "Cleaned up orphaned pod volumes >
--------------------------------------------分割结束线-----------------------------------------------
#退出root权限
root@node02:~# exit
logout
#退出node02
student@node02:~$ exit
logout
Connection to node02 closed.
12345678910111213141516171819202122232425262728293031323334353637383940414243444546474849505152535455565758596061626364656667686970717273
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
kubectl get nodes
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
NAME       STATUS   ROLES           AGE    VERSION
master01   Ready    control-plane   239d   v1.28.0
node01     Ready    <none>          239d   v1.28.0
node02     Ready    <none>          239d   v1.28.0
--------------------------------------------分割结束线-----------------------------------------------
123456789
```

# 第2题：服务暴露

## 1. 分值权重：7%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context sk8s`

### 2.2 Context

无

### 2.3 Task

请重新配置现有的deployment front-end以及添加名为http的端口规范来公开现有容器nginx的端口80/tcp。

创建一个名为front-end-svc的新服务，以公开容器端口http。

配置此服务，以通过服务所在节点上的NodePort来公开这些服务。

## 3. 考点解析

本题主要考查：以Nodeport的方式向外暴露服务

注意：

（1）deployment和svc的SELECTOR一定要保持一致；

（2）注意考试中需要创建的是 NodePort，还是 ClusterIP，如果是 ClusterIP，则应为–type=ClusterIP

（3）–port 是 service 的端口号，–target-port 是pod 里容器的端口号。

## 4. 考点参考链接

[Deployment](https://kubernetes.io/zh-cn/docs/concepts/workloads/controllers/deployment/)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context sk8s
kubectl edit deployments front-end
...
    spec:
      containers:
      - image: davidwatt/nginx:hello
        imagePullPolicy: IfNotPresent
        name: nginx
        #下面四行是需要新增的，注意containerPort中间的p需要大写、TCP需要大写、name为http必须要写；
        ports:
        - containerPort: 80
          name: http
          protocol: TCP
...
kubectl expose deployment front-end --name=front-end-svc --type=NodePort --port=80 --target-port=80
123456789101112131415
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context sk8s
kubectl get deployments front-end -o wide
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
NAME        READY   UP-TO-DATE   AVAILABLE   AGE    CONTAINERS   IMAGES              SELECTOR
front-end   1/1     1            1           239d   nginx        vicuu/nginx:hello   app=front-end
--------------------------------------------分割结束线----------------------------------------------
kubectl edit deployments front-end
#编辑Deployment front-end的yaml文件
    spec:
      containers:
      - image: davidwatt/nginx:hello
        imagePullPolicy: IfNotPresent
        name: nginx
        #下面四行是需要新增的，注意containerPort中间的p需要大写、TCP需要大写、name为http必须要写；
        ports:
        - containerPort: 80
          name: http
          protocol: TCP
...
kubectl expose -h
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Expose a resource as a new Kubernetes service.

 Looks up a deployment, service, replica set, replication controller or pod by name and uses the selector for that resource as the selector for a new service on the specified port. A deployment or replica set will be exposed as a service only if its selector is convertible to a selector that service supports, i.e. when the selector contains only the matchLabels component. Note that if no port is specified via --port and the exposed resource has multiple ports, all will be re-used by the new service. Also if no labels are specified, the new service will re-use the labels from the resource it exposes.

 Possible resources include (case insensitive):

 pod (po), service (svc), replicationcontroller (rc), deployment (deploy), replicaset (rs)

Examples:
  # Create a service for a replicated nginx, which serves on port 80 and connects to the containers on port 8000
  kubectl expose rc nginx --port=80 --target-port=8000

  # Create a service for a replication controller identified by type and name specified in "nginx-controller.yaml",
which serves on port 80 and connects to the containers on port 8000
  kubectl expose -f nginx-controller.yaml --port=80 --target-port=8000

  # Create a service for a pod valid-pod, which serves on port 444 with the name "frontend"
  kubectl expose pod valid-pod --port=444 --name=frontend

  # Create a second service based on the above service, exposing the container port 8443 as port 443 with the name "nginx-https"
  kubectl expose service nginx --port=443 --target-port=8443 --name=nginx-https

  # Create a service for a replicated streaming application on port 4100 balancing UDP traffic and named 'video-stream'.
  kubectl expose rc streamer --port=4100 --protocol=UDP --name=video-stream

  # Create a service for a replicated nginx using replica set, which serves on port 80 and connects to the containers on port 8000
  kubectl expose rs nginx --port=80 --target-port=8000

  # Create a service for an nginx deployment, which serves on port 80 and connects to the containers on port 8000 kubectl expose deployment nginx --port=80 --target-port=8000

Options:
    --allow-missing-template-keys=true:
        If true, ignore any errors in templates when a field or map key is missing in the template. Only applies to golang and jsonpath output formats.

    --cluster-ip='':
        ClusterIP to be assigned to the service. Leave empty to auto-allocate, or set to 'None' to create a headless service.

    --dry-run='none':
        Must be "none", "server", or "client". If client strategy, only print the object that would be sent, without sending it. If server strategy, submit server-side request without persisting the resource.

    --external-ip='':
        Additional external IP address (not managed by Kubernetes) to accept for the service. If this IP is routed to a node, the service can be accessed by this IP in addition to its generated service IP.

    --field-manager='kubectl-expose':
        Name of the manager used to track field ownership.

    -f, --filename=[]:
        Filename, directory, or URL to files identifying the resource to expose a service

    -k, --kustomize='':
        Process the kustomization directory. This flag can't be used together with -f or -R.

    -l, --labels='':
        Labels to apply to the service created by this call.

    --load-balancer-ip='':
        IP to assign to the LoadBalancer. If empty, an ephemeral IP will be created and used (cloud-provider specific).

    --name='':
        The name for the newly created object.

    -o, --output='':
        Output format. One of: (json, yaml, name, go-template, go-template-file, template, templatefile, jsonpath, jsonpath-as-json, jsonpath-file).

    --override-type='merge':
        The method used to override the generated object: json, merge, or strategic.

    --overrides='':
        An inline JSON override for the generated object. If this is non-empty, it is used to override the generated object. Requires that the object supply a valid apiVersion field.

    --port='':
        The port that the service should serve on. Copied from the resource being exposed, if unspecified

    --protocol='':
        The network protocol for the service to be created. Default is 'TCP'.

    -R, --recursive=false:
        Process the directory used in -f, --filename recursively. Useful when you want to manage related manifests organized within the same directory.

    --save-config=false:
        If true, the configuration of current object will be saved in its annotation. Otherwise, the annotation will be unchanged. This flag is useful when you want to perform kubectl apply on this object in the future.

    --selector='':
        A label selector to use for this service. Only equality-based selector requirements are supported. If empty (the default) infer the selector from the replication controller or replica set.)

    --session-affinity='':
        If non-empty, set the session affinity for the service to this; legal values: 'None', 'ClientIP'

    --show-managed-fields=false:
        If true, keep the managedFields when printing objects in JSON or YAML format.

    --target-port='':
        Name or number for the port on the container that the service should direct traffic to. Optional.

    --template='':
        Template string or path to template file to use when -o=go-template, -o=go-template-file. The template format is golang templates [http://golang.org/pkg/text/template/#pkg-overview].

    --type='':
        Type for this service: ClusterIP, NodePort, LoadBalancer, or ExternalName. Default is 'ClusterIP'.

Usage:
  kubectl expose (-f FILENAME | TYPE NAME) [--port=port] [--protocol=TCP|UDP|SCTP] [--target-port=number-or-name] [--name=name] [--external-ip=external-ip-of-service] [--type=type] [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
--------------------------------------------分割结束线----------------------------------------------
#向集群外暴露deployment，并定义名称、类型、端口和容器端口等；
kubectl expose deployment front-end --name=front-end-svc --type=NodePort --port=80 --target-port=80
#查看svc的SELECTOR是否和deployment的一致；
kubectl get svc front-end-svc -o wide
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
NAME            TYPE       CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE   SELECTOR
front-end-svc   NodePort   10.111.156.201   <none>        80:32395/TCP   14s   app=front-end
--------------------------------------------分割结束线----------------------------------------------
#如果不一致，则需要编辑svc使其保持一致；
kubectl edit svc front-end-svc
#如下所示：
spec:
  clusterIP: 10.111.156.201
  clusterIPs:
  - 10.111.156.201
  externalTrafficPolicy: Cluster
  internalTrafficPolicy: Cluster
  ipFamilies:
  - IPv4
  ipFamilyPolicy: SingleStack
  ports:
  - nodePort: 32395
    port: 80
    protocol: TCP
    targetPort: 80
#需要添加下面两行内容，与ports保持相同空格数；
  selector:
    app: front-end
...
kubectl get pod,svc -o wide
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
NAME                                READY   STATUS    RESTARTS       AGE     IP               NODE     NOMINATED NODE   READINESS GATES
pod/11-factor-app                   1/1     Running   6 (101m ago)   239d    10.244.196.181   node01   <none>           <none>
pod/foo                             1/1     Running   6 (101m ago)   239d    10.244.196.180   node01   <none>           <none>
pod/front-end-55f9bb474b-w2gd2      1/1     Running   0              8m50s   10.244.140.70    node02   <none>           <none>
pod/presentation-856b8578cd-ql27b   1/1     Running   0              75m     10.244.196.187   node01   <none>           <none>

NAME                    TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE     SELECTOR
service/front-end-svc   NodePort    10.111.156.201   <none>        80:32395/TCP   2m45s   app=front-end
service/kubernetes      ClusterIP   10.96.0.1        <none>        443/TCP        239d    <none>

--------------------------------------------分割结束线----------------------------------------------
123456789101112131415161718192021222324252627282930313233343536373839404142434445464748495051525354555657585960616263646566676869707172737475767778798081828384858687888990919293949596979899100101102103104105106107108109110111112113114115116117118119120121122123124125126127128129130131132133134135136137138139140141142143144145146147148149150151152153154155156157158159160161162163164165166167168169170171172
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
student@node01:~$ curl node02:32395 #这里的32395是Node端口；
Hello World
student@node01:~$ curl 10.111.156.201:80 #这里的80是Pod端口；
Hello World
12345
```

# 第3题：创建Ingress

## 1. 分值权重：7%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context ik8s`

### 2.2 Context

无

### 2.3 Task

按照如下要求，创建一个新的nginx Ingress 资源:

名称: ingress-demo

Namespace: ing-internal

使用服务端口：5678

在路径/hello. 上公开服务hello

可以使用以下命令检查服务hello 的可用性，该命令应返回hello：curl -kL <INTERNAL_ IP>/hello

## 3. 考点解析

创建Ingress

> -kL 用于使 curl 在执行请求时不进行 SSL 证书验证（-k），并跟随重定向（-L）。这通常在处理使用自签名证书的 HTTPS URL 或需要遵循重定向以获取最终内容时使用。
> 

## 4. 考点参考链接

[Ingress](https://kubernetes.io/zh-cn/docs/concepts/services-networking/ingress/)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context ik8s
vim ingress.yaml
...
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
#ingress的名称需要由原先的minimal-ingress修改为ingress-demo;
  name: ingress-demo
  #关键子步骤：新增命名空间，并按照要求写为ing-internal;
  namespace: ing-internal
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  ingressClassName: nginx
  rules:
  - http:
      paths:
      - path: /hello #路径需要由原先的/testpath修改为/hello
        pathType: Prefix
        backend:
          service:
            name: hello #服务名需要由原先的test修改为hello
            port:
              number: 5678 #端口需要由原先的80修改为5678
...
kubectl apply -f ingress.yaml
1234567891011121314151617181920212223242526
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context ik8s
vim ingress.yaml
#复制粘贴官网的service/networking/minimal-ingress.yaml文件，按照题目要求进行编辑修改
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
#ingress的名称需要由原先的minimal-ingress修改为ingress-demo;
  name: ingress-demo
  #关键子步骤：新增命名空间，并按照要求写为ing-internal;
  namespace: ing-internal
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  ingressClassName: nginx
  rules:
  - http:
      paths:
      - path: /hello #路径需要由原先的/testpath修改为/hello
        pathType: Prefix
        backend:
          service:
            name: hello #服务名需要由原先的test修改为hello
            port:
              number: 5678 #端口需要由原先的80修改为5678
...
kubectl apply -f ingress.yaml
kubectl get ingress -n ing-internal
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
NAME           CLASS   HOSTS   ADDRESS   PORTS   AGE
ingress-demo   nginx   *                 80      38s
--------------------------------------------分割结束线-----------------------------------------------
#需要等待5分钟左右，再次操作才能看到ingress的IP
kubectl get ingress -n ing-internal
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
NAME           CLASS   HOSTS   ADDRESS          PORTS   AGE
ingress-demo   nginx   *       10.105.186.107   80      9m17s
--------------------------------------------分割结束线-----------------------------------------------
123456789101112131415161718192021222324252627282930313233343536373839
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
curl ingress的IP地址/hello
curl 10.105.186.107/hello
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
Hello World
--------------------------------------------分割结束线-----------------------------------------------
1234567
```

# 第4题：NetworkPolicy

## 1. 分值权重：7%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context nk8s`

### 2.2 Context

无

### 2.3 Task

在现有的namespace my-app中创建一个名为allow-port-from-namespace 的新NetworkPolicy 。

确保新的NetworkPolicy 允许namespace echo中的Pods连接到namespace my-app中的端口8080 。

进一步确保新的 NetworkPolicy :

- 不允许对没有在监听端口8080的Pods的访问
- 不允午不来自namespace echo中的Pods的访问

## 3. 考点解析

配置Network Policy

注意：NetworkPolicy所在的命名空间；注意哪个ns是访问者，哪个ns是被访问者，以确定使用ingress还是egress，别搞错了！！！

## 4. 考点参考链接

[网络策略](https://kubernetes.io/zh-cn/docs/concepts/services-networking/network-policies/)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context nk8s
vim networkpolicy.yaml
#复制粘贴官网的service/networking/networkpolicy.yaml文件，按照题目要求进行编辑修改
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
#NetworkPolicy的名称需要由原先的test-network-policy修改为allow-port-from-namespace;
  name: allow-port-from-namespace
  #namespace需要由原先的default修改为my-app;
  namespace: my-app
spec:
  podSelector:
    matchLabels: {}
  policyTypes:
    - Ingress
  ingress:
    - from:
        - namespaceSelector:
            matchLabels:
              project: echo #project需要由原先的myproject修改为echo;
      ports:
        - protocol: TCP
          port: 8080 #port需要由原先的6379修改为8080;
...
kubectl apply -f networkpolicy.yaml
12345678910111213141516171819202122232425
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context nk8s
kubectl get ns --show-labels
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
NAME               STATUS   AGE    LABELS
app-team1          Active   248d   kubernetes.io/metadata.name=app-team1
calico-apiserver   Active   248d   kubernetes.io/metadata.name=calico-apiserver,name=calico-apiserver,pod-security.kubernetes.io/enforce-version=latest,pod-security.kubernetes.io/enforce=privileged
calico-system      Active   248d   kubernetes.io/metadata.name=calico-system,name=calico-system,pod-security.kubernetes.io/enforce-version=latest,pod-security.kubernetes.io/enforce=privileged
cpu-top            Active   248d   kubernetes.io/metadata.name=cpu-top
default            Active   248d   kubernetes.io/metadata.name=default
echo               Active   248d   kubernetes.io/metadata.name=echo
ing-internal       Active   248d   kubernetes.io/metadata.name=ing-internal
ingress-nginx      Active   248d   kubernetes.io/metadata.name=ingress-nginx
internal           Active   248d   kubernetes.io/metadata.name=internal
kube-node-lease    Active   248d   kubernetes.io/metadata.name=kube-node-lease
kube-public        Active   248d   kubernetes.io/metadata.name=kube-public
kube-system        Active   248d   kubernetes.io/metadata.name=kube-system
my-app             Active   248d   kubernetes.io/metadata.name=my-app
tigera-operator    Active   248d   kubernetes.io/metadata.name=tigera-operator,name=tigera-operator
--------------------------------------------分割结束线-----------------------------------------------
#给访问者的命名空间打上标签：
kubectl label namespace echo project=echo
vim networkpolicy.yaml
#复制粘贴官网的service/networking/networkpolicy.yaml文件，按照题目要求进行编辑修改
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
#NetworkPolicy的名称需要由原先的test-network-policy修改为allow-port-from-namespace;
  name: allow-port-from-namespace
  #namespace需要由原先的default修改为my-app;
  namespace: my-app
spec:
  podSelector:
    matchLabels: {}
  policyTypes:
    - Ingress
  ingress:
    - from:
        - namespaceSelector:
            matchLabels:
              project: echo #project需要由原先的myproject修改为echo;
      ports:
        - protocol: TCP
          port: 8080 #port需要由原先的6379修改为8080;
...
kubectl apply -f networkpolicy.yaml
networkpolicy.networking.k8s.io/allow-port-from-namespace created
1234567891011121314151617181920212223242526272829303132333435363738394041424344454647
```

### 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
kubectl describe networkpolicy -n my-app
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
Name:         allow-port-from-namespace
Namespace:    my-app
Created on:   2024-01-16 12:24:27 +0800 CST
Labels:       <none>
Annotations:  <none>
Spec:
  PodSelector:     <none> (Allowing the specific traffic to all pods in this namespace)
  Allowing ingress traffic:
    To Port: 8080/TCP
    From:
      NamespaceSelector: project=echo
  Not affecting egress traffic
  Policy Types: Ingress
--------------------------------------------分割结束线-----------------------------------------------
123456789101112131415161718
```

# 第5题：PVC

## 1. 分值权重：7%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context pvk8s`

### 2.2 Context

无

### 2.3 Task

创建一个新的PersistentVolumeClaim ;

- 名称: pv-volume
- Class: csi-hostpath-sc
- 容量: 10Mi

创建一个新的Pod, 并将上面新创建的PersistentVolumeClaim挂载到此Pod:

- 名称: davidwatt-web-server
- Image: nginx:1.16
- 挂载路径: /usr/share/nginx/html

配置新的pod，以对volume具有ReadWriteOnce权限。

最后，使用kubectl edit 或kubectl patch将PersistentVolumeClaim的容量扩展为100Mi，并记录此更改。

## 3. 考点解析

PVC的创建

其他考点：

（1）accessModes，存在多种模式，如ReadWriteMany 和 ReadOnlyMany 和 ReadWriteOnce，根据题目要求修改即可；

（2）如果用户关心对资源的每一次修改进行详细记录，包括修改的时间、执行修改的用户等信息，可以使用 `--record` 选项。如果只是希望保存当前配置而不需要详细的修改历史，可以使用 `--save-config` 选项。

（3）注意：Pod—>Spec中volumes的name和volumeMounts的那么一定要保持一致；

## 4. 考点参考链接

[配置 Pod 以使用 PersistentVolume 作为存储](https://kubernetes.io/zh-cn/docs/tasks/configure-pod-container/configure-persistent-volume-storage/)

## 5. 操作命令和结果 ##

### 5.1 必背操作命令

```
kubectl config use- context pvk8s
vim pv-claim.yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pv-volume #PersistentVolumeClaim的名称需要由原先的task-pv-claim修改为pv-volume;
spec:
  storageClassName: csi-hostpath-sc #SC的名称需要由原先的manual修改为csi-hostpath-sc;
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 10Mi #存储容量大小需要由原先的3Gi修改为10Mi;
...
kubectl apply -f pv-claim.yaml
vim pv-pod.yaml
apiVersion: v1
kind: Pod
metadata:
  name: davidwatt-web-server #Pod的名称需要由原先的task-pv-pod修改为davidwatt-web-server;
spec:
  volumes:
    - name: task-pv-storage
      persistentVolumeClaim:
        claimName: pv-volume #pvc的名称需要由原先的task-pv-claim修改为上面新建的pv-volume;
  containers:
    - name: davidwatt-web-server-container #这里的容器名称，建议跟pod保持一致;
      image: nginx:1.16 #镜像版本需要按照题目要求修改;
      volumeMounts:
        - mountPath: "/usr/share/nginx/html"
          name: task-pv-storage
...
kubectl apply -f pv-pod.yaml
kubectl edit pvc pv-volume --record
...
spec:
  accessModes:
  - ReadWriteOnce
  resources:
    requests:
      storage: 100Mi #注意只需要修改spec下面的Storage就行，status下面的Storage保持不变即可；
  storageClassName: csi-hostpath-sc
123456789101112131415161718192021222324252627282930313233343536373839404142
```

### 5.2 详细操作步骤和结果

```
kubectl config use- context pvk8s
vim pv-claim.yaml
#复制粘贴官网的pods/storage/pv-claim.yaml文件，按照题目要求进行编辑修改
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pv-volume #PersistentVolumeClaim的名称需要由原先的task-pv-claim修改为pv-volume;
spec:
  storageClassName: csi-hostpath-sc #SC的名称需要由原先的manual修改为csi-hostpath-sc;
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 10Mi #存储容量大小需要由原先的3Gi修改为10Mi;
...
kubectl apply -f pv-claim.yaml
kubectl get pvc
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
NAME        STATUS   VOLUME   CAPACITY   ACCESS MODES   STORAGECLASS      AGE
pv-volume   Bound    pv01     10Mi       RWO            csi-hostpath-sc   103s
--------------------------------------------分割结束线-----------------------------------------------
vim pv-pod.yaml
#复制粘贴官网的pods/storage/pv-pod.yaml文件，按照题目要求进行编辑修改
apiVersion: v1
kind: Pod
metadata:
  name: davidwatt-web-server #Pod的名称需要由原先的task-pv-pod修改为davidwatt-web-server;
spec:
  volumes:
    - name: task-pv-storage
      persistentVolumeClaim:
        claimName: pv-volume #pvc的名称需要由原先的task-pv-claim修改为上面新建的pv-volume;
  containers:
    - name: davidwatt-web-server-container #这里的容器名称，建议跟pod保持一致;
      image: nginx:1.16 #镜像版本需要按照题目要求修改;
      volumeMounts:
        - mountPath: "/usr/share/nginx/html"
          name: task-pv-storage
...
kubectl apply -f pv-pod.yaml
#扩容 PVC 容量
#方法1学习步骤
kubectl edit -h
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Edit a resource from the default editor.

 The edit command allows you to directly edit any API resource you can retrieve via the command-line tools. It will open the editor defined by your KUBE_EDITOR, or EDITOR environment variables, or fall back to 'vi' for Linux or 'notepad' for Windows. When attempting to open the editor, it will first attempt to use the shell that has been defined in the 'SHELL' environment variable. If this is not defined, the default shell will be used, which is '/bin/bash' for Linux or 'cmd' for Windows.

 You can edit multiple objects, although changes are applied one at a time. The command accepts file names as well as command-line arguments, although the files you point to must be previously saved versions of resources.
 Editing is done with the API version used to fetch the resource. To edit using a specific API version, fully-qualify the resource, version, and group.

 The default format is YAML. To edit in JSON, specify "-o json".

 The flag --windows-line-endings can be used to force Windows line endings, otherwise the default for your operating system will be used.

 In the event an error occurs while updating, a temporary file will be created on disk that contains your unapplied changes. The most common error when updating a resource is another editor changing the resource on the server. When this occurs, you will have to apply your changes to the newer version of the resource, or update your temporary saved copy to include the latest resource version.

Examples:
  # Edit the service named 'registry'
  kubectl edit svc/registry

  # Use an alternative editor
  KUBE_EDITOR="nano" kubectl edit svc/registry

  # Edit the job 'myjob' in JSON using the v1 API format
  kubectl edit job.v1.batch/myjob -o json

  # Edit the deployment 'mydeployment' in YAML and save the modified config in its annotation
  kubectl edit deployment/mydeployment -o yaml --save-config

  # Edit the 'status' subresource for the 'mydeployment' deployment
  kubectl edit deployment mydeployment --subresource='status'

Options:
    --allow-missing-template-keys=true:
        If true, ignore any errors in templates when a field or map key is missing in the template. Only applies to golang and jsonpath output formats.

    --field-manager='kubectl-edit':
        Name of the manager used to track field ownership.

    -f, --filename=[]:
        Filename, directory, or URL to files to use to edit the resource

    -k, --kustomize='':
        Process the kustomization directory. This flag can't be used together with -f or -R.

    -o, --output='':
        Output format. One of: (json, yaml, name, go-template, go-template-file, template, templatefile, jsonpath, jsonpath-as-json, jsonpath-file).

    --output-patch=false:
        Output the patch if the resource is edited.

    -R, --recursive=false:
        Process the directory used in -f, --filename recursively. Useful when you want to manage related manifests organized within the same directory.

    --save-config=false:
        If true, the configuration of current object will be saved in its annotation. Otherwise, the annotation will be unchanged. This flag is useful when you want to perform kubectl apply on this object in the future.

    --show-managed-fields=false:
        If true, keep the managedFields when printing objects in JSON or YAML format.

    --subresource='':
        If specified, edit will operate on the subresource of the requested object. Must be one of [status]. This flag is beta and may change in the future.

    --template='':
        Template string or path to template file to use when -o=go-template, -o=go-template-file. The template format is golang templates [http://golang.org/pkg/text/template/#pkg-overview].

    --validate='strict':
        Must be one of: strict (or true), warn, ignore (or false).              "true" or "strict" will use a schema to validate the input and fail the request if invalid. It will perform server side validation if ServerSideFieldValidation is enabled on the api-server, but will fall back to less reliable client-side validation if not.
        "warn" will warn about unknown or duplicate fields without blocking the request if server-side field validation is enabled on the API server, and behave as "ignore" otherwise.            "false" or "ignore" will not perform any schema validation, silently dropping any unknown or duplicate fields.

    --windows-line-endings=false:
        Defaults to the line ending native to your platform.

Usage:
  kubectl edit (RESOURCE/NAME | -f FILENAME) [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
--------------------------------------------分割结束线----------------------------------------------
#方法1核心步骤
kubectl edit pvc pv-volume --record
...
spec:
  accessModes:
  - ReadWriteOnce
  resources:
    requests:
      storage: 70Mi #注意只需要修改spec下面的Storage就行，status下面的Storage保持不变即可；
  storageClassName: csi-hostpath-sc
  ...
#方法2学习步骤
kubectl patch -h
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Update fields of a resource using strategic merge patch, a JSON merge patch, or a JSON patch.

 JSON and YAML formats are accepted.

 Note: Strategic merge patch is not supported for custom resources.

Examples:
  # Partially update a node using a strategic merge patch, specifying the patch as JSON
  kubectl patch node k8s-node-1 -p '{"spec":{"unschedulable":true}}'

  # Partially update a node using a strategic merge patch, specifying the patch as YAML
  kubectl patch node k8s-node-1 -p $'spec:\n unschedulable: true'

  # Partially update a node identified by the type and name specified in "node.json" using strategic merge patch
  kubectl patch -f node.json -p '{"spec":{"unschedulable":true}}'

  # Update a container's image; spec.containers[*].name is required because it's a merge key
  kubectl patch pod valid-pod -p '{"spec":{"containers":[{"name":"kubernetes-serve-hostname","image":"new image"}]}}'

  # Update a container's image using a JSON patch with positional arrays
  kubectl patch pod valid-pod --type='json' -p='[{"op": "replace", "path": "/spec/containers/0/image", "value":"new image"}]'

  # Update a deployment's replicas through the 'scale' subresource using a merge patch
  kubectl patch deployment nginx-deployment --subresource='scale' --type='merge' -p '{"spec":{"replicas":2}}'

Options:
    --allow-missing-template-keys=true:
        If true, ignore any errors in templates when a field or map key is missing in the template. Only applies to golang and jsonpath output formats.

    --dry-run='none':
        Must be "none", "server", or "client". If client strategy, only print the object that would be sent, without sending it. If server strategy, submit server-side request without persisting the resource.

    --field-manager='kubectl-patch':
        Name of the manager used to track field ownership.

    -f, --filename=[]:
        Filename, directory, or URL to files identifying the resource to update

    -k, --kustomize='':
        Process the kustomization directory. This flag can't be used together with -f or -R.

    --local=false:
        If true, patch will operate on the content of the file, not the server-side resource.

    -o, --output='':
        Output format. One of: (json, yaml, name, go-template, go-template-file, template, templatefile, jsonpath, jsonpath-as-json, jsonpath-file).

    -p, --patch='':
        The patch to be applied to the resource JSON file.

    --patch-file='':
        A file containing a patch to be applied to the resource.

    -R, --recursive=false:
        Process the directory used in -f, --filename recursively. Useful when you want to manage related manifests organized within the same directory.

    --show-managed-fields=false:
        If true, keep the managedFields when printing objects in JSON or YAML format.

    --subresource='':
        If specified, patch will operate on the subresource of the requested object. Must be one of [status scale].
        This flag is beta and may change in the future.

    --template='':
        Template string or path to template file to use when -o=go-template, -o=go-template-file. The template format is golang templates [http://golang.org/pkg/text/template/#pkg-overview].

    --type='strategic':
        The type of patch being provided; one of [json merge strategic]

Usage:
  kubectl patch (-f FILENAME | TYPE NAME) [-p PATCH|--patch-file FILE] [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
--------------------------------------------分割结束线----------------------------------------------
#方法2核心步骤
kubectl patch pvc pv-volume -p '{"spec":{"resources":{"requests":{"storage":"100Mi"}}}}'
123456789101112131415161718192021222324252627282930313233343536373839404142434445464748495051525354555657585960616263646566676869707172737475767778798081828384858687888990919293949596979899100101102103104105106107108109110111112113114115116117118119120121122123124125126127128129130131132133134135136137138139140141142143144145146147148149150151152153154155156157158159160161162163164165166167168169170171172173174175176177178179180181182183184185186187188189190191192193194195196197198199200201202203204205206207208209210211212
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
kubectl get pod davidwatt-web-server
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
NAME                   READY   STATUS    RESTARTS   AGE
davidwatt-web-server   1/1     Running   0          43s
--------------------------------------------分割结束线-----------------------------------------------
1234567
```

# 第6题：Sidecar日志体系

## 1. 分值权重：7%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context sk8s`

### 2.2 Context

将一个现有的Pod集成到Kubernetes的内置日志记录体系结构中(例如kubectl logs) ，添加streaming sidecar容器是实现此要求的一种好方法。

### 2.3 Task

使用busybox Image来将名为sidecar的sidecar容器添加到现有的Pod legacy-app 中。新的sidecar容器必须运行以下命令：`/bin/sh -c tail -n+1 -f /var/log/legacy-app.log`

使用挂载在/var/log的Volume，使日志文件legacy-app.log可用于sidecar容器。

除了添加所需的volume mount以外，请勿更改现有容器的规格。

## 3. 考点解析

Pod的两个container共享存储卷

## 4. 考点参考链接

[日志架构](https://kubernetes.io/zh-cn/docs/concepts/cluster-administration/logging/)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context sk8s
kubectl get pod legacy-app -o yaml > varlog.yaml
vim varlog.yaml
kubectl delete pod legacy-app
kubectl apply -f varlog.yaml
12345
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context sk8s
#导出已有Pod的yaml文件
kubectl get pod legacy-app -o yaml > varlog.yaml
vim varlog.yaml
#仅需修改spec里面的部分内容，其他均不涉及；
#注意：在英文半角下操作；
#注意：空格数量保持一致，这里极其容易出错；
spec:
  containers:
  - args:
    - /bin/sh
    - -c
    - |
      i=0; while true; do
        echo "$(date) INFO $i" >> /var/log/legacy-app.log;
        i=$((i+1));
        sleep 1;
      done
    image: busybox
    imagePullPolicy: IfNotPresent
    name: count
    resources: {}
    terminationMessagePath: /dev/termination-log
    terminationMessagePolicy: File
    volumeMounts:
    - mountPath: /var/run/secrets/kubernetes.io/serviceaccount
      name: kube-api-access-rlkbh
      readOnly: true
    - name: varlog #需要新增的内容；
      mountPath: /var/log #需要新增的内容，严格按照题目中要求的路径填写；
  - name: sidecar #需要新增的内容，严格按照题目中要求的名字填写；
    image: busybox #需要新增的内容，只能使用题目中要求的镜像；
    imagePullPolicy: IfNotPresent #需要新增的内容，题目中没要求，建议这样写；
    args: [/bin/sh, -c, 'tail -n+1 -f /var/log/legacy-app.log'] #需要新增的内容，注意使用英文半角的逗号和引号；
    volumeMounts: #需要新增的内容；
    - name: varlog #需要新增的内容；
      mountPath: /var/log #需要新增的内容，严格按照题目中要求的路径填写，且需要与容器count保持一致；
...

  volumes:
  - name: kube-api-access-rlkbh
    projected:
      defaultMode: 420
      sources:
      - serviceAccountToken:
          expirationSeconds: 3607
          path: token
      - configMap:
          items:
          - key: ca.crt
            path: ca.crt
          name: kube-root-ca.crt
      - downwardAPI:
          items:
          - fieldRef:
              apiVersion: v1
              fieldPath: metadata.namespace
            path: namespace
  - name: varlog #需要新增的内容，注意需要跟上面kube-api-access-rlkbh的空格数保持一致；
    emptyDir: {} #需要新增的内容；
...
#注意，这里需要先删除已有的Pod，否则会报Warning，这里需要耐心等待2分钟左右，不建议做任何操作；
kubectl delete pod legacy-app
#检查确认是否已删除原Pod；
kubectl get pod legacy-app
kubectl apply -f varlog.yaml
kubectl get pod legacy-app
12345678910111213141516171819202122232425262728293031323334353637383940414243444546474849505152535455565758596061626364656667
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
kubectl logs legacy-app sidecar
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
Tue Jan 16 09:43:49 UTC 2024 INFO 0
Tue Jan 16 09:43:50 UTC 2024 INFO 1
Tue Jan 16 09:43:51 UTC 2024 INFO 2
Tue Jan 16 09:43:52 UTC 2024 INFO 3
Tue Jan 16 09:43:53 UTC 2024 INFO 4
Tue Jan 16 09:43:54 UTC 2024 INFO 5
Tue Jan 16 09:43:55 UTC 2024 INFO 6
Tue Jan 16 09:43:56 UTC 2024 INFO 7
Tue Jan 16 09:43:57 UTC 2024 INFO 8
Tue Jan 16 09:43:58 UTC 2024 INFO 9
Tue Jan 16 09:43:59 UTC 2024 INFO 10
Tue Jan 16 09:44:00 UTC 2024 INFO 11
Tue Jan 16 09:44:01 UTC 2024 INFO 12
Tue Jan 16 09:44:02 UTC 2024 INFO 13
Tue Jan 16 09:44:03 UTC 2024 INFO 14
Tue Jan 16 09:44:04 UTC 2024 INFO 15
...
--------------------------------------------分割结束线-----------------------------------------------
12345678910111213141516171819202122
```

# 第7题：Etcd的备份恢复

## 1. 分值权重：7%

## 2. 考题内容

### 2.1 设置配置环境

此题目无需更改配置环境。但是，在执行此项目之前，请确保您已返回初始环境student@node01，否则需要exit退出。

### 2.2 Context

无

### 2.3 Task

首先，为运行在https://127.0.0.1:2379上的现有etcd 实例创建快照并将快照保存到 /var/lib/backup/etcd-snapshot.db

为给定实例创建快照预计能在几秒钟内完成。如果该操作似乎挂起，则命令可能有问题。用CTRL+C 来取消操作，然后重试。

然后还原位于/data/backup/etcd-snapshot-previous.db的现有先前快照。

最后，提供了以下TLS证书和密钥，以通过etcdctl连接到服务。

- CA证书: /opt/DAVIDWATT00601/ca.crt
- 客户端证书: /opt/DAVIDWATT00601/etcd-client.crt
- 客户端密钥: /opt/DAVIDWATT00601/etcd-client.key

## 3. 考点解析

Etcd的备份恢复

## 4. 考点参考链接

[操作 Kubernetes 中的 etcd 集群](https://kubernetes.io/zh-cn/docs/tasks/administer-cluster/configure-upgrade-etcd/)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
#注意，一般情况下，本题不需要切换环境，直接操作即可；
export ETCDCTL_API=3 #建议操作，避免下面每条 etcdctl 命令前都要加 ETCDCTL_API=3；
etcdctl snapshot save /var/lib/backup/etcd-snapshot.db --endpoints=https://127.0.0.1:2379 --cacert="/opt/DAVIDWATT00601/ca.crt" --cert="/opt/DAVIDWATT00601/etcd-client.crt" --key="/opt/DAVIDWATT00601/etcd-client.key"
sudo etcdctl snapshot restore /data/backup/etcd-snapshot-previous.db --endpoints=https://127.0.0.1:2379
1234
```

### 5.2 详细操作步骤和结果

```
#注意，一般情况下，本题不需要切换环境，直接操作即可；
# 备份
export ETCDCTL_API=3 #建议操作，避免下面每条 etcdctl 命令前都要加 ETCDCTL_API=3；
etcdctl snapshot save /var/lib/backup/etcd-snapshot.db --endpoints=https://127.0.0.1:2379 --cacert="/opt/DAVIDWATT00601/ca.crt" --cert="/opt/DAVIDWATT00601/etcd-client.crt" --key="/opt/DAVIDWATT00601/etcd-client.key"
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
{"level":"info","ts":"2024-01-17T14:57:41.061+0800","caller":"snapshot/v3_snapshot.go:65","msg":"created temporary db file","path":"/var/lib/backup/etcd-snapshot.db.part"}
{"level":"info","ts":"2024-01-17T14:57:41.077+0800","logger":"client","caller":"v3@v3.5.7/maintenance.go:212","msg":"opened snapshot stream; downloading"}
{"level":"info","ts":"2024-01-17T14:57:41.077+0800","caller":"snapshot/v3_snapshot.go:73","msg":"fetching snapshot","endpoint":"https://127.0.0.1:2379"}
{"level":"info","ts":"2024-01-17T14:57:41.621+0800","logger":"client","caller":"v3@v3.5.7/maintenance.go:220","msg":"completed snapshot read; closing"}
{"level":"info","ts":"2024-01-17T14:57:41.661+0800","caller":"snapshot/v3_snapshot.go:88","msg":"fetched snapshot","endpoint":"https://127.0.0.1:2379","size":"14 MB","took":"now"}
{"level":"info","ts":"2024-01-17T14:57:41.661+0800","caller":"snapshot/v3_snapshot.go:97","msg":"saved","path":"/var/lib/backup/etcd-snapshot.db"}
Snapshot saved at /var/lib/backup/etcd-snapshot.db
--------------------------------------------分割结束线-----------------------------------------------
#检查备份是否成功，考试时如果时间紧张可以不用检查；
etcdctl snapshot status /var/lib/backup/etcd-snapshot.db -wtable
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
Deprecated: Use `etcdutl snapshot status` instead.

+----------+----------+------------+------------+
|   HASH   | REVISION | TOTAL KEYS | TOTAL SIZE |
+----------+----------+------------+------------+
| a5716347 |    39416 |       3600 |      14 MB |
+----------+----------+------------+------------+
--------------------------------------------分割结束线-----------------------------------------------
#检查读写权限
ll /data/backup/etcd-snapshot-previous.db
-rw-------+ 1 root root 6713376 May 20  2023 /data/backup/etcd-snapshot-previous.db
# 恢复
#注意，这里需要使用sudo,否则会报“Error: open /data/backup/etcd-snapshot-previous.db: permission denied”
sudo etcdctl snapshot restore /data/backup/etcd-snapshot-previous.db --endpoints=https://127.0.0.1:2379
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
Deprecated: Use `etcdutl snapshot restore` instead.

2024-01-17T15:06:37+08:00       info    snapshot/v3_snapshot.go:248     restoring snapshot      {"path": "/data/backup/etcd-snapshot-previous.db", "wal-dir": "default.etcd/member/wal", "data-dir": "default.etcd", "snap-dir": "default.etcd/member/snap", "stack": "go.etcd.io/etcd/etcdutl/v3/snapshot.(*v3Manager).Restore\n\tgo.etcd.io/etcd/etcdutl/v3@v3.5.7/snapshot/v3_snapshot.go:254\ngo.etcd.io/etcd/etcdutl/v3/etcdutl.SnapshotRestoreCommandFunc\n\tgo.etcd.io/etcd/etcdutl/v3@v3.5.7/etcdutl/snapshot_command.go:147\ngo.etcd.io/etcd/etcdctl/v3/ctlv3/command.snapshotRestoreCommandFunc\n\tgo.etcd.io/etcd/etcdctl/v3/ctlv3/command/snapshot_command.go:129\ngithub.com/spf13/cobra.(*Command).execute\n\tgithub.com/spf13/cobra@v1.1.3/command.go:856\ngithub.com/spf13/cobra.(*Command).ExecuteC\n\tgithub.com/spf13/cobra@v1.1.3/command.go:960\ngithub.com/spf13/cobra.(*Command).Execute\n\tgithub.com/spf13/cobra@v1.1.3/command.go:897\ngo.etcd.io/etcd/etcdctl/v3/ctlv3.Start\n\tgo.etcd.io/etcd/etcdctl/v3/ctlv3/ctl.go:107\ngo.etcd.io/etcd/etcdctl/v3/ctlv3.MustStart\n\tgo.etcd.io/etcd/etcdctl/v3/ctlv3/ctl.go:111\nmain.main\n\tgo.etcd.io/etcd/etcdctl/v3/main.go:59\nruntime.main\n\truntime/proc.go:255"}
2024-01-17T15:06:37+08:00       info    membership/store.go:141 Trimming membership information from the backend...
2024-01-17T15:06:37+08:00       info    membership/cluster.go:421       added member    {"cluster-id": "cdf818194e3a8c32", "local-member-id": "0", "added-peer-id": "8e9e05c52164694d", "added-peer-peer-urls": ["http://localhost:2380"]}
2024-01-17T15:06:37+08:00       info    snapshot/v3_snapshot.go:269     restored snapshot       {"path": "/data/backup/etcd-snapshot-previous.db", "wal-dir": "default.etcd/member/wal", "data-dir": "default.etcd", "snap-dir": "default.etcd/member/snap"}
--------------------------------------------分割结束线-----------------------------------------------
1234567891011121314151617181920212223242526272829303132333435363738394041
```

## 6. 验证命令和结果

```
#检查恢复是否成功，考试时如果时间紧张可以不用检查；
kubectl get pod -A
12
```

# 第8题：Kubernetes集群版本升级

## 1. 分值权重：7%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context vk8s`

### 2.2 Context

无

### 2.3 Task

当前 Kubernetes 集群正在运行版本为1.28.0，仅将 master 节点上的所有 Kubernetes 控制平面和节点组件升级到版本 1.28.1。

确保在升级之前 drain master 节点，并在升级后 uncordon master 节点。

可以使用以下命令，通过 ssh 连接到 master 节点：`ssh master01`

可以使用以下命令，在该 master 节点上获取更高权限：`sudo -i`

另外，在主节点上升级 kubelet 和 kubectl。请不要升级工作节点、etcd、container 管理器、CNI 插件、 DNS 服务或任何其他插件。

## 3. 考点解析

（1）Kubernetes集群版本升级

（2）`apt-get update` 和 `apt-get upgrade`

`apt-get update` 和 `apt-get upgrade` 是两个用于管理 Debian 系统软件包的命令，它们的主要区别在于功能和执行时机。

*apt-get update:**

- `apt-get update` 命令用于更新本地存储库索引。它会从软件包源（repository）中下载最新的软件包列表和信息，但不会安装任何新的软件包。这个命令确保你的本地软件包信息是最新的，以便后续的软件包管理操作。
- 示例：
    
    ```bash
    sudo apt-get update
    ```
    

**apt-get upgrade:**

- `apt-get upgrade` 命令用于安装当前系统上已安装的软件包的最新版本。它会检查系统上已安装软件包的新版本，并升级这些软件包到最新版本。在执行之前，通常需要先运行 `apt-get update` 确保软件包信息是最新的。
- 示例：
    
    ```
    sudo apt-get upgrade
    1
    ```
    

因此，一般的更新软件包的步骤是先运行 `apt-get update` 更新软件包索引，然后再运行 `apt-get upgrade` 升级已安装的软件包。

## 4. 考点参考链接

[升级 kubeadm 集群](https://kubernetes.io/zh-cn/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade/)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context vk8s
kubectl get node
#注意，这里需要加上--ignore-daemonsets；
kubectl drain master01 --ignore-daemonsets
ssh master01
sudo -i
apt-get update
apt-get install kubeadm=1.28.1-00
kubeadm upgrade plan
#注意需要输入--etcd-upgrade=false，中间需要输入y确认，整个过程大约需要5分钟左右，请耐心等待；
kubeadm upgrade apply 1.28.1 --etcd-upgrade=false
apt-get install kubelet=1.28.1-00
apt-get install kubectl=1.28.1-00
kubectl uncordon master01
1234567891011121314
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context vk8s
#操作前记录；
kubectl get node
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：（注意此时master01的版本为1.28.0）
NAME       STATUS   ROLES           AGE    VERSION
master01   Ready    control-plane   241d   v1.28.0
node01     Ready    <none>          241d   v1.28.0
node02     Ready    <none>          241d   v1.28.0
--------------------------------------------分割结束线----------------------------------------------
#注意，这里需要加上--ignore-daemonsets；
kubectl drain master01 --ignore-daemonsets
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
node/master01 cordoned
Warning: ignoring DaemonSet-managed Pods: calico-system/calico-node-9d6xh, calico-system/csi-node-driver-jf5j6, kube-system/kube-proxy-m72qj
evicting pod calico-system/calico-typha-5f66cb788d-nf2d7
pod/calico-typha-5f66cb788d-nf2d7 evicted
node/master01 drained
--------------------------------------------分割结束线----------------------------------------------
ssh master01
sudo -i
apt-get update
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Hit:1 http://mirrors.ustc.edu.cn/ubuntu focal InRelease
Get:2 http://mirrors.ustc.edu.cn/ubuntu focal-updates InRelease [114 kB]
Get:3 http://mirrors.ustc.edu.cn/ubuntu focal-backports InRelease [108 kB]
Get:4 http://mirrors.ustc.edu.cn/ubuntu focal-security InRelease [114 kB]
Get:5 http://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu focal InRelease [57.7 kB]
Get:6 http://mirrors.ustc.edu.cn/kubernetes/apt kubernetes-xenial InRelease [8,993 B]
Get:7 http://mirrors.ustc.edu.cn/ubuntu focal-updates/main amd64 Packages [3,030 kB]
Get:8 http://mirrors.ustc.edu.cn/ubuntu focal-updates/main Translation-en [489 kB]
Get:9 http://mirrors.ustc.edu.cn/ubuntu focal-updates/main amd64 c-n-f Metadata [17.2 kB]
Get:10 http://mirrors.ustc.edu.cn/ubuntu focal-updates/restricted amd64 Packages [2,579 kB]
Get:11 http://mirrors.ustc.edu.cn/ubuntu focal-updates/restricted Translation-en [360 kB]
Get:12 http://mirrors.ustc.edu.cn/ubuntu focal-updates/restricted amd64 c-n-f Metadata [552 B]
Get:13 http://mirrors.ustc.edu.cn/ubuntu focal-updates/universe amd64 Packages [1,150 kB]
Get:14 http://mirrors.ustc.edu.cn/ubuntu focal-updates/universe Translation-en [276 kB]
Get:15 http://mirrors.ustc.edu.cn/ubuntu focal-updates/universe amd64 c-n-f Metadata [25.7 kB]
Get:16 http://mirrors.ustc.edu.cn/ubuntu focal-updates/multiverse amd64 Packages [26.1 kB]
Get:17 http://mirrors.ustc.edu.cn/ubuntu focal-updates/multiverse Translation-en [7,768 B]
Get:18 http://mirrors.ustc.edu.cn/ubuntu focal-updates/multiverse amd64 c-n-f Metadata [620 B]
Get:19 http://mirrors.ustc.edu.cn/ubuntu focal-security/main amd64 Packages [2,647 kB]
Get:20 http://mirrors.ustc.edu.cn/ubuntu focal-security/main Translation-en [406 kB]
Get:21 http://mirrors.ustc.edu.cn/ubuntu focal-security/main amd64 c-n-f Metadata [13.2 kB]
Get:22 http://mirrors.ustc.edu.cn/ubuntu focal-security/restricted amd64 Packages [2,461 kB]
Get:23 http://mirrors.ustc.edu.cn/ubuntu focal-security/restricted Translation-en [343 kB]
Get:24 http://mirrors.ustc.edu.cn/ubuntu focal-security/restricted amd64 c-n-f Metadata [552 B]
Get:25 http://mirrors.ustc.edu.cn/ubuntu focal-security/universe amd64 Packages [924 kB]
Get:26 http://mirrors.ustc.edu.cn/ubuntu focal-security/universe Translation-en [194 kB]
Get:27 http://mirrors.ustc.edu.cn/ubuntu focal-security/universe amd64 c-n-f Metadata [19.2 kB]
Get:28 http://mirrors.ustc.edu.cn/ubuntu focal-security/multiverse amd64 Packages [23.9 kB]
Get:29 http://mirrors.ustc.edu.cn/ubuntu focal-security/multiverse Translation-en [5,796 B]
Get:30 http://mirrors.ustc.edu.cn/ubuntu focal-security/multiverse amd64 c-n-f Metadata [548 B]
Get:31 http://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu focal/stable amd64 Packages [34.2 kB]
Ign:32 http://mirrors.ustc.edu.cn/kubernetes/apt kubernetes-xenial/main amd64 Packages
Get:32 http://mirrors.ustc.edu.cn/kubernetes/apt kubernetes-xenial/main amd64 Packages [69.9 kB]
Fetched 15.5 MB in 28s (552 kB/s)
Reading package lists... Done
--------------------------------------------分割结束线----------------------------------------------
apt-cache show kubeadm | grep 1.28.1 #根据考试要求，填写相应版本；
apt-get install kubeadm=1.28.1-00
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages will be upgraded:
  kubeadm
1 upgraded, 0 newly installed, 0 to remove and 151 not upgraded.
Need to get 10.3 MB of archives.
After this operation, 0 B of additional disk space will be used.
Get:1 http://mirrors.ustc.edu.cn/kubernetes/apt kubernetes-xenial/main amd64 kubeadm amd64 1.28.1-00 [10.3 MB]
Fetched 10.3 MB in 9s (1,200 kB/s)
(Reading database ... 111150 files and directories currently installed.)
Preparing to unpack .../kubeadm_1.28.1-00_amd64.deb ...
Unpacking kubeadm (1.28.1-00) over (1.28.0-00) ...
Setting up kubeadm (1.28.1-00) ...
--------------------------------------------分割结束线----------------------------------------------
kubeadm version
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
kubeadm version: &version.Info{Major:"1", Minor:"28", GitVersion:"v1.28.1", GitCommit:"8dc49c4b984b897d423aab4971090e1879eb4f23", GitTreeState:"clean", BuildDate:"2023-08-24T11:21:51Z", GoVersion:"go1.20.7", Compiler:"gc", Platform:"linux/amd64"}
--------------------------------------------分割结束线----------------------------------------------
kubeadm upgrade plan
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
[upgrade/config] Making sure the configuration is correct:
[upgrade/config] Reading configuration from the cluster...
[upgrade/config] FYI: You can look at this config file with 'kubectl -n kube-system get cm kubeadm-config -o yaml'
[preflight] Running pre-flight checks.
[upgrade] Running cluster health checks
[upgrade] Fetching available versions to upgrade to
[upgrade/versions] Cluster version: v1.28.0
[upgrade/versions] kubeadm version: v1.28.1
I0117 16:06:15.844532   29971 version.go:256] remote version is much newer: v1.29.0; falling back to: stable-1.28
[upgrade/versions] Target version: v1.28.5
W0117 16:06:31.919989   29971 version.go:104] could not fetch a Kubernetes version from the internet: unable to get URL "https://dl.k8s.io/release/stable-1.28.txt": Get "https://cdn.dl.k8s.io/release/stable-1.28.txt": context deadline exceeded (Client.Timeout exceeded while awaiting headers)
W0117 16:06:31.920026   29971 version.go:105] falling back to the local client version: v1.28.1
[upgrade/versions] Latest version in the v1.28 series: v1.28.1

Components that must be upgraded manually after you have upgraded the control plane with 'kubeadm upgrade apply':
COMPONENT   CURRENT       TARGET
kubelet     3 x v1.28.0   v1.28.1

Upgrade to the latest version in the v1.28 series:

COMPONENT                 CURRENT   TARGET
kube-apiserver            v1.28.0   v1.28.1
kube-controller-manager   v1.28.0   v1.28.1
kube-scheduler            v1.28.0   v1.28.1
kube-proxy                v1.28.0   v1.28.1
CoreDNS                   v1.10.1   v1.10.1
etcd                      3.5.7-0   3.5.9-0

You can now apply the upgrade by executing the following command:

        kubeadm upgrade apply v1.28.1

_____________________________________________________________________

Components that must be upgraded manually after you have upgraded the control plane with 'kubeadm upgrade apply':
COMPONENT   CURRENT       TARGET
kubelet     3 x v1.28.0   v1.28.5

Upgrade to the latest stable version:

COMPONENT                 CURRENT   TARGET
kube-apiserver            v1.28.0   v1.28.5
kube-controller-manager   v1.28.0   v1.28.5
kube-scheduler            v1.28.0   v1.28.5
kube-proxy                v1.28.0   v1.28.5
CoreDNS                   v1.10.1   v1.10.1
etcd                      3.5.7-0   3.5.9-0

You can now apply the upgrade by executing the following command:

        kubeadm upgrade apply v1.28.5

Note: Before you can perform this upgrade, you have to update kubeadm to v1.28.5.

_____________________________________________________________________

The table below shows the current state of component configs as understood by this version of kubeadm.
Configs that have a "yes" mark in the "MANUAL UPGRADE REQUIRED" column require manual config upgrade or
resetting to kubeadm defaults before a successful upgrade can be performed. The version to manually
upgrade to is denoted in the "PREFERRED VERSION" column.

API GROUP                 CURRENT VERSION   PREFERRED VERSION   MANUAL UPGRADE REQUIRED
kubeproxy.config.k8s.io   v1alpha1          v1alpha1            no
kubelet.config.k8s.io     v1beta1           v1beta1             no
_____________________________________________________________________
--------------------------------------------分割结束线----------------------------------------------
#注意需要输入--etcd-upgrade=false，中间需要输入y确认，整个过程大约需要5分钟左右，请耐心等待；
kubeadm upgrade apply 1.28.1 --etcd-upgrade=false
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
[upgrade/config] Making sure the configuration is correct:
[upgrade/config] Reading configuration from the cluster...
[upgrade/config] FYI: You can look at this config file with 'kubectl -n kube-system get cm kubeadm-config -o yaml'
[preflight] Running pre-flight checks.
[upgrade] Running cluster health checks
[upgrade/version] You have chosen to change the cluster version to "v1.28.1"
[upgrade/versions] Cluster version: v1.28.0
[upgrade/versions] kubeadm version: v1.28.1
[upgrade] Are you sure you want to proceed? [y/N]: y
[upgrade/prepull] Pulling images required for setting up a Kubernetes cluster
[upgrade/prepull] This might take a minute or two, depending on the speed of your internet connection
[upgrade/prepull] You can also perform this action in beforehand using 'kubeadm config images pull'
W0117 16:12:04.044053   30485 checks.go:835] detected that the sandbox image "registry.k8s.io/pause:3.6" of the container runtime is inconsistent with that used by kubeadm. It is recommended that using "registry.aliyuncs.com/google_containers/pause:3.9" as the CRI sandbox image.
[upgrade/apply] Upgrading your Static Pod-hosted control plane to version "v1.28.1" (timeout: 5m0s)...
[upgrade/staticpods] Writing new Static Pod manifests to "/etc/kubernetes/tmp/kubeadm-upgraded-manifests271030507"
[upgrade/staticpods] Preparing for "kube-apiserver" upgrade
[upgrade/staticpods] Renewing apiserver certificate
[upgrade/staticpods] Renewing apiserver-kubelet-client certificate
[upgrade/staticpods] Renewing front-proxy-client certificate
[upgrade/staticpods] Renewing apiserver-etcd-client certificate
[upgrade/staticpods] Moved new manifest to "/etc/kubernetes/manifests/kube-apiserver.yaml" and backed up old manifest to "/etc/kubernetes/tmp/kubeadm-backup-manifests-2024-01-17-16-12-04/kube-apiserver.yaml"
[upgrade/staticpods] Waiting for the kubelet to restart the component
[upgrade/staticpods] This might take a minute or longer depending on the component/version gap (timeout 5m0s)
[apiclient] Found 1 Pods for label selector component=kube-apiserver
[upgrade/staticpods] Component "kube-apiserver" upgraded successfully!
[upgrade/staticpods] Preparing for "kube-controller-manager" upgrade
[upgrade/staticpods] Renewing controller-manager.conf certificate
[upgrade/staticpods] Moved new manifest to "/etc/kubernetes/manifests/kube-controller-manager.yaml" and backed up old manifest to "/etc/kubernetes/tmp/kubeadm-backup-manifests-2024-01-17-16-12-04/kube-controller-manager.yaml"
[upgrade/staticpods] Waiting for the kubelet to restart the component
[upgrade/staticpods] This might take a minute or longer depending on the component/version gap (timeout 5m0s)
[apiclient] Found 1 Pods for label selector component=kube-controller-manager
[upgrade/staticpods] Component "kube-controller-manager" upgraded successfully!
[upgrade/staticpods] Preparing for "kube-scheduler" upgrade
[upgrade/staticpods] Renewing scheduler.conf certificate
[upgrade/staticpods] Moved new manifest to "/etc/kubernetes/manifests/kube-scheduler.yaml" and backed up old manifest to "/etc/kubernetes/tmp/kubeadm-backup-manifests-2024-01-17-16-12-04/kube-scheduler.yaml"
[upgrade/staticpods] Waiting for the kubelet to restart the component
[upgrade/staticpods] This might take a minute or longer depending on the component/version gap (timeout 5m0s)
[apiclient] Found 1 Pods for label selector component=kube-scheduler
[upgrade/staticpods] Component "kube-scheduler" upgraded successfully!
[upload-config] Storing the configuration used in ConfigMap "kubeadm-config" in the "kube-system" Namespace
[kubelet] Creating a ConfigMap "kubelet-config" in namespace kube-system with the configuration for the kubelets in the cluster
[upgrade] Backing up kubelet config file to /etc/kubernetes/tmp/kubeadm-kubelet-config2482258095/config.yaml
[kubelet-start] Writing kubelet configuration to file "/var/lib/kubelet/config.yaml"
[bootstrap-token] Configured RBAC rules to allow Node Bootstrap tokens to get nodes
[bootstrap-token] Configured RBAC rules to allow Node Bootstrap tokens to post CSRs in order for nodes to get long term certificate credentials
[bootstrap-token] Configured RBAC rules to allow the csrapprover controller automatically approve CSRs from a Node Bootstrap Token
[bootstrap-token] Configured RBAC rules to allow certificate rotation for all node client certificates in the cluster
[addons] Applied essential addon: CoreDNS
[addons] Applied essential addon: kube-proxy

[upgrade/successful] SUCCESS! Your cluster was upgraded to "v1.28.1". Enjoy!

[upgrade/kubelet] Now that your control plane is upgraded, please proceed with upgrading your kubelets if you haven't already done so.
--------------------------------------------分割结束线----------------------------------------------
apt-get install kubelet=1.28.1-00
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages will be upgraded:
  kubelet
1 upgraded, 0 newly installed, 0 to remove and 151 not upgraded.
Need to get 19.5 MB of archives.
After this operation, 0 B of additional disk space will be used.
Get:1 http://mirrors.ustc.edu.cn/kubernetes/apt kubernetes-xenial/main amd64 kubelet amd64 1.28.1-00 [19.5 MB]
Fetched 19.5 MB in 7s (2,745 kB/s)
(Reading database ... 111150 files and directories currently installed.)
Preparing to unpack .../kubelet_1.28.1-00_amd64.deb ...
Unpacking kubelet (1.28.1-00) over (1.28.0-00) ...
Setting up kubelet (1.28.1-00) ...
--------------------------------------------分割结束线----------------------------------------------
kubelet --version
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Kubernetes v1.28.1
--------------------------------------------分割结束线----------------------------------------------
apt-get install kubectl=1.28.1-00
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages will be upgraded:
  kubectl
1 upgraded, 0 newly installed, 0 to remove and 151 not upgraded.
Need to get 10.3 MB of archives.
After this operation, 0 B of additional disk space will be used.
Get:1 http://mirrors.ustc.edu.cn/kubernetes/apt kubernetes-xenial/main amd64 kubectl amd64 1.28.1-00 [10.3 MB]
Fetched 10.3 MB in 3s (3,289 kB/s)
(Reading database ... 111150 files and directories currently installed.)
Preparing to unpack .../kubectl_1.28.1-00_amd64.deb ...
Unpacking kubectl (1.28.1-00) over (1.28.0-00) ...
Setting up kubectl (1.28.1-00) ...
--------------------------------------------分割结束线----------------------------------------------
kubectl version
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Client Version: v1.28.1
Kustomize Version: v5.0.4-0.20230601165947-6ce0bf390ce3
Server Version: v1.28.1
--------------------------------------------分割结束线----------------------------------------------
root@master01:~# exit
logout
student@master01:~$ exit
logout
Connection to master01 closed.
#将master01设置为可调度
kubectl uncordon master01
node/master01 uncordoned
123456789101112131415161718192021222324252627282930313233343536373839404142434445464748495051525354555657585960616263646566676869707172737475767778798081828384858687888990919293949596979899100101102103104105106107108109110111112113114115116117118119120121122123124125126127128129130131132133134135136137138139140141142143144145146147148149150151152153154155156157158159160161162163164165166167168169170171172173174175176177178179180181182183184185186187188189190191192193194195196197198199200201202203204205206207208209210211212213214215216217218219220221222223224225226227228229230231232233234235236237238239240241242243244245246247248249250251252253254255256257258259260261262263264265266267268269
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
kubectl get node
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：（注意此时master01节点的版本已经升级为1.28.1）
NAME       STATUS   ROLES           AGE    VERSION
master01   Ready    control-plane   241d   v1.28.1
node01     Ready    <none>          241d   v1.28.0
node02     Ready    <none>          241d   v1.28.0
--------------------------------------------分割结束线----------------------------------------------
123456789
```

# 第9题：Pod日志

## 1. 分值权重：5%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context lk8s`

### 2.2 Context

无

### 2.3 Task

监控pod foo的日志，并提取与错误RLIMIT_NOFILE 相对应的日志行，将这些日志行写入/opt/DAVIDWATT00101/foo

## 3. 考点解析

检查 Pod 的日志

## 4. 考点参考链接

[检查 Pod 的日志](https://kubernetes.io/zh-cn/docs/tasks/debug/debug-application/debug-running-pod/#examine-pod-logs)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context lk8s
kubectl logs foo | grep RLIMIT_NOFILE > /opt/DAVIDWATT00101/foo
12
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context lk8s
#学习步骤
kubectl logs -h
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Print the logs for a container in a pod or specified resource. If the pod has only one container, the container name is optional.

Examples:
  # Return snapshot logs from pod nginx with only one container
  kubectl logs nginx

  # Return snapshot logs from pod nginx with multi containers
  kubectl logs nginx --all-containers=true

  # Return snapshot logs from all containers in pods defined by label app=nginx
  kubectl logs -l app=nginx --all-containers=true

  # Return snapshot of previous terminated ruby container logs from pod web-1
  kubectl logs -p -c ruby web-1

  # Begin streaming the logs of the ruby container in pod web-1
  kubectl logs -f -c ruby web-1

  # Begin streaming the logs from all containers in pods defined by label app=nginx
  kubectl logs -f -l app=nginx --all-containers=true

  # Display only the most recent 20 lines of output in pod nginx
  kubectl logs --tail=20 nginx

  # Show all logs from pod nginx written in the last hour
  kubectl logs --since=1h nginx

  # Show logs from a kubelet with an expired serving certificate
  kubectl logs --insecure-skip-tls-verify-backend nginx

  # Return snapshot logs from first container of a job named hello
  kubectl logs job/hello

  # Return snapshot logs from container nginx-1 of a deployment named nginx
  kubectl logs deployment/nginx -c nginx-1

Options:
    --all-containers=false:
        Get all containers' logs in the pod(s).

    -c, --container='':
        Print the logs of this container

    -f, --follow=false:
        Specify if the logs should be streamed.

    --ignore-errors=false:
        If watching / following pod logs, allow for any errors that occur to be non-fatal

    --insecure-skip-tls-verify-backend=false:
        Skip verifying the identity of the kubelet that logs are requested from.  In theory, an attacker could provide invalid log content back. You might want to use this if your kubelet serving certificates have expired.

    --limit-bytes=0:
        Maximum bytes of logs to return. Defaults to no limit.

    --max-log-requests=5:
        Specify maximum number of concurrent logs to follow when using by a selector. Defaults to 5.

    --pod-running-timeout=20s:
        The length of time (like 5s, 2m, or 3h, higher than zero) to wait until at least one pod is running

    --prefix=false:
        Prefix each log line with the log source (pod name and container name)

    -p, --previous=false:
        If true, print the logs for the previous instance of the container in a pod if it exists.

    -l, --selector='':
        Selector (label query) to filter on, supports '=', '==', and '!='.(e.g. -l key1=value1,key2=value2). Matching objects must satisfy all of the specified label constraints.

    --since=0s:
        Only return logs newer than a relative duration like 5s, 2m, or 3h. Defaults to all logs. Only one of since-time / since may be used.

    --since-time='':
        Only return logs after a specific date (RFC3339). Defaults to all logs. Only one of since-time / since may be used.

    --tail=-1:
        Lines of recent log file to display. Defaults to -1 with no selector, showing all log lines otherwise 10, if a selector is provided.

    --timestamps=false:
        Include timestamps on each line in the log output

Usage:
  kubectl logs [-f] [-p] (POD | TYPE/NAME) [-c CONTAINER] [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
--------------------------------------------分割结束线----------------------------------------------
#核心步骤
kubectl logs pod/foo | grep RLIMIT_NOFILE > /opt/DAVIDWATT00101/foo
12345678910111213141516171819202122232425262728293031323334353637383940414243444546474849505152535455565758596061626364656667686970717273747576777879808182838485868788899091929394
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
cat /opt/DAVIDWATT00101/foo
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
2024/01/17 06:03:28 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
--------------------------------------------分割结束线----------------------------------------------
123456
```

# 第10题：Pod监控

## 1. 分值权重：5%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context mk8s`

### 2.2 Context

无

### 2.3 Task

通过pod label name=cpu-loader，找到运行时占用大量CPU的pod，并将占用CPU最高的pod名称写入文件：/opt/DAVIDWATT00401/DAVIDWATT00401.txt (已存在)

## 3. 考点解析

kubectl top pod命令

## 4. 考点参考链接

[与Pod交互](https://kubernetes.io/docs/reference/kubectl/quick-reference/#interacting-with-running-pods)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context mk8s
kubectl top pod -h
kubectl top pod -l name=cpu-loader --sort-by=cpu –A
echo "<POD_NAME>" > /opt/DAVIDWATT00401/DAVIDWATT00401.txt
1234
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context mk8s
kubectl top pod -h
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Display resource (CPU/memory) usage of pods.

 The 'top pod' command allows you to see the resource consumption of pods.

 Due to the metrics pipeline delay, they may be unavailable for a few minutes since pod creation.

Aliases:
pod, pods, po

Examples:
  # Show metrics for all pods in the default namespace
  kubectl top pod

  # Show metrics for all pods in the given namespace
  kubectl top pod --namespace=NAMESPACE

  # Show metrics for a given pod and its containers
  kubectl top pod POD_NAME --containers

  # Show metrics for the pods defined by label name=myLabel
  kubectl top pod -l name=myLabel

Options:
    -A, --all-namespaces=false:
        If present, list the requested object(s) across all namespaces. Namespace in current context is ignored even if specified with --namespace.

    --containers=false:
        If present, print usage of containers within a pod.

    --field-selector='':
        Selector (field query) to filter on, supports '=', '==', and '!='.(e.g. --field-selector
        key1=value1,key2=value2). The server only supports a limited number of field queries per type.

    --no-headers=false:
        If present, print output without headers.

    -l, --selector='':
        Selector (label query) to filter on, supports '=', '==', and '!='.(e.g. -l key1=value1,key2=value2). Matching objects must satisfy all of the specified label constraints.

    --sort-by='':
        If non-empty, sort pods list using specified field. The field can be either 'cpu' or 'memory'.

    --sum=false:
        Print the sum of the resource usage

    --use-protocol-buffers=true:
        Enables using protocol-buffers to access Metrics API.

Usage:
  kubectl top pod [NAME | -l label] [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
--------------------------------------------分割结束线----------------------------------------------
#核心步骤
kubectl top pod -l name=cpu-loader --sort-by=cpu –A
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
NAMESPACE   NAME                         CPU(cores)   MEMORY(bytes)
cpu-top     redis-test-5db498bbd-h2mfj   2m           3Mi
cpu-top     nginx-host-c58757c-q6k74     0m           5Mi
cpu-top     test0-784f495b5c-2dqdv       0m           8Mi
--------------------------------------------分割结束线----------------------------------------------
echo "redis-test-5db498bbd-h2mfj" > /opt/DAVIDWATT00401/DAVIDWATT00401.txt
12345678910111213141516171819202122232425262728293031323334353637383940414243444546474849505152535455565758596061626364656667
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
cat /opt/DAVIDWATT000401/DAVIDWATT00401.txt
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
redis-test-5db498bbd-h2mfj
--------------------------------------------分割结束线----------------------------------------------
123456
```

# 第11题：节点维护

## 1. 分值权重：4%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context nk8s`

### 2.2 Context

无

### 2.3 Task

将名为 node02 的 node 设置为不可用，并重新调度该 node 上所有运行的 pods。

## 3. 考点解析

drain和cordon

（1）Cordon

- `cordon` 的主要目的是防止调度新的 Pod 到节点上。
- 当您执行 `kubectl cordon <node-name>` 时，该节点将被标记为不可调度，即 Kubernetes 控制平面不会将新的 Pod 调度到该节点上，现有的 Pod 仍将在节点上正常运行不受影响。

（2）Drain

- `drain` 的主要目的是优雅地从节点上删除所有工作负载，并确保节点上的所有 Pod 均已经被重新调度到其他节点上。
- 当您执行 `kubectl drain <node-name>` 时，Kubernetes 将尝试从节点上驱逐所有 Pod，并确保它们已经在其他节点上重新调度。

总之，`cordon` 主要用于防止新 Pod 被调度到节点上，而 `drain` 用于安全地从节点上移除所有 Pod，并确保它们在其他节点上继续运行。在执行 `drain` 操作时，通常需要使用 `--ignore-daemonsets` 选项来忽略系统中的 DaemonSet，以确保集群中的一些核心服务（如网络插件）仍然能够正常工作。

## 4. 考点参考链接

[安全地清空一个节点](https://kubernetes.io/zh-cn/docs/tasks/administer-cluster/safely-drain-node/)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context nk8s
kubectl get nodes
kubectl cordon node02
kubectl get nodes
#核心步骤
kubectl drain node02 --ignore-daemonsets --force
123456
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context nk8s
kubectl get nodes
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
NAME       STATUS   ROLES           AGE    VERSION
master01   Ready    control-plane   242d   v1.28.0
node01     Ready    <none>          242d   v1.28.0
node02     Ready    <none>          242d   v1.28.0
--------------------------------------------分割结束线----------------------------------------------
kubectl cordon node02
kubectl get nodes
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
NAME       STATUS                     ROLES           AGE    VERSION
master01   Ready                      control-plane   242d   v1.28.0
node01     Ready                      <none>          242d   v1.28.0
node02     Ready,SchedulingDisabled   <none>          242d   v1.28.0
--------------------------------------------分割结束线----------------------------------------------
kubectl drain -h
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Drain node in preparation for maintenance.

 The given node will be marked unschedulable to prevent new pods from arriving. 'drain' evicts the pods if the API server supports https://kubernetes.io/docs/concepts/workloads/pods/disruptions/ eviction
https://kubernetes.io/docs/concepts/workloads/pods/disruptions/ . Otherwise, it will use normal DELETE to delete the pods. The 'drain' evicts or deletes all pods except mirror pods (which cannot be deleted through the API server).  If there are daemon set-managed pods, drain will not proceed without --ignore-daemonsets, and regardless it will not delete any daemon set-managed pods, because those pods would be immediately replaced by the daemon set controller, which ignores unschedulable markings.  If there are any pods that are neither mirror pods nor managed by a replication controller, replica set, daemon set, stateful set, or job, then drain will not delete any pods unless you use --force.
--force will also allow deletion to proceed if the managing resource of one or more pods is missing.

 'drain' waits for graceful termination. You should not operate on the machine until the command completes.

 When you are ready to put the node back into service, use kubectl uncordon, which will make the node schedulable again.

https://kubernetes.io/images/docs/kubectl_drain.svg Workflowhttps://kubernetes.io/images/docs/kubectl_drain.svg

Examples:
  # Drain node "foo", even if there are pods not managed by a replication controller, replica set, job, daemon set, or stateful set on it
  kubectl drain foo --force

  # As above, but abort if there are pods not managed by a replication controller, replica set, job, daemon set, or stateful set, and use a grace period of 15 minutes
  kubectl drain foo --grace-period=900

Options:
    --chunk-size=500:
        Return large lists in chunks rather than all at once. Pass 0 to disable. This flag is beta and may change in the future.

    --delete-emptydir-data=false:
        Continue even if there are pods using emptyDir (local data that will be deleted when the node is drained).

    --disable-eviction=false:
        Force drain to use delete, even if eviction is supported. This will bypass checking PodDisruptionBudgets, use with caution.

    --dry-run='none':
        Must be "none", "server", or "client". If client strategy, only print the object that would be sent, without sending it. If server strategy, submit server-side request without persisting the resource.

    --force=false:
        Continue even if there are pods that do not declare a controller.

    --grace-period=-1:
        Period of time in seconds given to each pod to terminate gracefully. If negative, the default value specified in the pod will be used.

    --ignore-daemonsets=false:
        Ignore DaemonSet-managed pods.

    --pod-selector='':
        Label selector to filter pods on the node

    -l, --selector='':
        Selector (label query) to filter on, supports '=', '==', and '!='.(e.g. -l key1=value1,key2=value2). Matching objects must satisfy all of the specified label constraints.

    --skip-wait-for-delete-timeout=0:
        If pod DeletionTimestamp older than N seconds, skip waiting for the pod.  Seconds must be greater than 0 to skip.

    --timeout=0s:
        The length of time to wait before giving up, zero means infinite

Usage:
  kubectl drain NODE [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
--------------------------------------------分割结束线----------------------------------------------
#核心步骤
kubectl drain node02 --ignore-daemonsets --force
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
node/node02 already cordoned
Warning: ignoring DaemonSet-managed Pods: calico-system/calico-node-9wv7w, calico-system/csi-node-driver-rsr2w, ingress-nginx/ingress-nginx-controller-48m8c, kube-system/kube-proxy-wgkm6
evicting pod kube-system/coredns-7bdc4cb885-5hw46
evicting pod cpu-top/test0-784f495b5c-2dqdv
evicting pod calico-apiserver/calico-apiserver-866cccf79f-vmbcb
evicting pod calico-system/calico-kube-controllers-789dc4c76b-vbm6v
evicting pod cpu-top/redis-test-5db498bbd-h2mfj
evicting pod default/presentation-856b8578cd-gd28p
evicting pod default/front-end-cfdfbdb95-v7q4t
evicting pod ing-internal/hello-77766974fd-khpjv
I0118 09:49:47.773920   18814 request.go:697] Waited for 1.045639554s due to client-side throttling, not priority and fairness, request: GET:https://11.0.1.111:6443/api/v1/namespaces/cpu-top/pods/test0-784f495b5c-2dqdv
pod/hello-77766974fd-khpjv evicted
pod/calico-kube-controllers-789dc4c76b-vbm6v evicted
pod/presentation-856b8578cd-gd28p evicted
pod/test0-784f495b5c-2dqdv evicted
pod/coredns-7bdc4cb885-5hw46 evicted
pod/calico-apiserver-866cccf79f-vmbcb evicted
pod/front-end-cfdfbdb95-v7q4t evicted
pod/redis-test-5db498bbd-h2mfj evicted
node/node02 drained
--------------------------------------------分割结束线----------------------------------------------
123456789101112131415161718192021222324252627282930313233343536373839404142434445464748495051525354555657585960616263646566676869707172737475767778798081828384858687888990919293949596979899100101102103104
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
kubectl get nodes
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
NAME       STATUS                     ROLES           AGE    VERSION
master01   Ready                      control-plane   242d   v1.28.0
node01     Ready                      <none>          242d   v1.28.0
node02     Ready,SchedulingDisabled   <none>          242d   v1.28.0
--------------------------------------------分割结束线----------------------------------------------
kubectl get pod -A -o wide | grep node02
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
calico-system      calico-node-9wv7w                          1/1     Running   8 (35m ago)    242d   11.0.1.113       node02     <none>           <none>
calico-system      csi-node-driver-rsr2w                      2/2     Running   16 (35m ago)   242d   10.244.140.65    node02     <none>           <none>
ingress-nginx      ingress-nginx-controller-48m8c             1/1     Running   6 (35m ago)    242d   11.0.1.113       node02     <none>           <none>
kube-system        kube-proxy-wgkm6                           1/1     Running   3 (35m ago)    143d   11.0.1.113       node02     <none>           <none>
--------------------------------------------分割结束线----------------------------------------------
1234567891011121314151617
```

# 第12题：节点污点

## 1. 分值权重：4%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context tk8s`

### 2.2 Context

无

### 2.3 Task

检查有多少 nodes 已准备就绪（不包括被打上Taint：NoSchedule的节点），并将数量写入

/opt/DAVIDWATT00402/davidwatt00402.txt文件中。

## 3. 考点解析

（1）污点和容忍

（2）grep的用法

1. **`grep -i` 示例：**
    - `i` 选项用于忽略大小写，即不区分大小写地进行搜索。
    
    ```
    #在文件 example.txt 中搜索包含 "apple" 的行，不区分大小写
    grep -i "apple" example.txt
    12
    ```
    
    如果 `example.txt` 中有 “Apple” 或 “aPpLe” 等形式，都会被匹配。
    
2. **`grep -e` 示例：**
    - `e` 选项用于指定搜索的模式。
    
    ```
    #在文件 example.txt 中搜索包含 "apple" 或 "orange" 的行
    grep -e "apple" -e "orange" example.txt
    12
    ```
    
    这个命令将匹配包含 “apple” 或 “orange” 的行。
    

## 4. 考点参考链接

[污点和容忍度](https://kubernetes.io/zh-cn/docs/concepts/scheduling-eviction/taint-and-toleration/)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context tk8s
kubectl describe nodes | grep -i Taints
echo "2" > /opt/DAVIDWATT00402/davidwatt00402.txt
123
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context tk8s
#核心步骤
#如果使用Taints，可以不用-i;
kubectl describe nodes | grep -i Taints
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Taints:             node-role.kubernetes.io/control-plane:NoSchedule
Taints:             <none>
Taints:             <none>
--------------------------------------------分割结束线----------------------------------------------
echo "2" > /opt/DAVIDWATT00402/davidwatt00402.txt
1234567891011
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
cat /opt/DAVIDWATT00402/davidwatt00402.txt
2
123
```

# 第13题：NodeSelector

## 1. 分值权重：4%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context sk8s`

### 2.2 Context

无

### 2.3 Task

按如下要求调度一个pod:

名称: nginx-davidwatt00401

Image: nginx

nodeSelector: disk=ssd

## 3. 考点解析

NodeSelector的使用

## 4. 考点参考链接

[将 Pod 分配给节点](https://kubernetes.io/zh-cn/docs/tasks/configure-pod-container/assign-pods-nodes/)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context sk8s
#核心步骤
kubectl run nginx-davidwatt00401 --image=nginx --dry-run=client -o yaml > pod-ssd.yaml
vim pod-ssd.yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-davidwatt00401
spec:
  containers:
  - image: nginx
    imagePullPolicy: IfNotPresent #新增内容
    name: nginx-davidwatt00401
  nodeSelector: #重点新增内容
    disk: ssd #重点新增内容
...
kubectl apply -f pod-ssd.yaml
1234567891011121314151617
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context sk8s
#核心步骤
kubectl run nginx-davidwatt00401 --image=nginx --dry-run=client -o yaml > pod-ssd.yaml
vim pod-ssd.yaml
apiVersion: v1
kind: Pod
metadata:
  labels:
    run: nginx-davidwatt00401
  name: nginx-davidwatt00401
spec:
  containers:
  - image: nginx
    imagePullPolicy: IfNotPresent #新增内容
    name: nginx-davidwatt00401
    resources: {}
  nodeSelector: #重点新增内容
    disk: ssd #重点新增内容
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
...
kubectl apply -f pod-ssd.yaml
#其他方法参考
kubectl run nginx-davidwatt00401 --image=nginx --image-pull-policy="IfNotPresent" --overrides='{ "spec": { "nodeSelector": { "disk": "ssd" } } }'
12345678910111213141516171819202122232425
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
kubectl get pod
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
NAME                            READY   STATUS    RESTARTS       AGE
11-factor-app                   1/1     Running   6 (161m ago)   242d
foo                             1/1     Running   6 (161m ago)   242d
front-end-cfdfbdb95-7fpnq       1/1     Running   0              127m
nginx-davidwatt00401            1/1     Running   0              33s
presentation-856b8578cd-vzkxj   1/1     Running   0              127m
--------------------------------------------分割结束线----------------------------------------------
kubectl describe pod nginx-davidwatt00401
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Name:             nginx-davidwatt00401
Namespace:        default
Priority:         0
Service Account:  default
Node:             node01/11.0.1.112
Start Time:       Thu, 18 Jan 2024 11:56:40 +0800
Labels:           run=nginx-davidwatt00401
Annotations:      cni.projectcalico.org/containerID: b49b94403a71d2b056ebc61c49e5b31294aba2a43814e138e7b6cbacfa6a3a58
                  cni.projectcalico.org/podIP: 10.244.196.190/32
                  cni.projectcalico.org/podIPs: 10.244.196.190/32
Status:           Running
IP:               10.244.196.190
IPs:
  IP:  10.244.196.190
Containers:
  nginx-davidwatt00401:
    Container ID:   containerd://5a7bfb1bad8d1b8632624043f0a1009cfe64222409d7579cc0e3557d9629b73c
    Image:          nginx
    Image ID:       sha256:448a08f1d2f94e8db6db9286fd77a3a4f3712786583720a12f1648abb8cace25
    Port:           <none>
    Host Port:      <none>
    State:          Running
      Started:      Thu, 18 Jan 2024 11:56:42 +0800
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-pvzbl (ro)
Conditions:
  Type              Status
  Initialized       True
  Ready             True
  ContainersReady   True
  PodScheduled      True
Volumes:
  kube-api-access-pvzbl:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   BestEffort
Node-Selectors:              disk=ssd
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  92s   default-scheduler  Successfully assigned default/nginx-davidwatt00401 to node01
  Normal  Pulled     91s   kubelet            Container image "nginx" already present on machine
  Normal  Created    91s   kubelet            Created container nginx-davidwatt00401
  Normal  Started    90s   kubelet            Started container nginx-davidwatt00401
--------------------------------------------分割结束线----------------------------------------------
12345678910111213141516171819202122232425262728293031323334353637383940414243444546474849505152535455565758596061626364656667
```

# 第14题：Deployment的扩缩容

## 1. 分值权重：4%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context sk8s`

### 2.2 Context

无

### 2.3 Task

将deployment presentation 扩展至 8 pods

## 3. 考点解析

Deployment的扩缩容

（1）`kubectl scale deployment presentation -h`

（2）`kubectl edit deployment presentation -h`

## 4. 考点参考链接

[Deployment扩缩容](https://kubernetes.io/zh-cn/docs/concepts/workloads/controllers/deployment/#scaling-a-deployment)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context sk8s
kubectl get deployment presentation -o wide
#核心步骤
kubectl scale deployment presentation --replicas=8
deployment.apps/presentation scaled
12345
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context sk8s
kubectl get deployment presentation -o wide
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
NAME           READY   UP-TO-DATE   AVAILABLE   AGE    CONTAINERS   IMAGES              SELECTOR
presentation   1/1     1            1           242d   nginx        vicuu/nginx:hello   app=presentation
--------------------------------------------分割结束线----------------------------------------------
#方法1的学习步骤
kubectl scale -h
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Set a new size for a deployment, replica set, replication controller, or stateful set.

 Scale also allows users to specify one or more preconditions for the scale action.

 If --current-replicas or --resource-version is specified, it is validated before the scale is attempted, and it is guaranteed that the precondition holds true when the scale is sent to the server.

Examples:
  # Scale a replica set named 'foo' to 3
  kubectl scale --replicas=3 rs/foo

  # Scale a resource identified by type and name specified in "foo.yaml" to 3
  kubectl scale --replicas=3 -f foo.yaml

  # If the deployment named mysql's current size is 2, scale mysql to 3
  kubectl scale --current-replicas=2 --replicas=3 deployment/mysql

  # Scale multiple replication controllers
  kubectl scale --replicas=5 rc/example1 rc/example2 rc/example3

  # Scale stateful set named 'web' to 3
  kubectl scale --replicas=3 statefulset/web

Options:
    --all=false:
        Select all resources in the namespace of the specified resource types

    --allow-missing-template-keys=true:
        If true, ignore any errors in templates when a field or map key is missing in the template. Only applies to golang and jsonpath output formats.

    --current-replicas=-1:
        Precondition for current size. Requires that the current size of the resource match this value in order to scale. -1 (default) for no condition.

    --dry-run='none':
        Must be "none", "server", or "client". If client strategy, only print the object that would be sent, without sending it. If server strategy, submit server-side request without persisting the resource.

    -f, --filename=[]:
        Filename, directory, or URL to files identifying the resource to set a new size

    -k, --kustomize='':
        Process the kustomization directory. This flag can't be used together with -f or -R.

    -o, --output='':
        Output format. One of: (json, yaml, name, go-template, go-template-file, template, templatefile, jsonpath, jsonpath-as-json, jsonpath-file).

    -R, --recursive=false:
        Process the directory used in -f, --filename recursively. Useful when you want to manage related manifests organized within the same directory.

    --replicas=0:
        The new desired number of replicas. Required.

    --resource-version='':
        Precondition for resource version. Requires that the current resource version match this value in order to scale.

    -l, --selector='':
        Selector (label query) to filter on, supports '=', '==', and '!='.(e.g. -l key1=value1,key2=value2). Matching objects must satisfy all of the specified label constraints.

    --show-managed-fields=false:
        If true, keep the managedFields when printing objects in JSON or YAML format.

    --template='':
        Template string or path to template file to use when -o=go-template, -o=go-template-file. The template format is golang templates [http://golang.org/pkg/text/template/#pkg-overview].

    --timeout=0s:
        The length of time to wait before giving up on a scale operation, zero means don't wait. Any other values should contain a corresponding time unit (e.g. 1s, 2m, 3h).

Usage:
  kubectl scale [--resource-version=version] [--current-replicas=count] --replicas=COUNT (-f FILENAME | TYPE NAME) [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
--------------------------------------------分割结束线----------------------------------------------
#方法2的学习步骤
kubectl edit -h
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Edit a resource from the default editor.

 The edit command allows you to directly edit any API resource you can retrieve via the command-line tools. It will open the editor defined by your KUBE_EDITOR, or EDITOR environment variables, or fall back to 'vi' for Linux or 'notepad' for Windows. When attempting to open the editor, it will first attempt to use the shell that has been defined in the 'SHELL' environment variable. If this is not defined, the default shell will be used, which is '/bin/bash' for Linux or 'cmd' for Windows.

 You can edit multiple objects, although changes are applied one at a time. The command accepts file names as well as command-line arguments, although the files you point to must be previously saved versions of resources.
 Editing is done with the API version used to fetch the resource. To edit using a specific API version, fully-qualify the resource, version, and group.

 The default format is YAML. To edit in JSON, specify "-o json".

 The flag --windows-line-endings can be used to force Windows line endings, otherwise the default for your operating system will be used.

 In the event an error occurs while updating, a temporary file will be created on disk that contains your unapplied changes. The most common error when updating a resource is another editor changing the resource on the server. When this occurs, you will have to apply your changes to the newer version of the resource, or update your temporary saved copy to include the latest resource version.

Examples:
  # Edit the service named 'registry'
  kubectl edit svc/registry

  # Use an alternative editor
  KUBE_EDITOR="nano" kubectl edit svc/registry

  # Edit the job 'myjob' in JSON using the v1 API format
  kubectl edit job.v1.batch/myjob -o json

  # Edit the deployment 'mydeployment' in YAML and save the modified config in its annotation
  kubectl edit deployment/mydeployment -o yaml --save-config

  # Edit the 'status' subresource for the 'mydeployment' deployment
  kubectl edit deployment mydeployment --subresource='status'

Options:
    --allow-missing-template-keys=true:
        If true, ignore any errors in templates when a field or map key is missing in the template. Only applies to golang and jsonpath output formats.

    --field-manager='kubectl-edit':
        Name of the manager used to track field ownership.

    -f, --filename=[]:
        Filename, directory, or URL to files to use to edit the resource

    -k, --kustomize='':
        Process the kustomization directory. This flag can't be used together with -f or -R.

    -o, --output='':
        Output format. One of: (json, yaml, name, go-template, go-template-file, template, templatefile, jsonpath, jsonpath-as-json, jsonpath-file).

    --output-patch=false:
        Output the patch if the resource is edited.

    -R, --recursive=false:
        Process the directory used in -f, --filename recursively. Useful when you want to manage related manifests organized within the same directory.

    --save-config=false:
        If true, the configuration of current object will be saved in its annotation. Otherwise, the annotation will be unchanged. This flag is useful when you want to perform kubectl apply on this object in the future.

    --show-managed-fields=false:
        If true, keep the managedFields when printing objects in JSON or YAML format.

    --subresource='':
        If specified, edit will operate on the subresource of the requested object. Must be one of [status]. This flag is beta and may change in the future.

    --template='':
        Template string or path to template file to use when -o=go-template, -o=go-template-file. The template format is golang templates [http://golang.org/pkg/text/template/#pkg-overview].

    --validate='strict':
        Must be one of: strict (or true), warn, ignore (or false).              "true" or "strict" will use a schema to validate the input and fail the request if invalid. It will perform server side validation if ServerSideFieldValidation is enabled on the api-server, but will fall back to less reliable client-side validation if not.
        "warn" will warn about unknown or duplicate fields without blocking the request if server-side field validation is enabled on the API server, and behave as "ignore" otherwise.            "false" or "ignore" will not perform any schema validation, silently dropping any unknown or duplicate fields.

    --windows-line-endings=false:
        Defaults to the line ending native to your platform.

Usage:
  kubectl edit (RESOURCE/NAME | -f FILENAME) [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
--------------------------------------------分割结束线----------------------------------------------
#核心步骤
kubectl scale deployment presentation --replicas=8
deployment.apps/presentation scaled
123456789101112131415161718192021222324252627282930313233343536373839404142434445464748495051525354555657585960616263646566676869707172737475767778798081828384858687888990919293949596979899100101102103104105106107108109110111112113114115116117118119120121122123124125126127128129130131132133134135136137138139140141142143144145146147148149150151152153154155156157158159160161162163
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
kubectl get deployment presentation -o wide
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
NAME           READY   UP-TO-DATE   AVAILABLE   AGE    CONTAINERS   IMAGES              SELECTOR
presentation   8/8     8            8           242d   nginx        vicuu/nginx:hello   app=presentation
--------------------------------------------分割结束线----------------------------------------------
kubectl get pod -l app=presentation
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
NAME                            READY   STATUS    RESTARTS        AGE
presentation-856b8578cd-6h9mf   1/1     Running   0               40s
presentation-856b8578cd-cljvz   1/1     Running   0               40s
presentation-856b8578cd-fgjmd   1/1     Running   0               40s
presentation-856b8578cd-gd28p   1/1     Running   6 (7m21s ago)   242d
presentation-856b8578cd-hfjsh   1/1     Running   0               40s
presentation-856b8578cd-mmkjd   1/1     Running   0               40s
presentation-856b8578cd-nbmk5   1/1     Running   0               40s
presentation-856b8578cd-s2hf7   1/1     Running   0               40s
--------------------------------------------分割结束线----------------------------------------------
1234567891011121314151617181920
```

# 第15题：Pod内容器

### 1. 分值权重：4%

### 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context pk8s`

### 2.2 Context

无

### 2.3 Task

创建一个名为davidwatt 的pod, 在pod里面分别为以下每个images单独运行一个app container (注：考试中可能会有1-4个images) : nginx + redis + memcached+consul

## 3. 考点解析

创建包含多个container的Pod

## 4. 考点参考链接

[Pod](https://kubernetes.io/zh-cn/docs/concepts/workloads/pods/)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context pk8s
#核心步骤
kubectl run kucc8 --image=nginx --dry-run=client -o yaml > davidwatt-pod.yaml
vim davidwatt-pod.yaml
apiVersion: v1
kind: Pod
metadata:
  name: davidwatt
spec:
  containers:
  - name: nginx
    image: nginx
    imagePullPolicy: IfNotPresent #需要新增内容；
  - name: redis #需要新增内容；
    image: redis #需要新增内容；
    imagePullPolicy: IfNotPresent #需要新增内容；
  - name: memcached #需要新增内容；
    image: memcached #需要新增内容；
    imagePullPolicy: IfNotPresent #需要新增内容；
  - name: consul #需要新增内容；
    image: consul #需要新增内容；
    imagePullPolicy: IfNotPresent #需要新增内容；
...
kubectl apply -f davidwatt-pod.yaml
123456789101112131415161718192021222324
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context pk8s
kubectl run -h
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Create and run a particular image in a pod.

Examples:
  # Start a nginx pod
  kubectl run nginx --image=nginx

  # Start a hazelcast pod and let the container expose port 5701
  kubectl run hazelcast --image=hazelcast/hazelcast --port=5701

  # Start a hazelcast pod and set environment variables "DNS_DOMAIN=cluster" and "POD_NAMESPACE=default" in the
container
  kubectl run hazelcast --image=hazelcast/hazelcast --env="DNS_DOMAIN=cluster" --env="POD_NAMESPACE=default"

  # Start a hazelcast pod and set labels "app=hazelcast" and "env=prod" in the container
  kubectl run hazelcast --image=hazelcast/hazelcast --labels="app=hazelcast,env=prod"

  # Dry run; print the corresponding API objects without creating them
  kubectl run nginx --image=nginx --dry-run=client

  # Start a nginx pod, but overload the spec with a partial set of values parsed from JSON
  kubectl run nginx --image=nginx --overrides='{ "apiVersion": "v1", "spec": { ... } }'

  # Start a busybox pod and keep it in the foreground, don't restart it if it exits
  kubectl run -i -t busybox --image=busybox --restart=Never

  # Start the nginx pod using the default command, but use custom arguments (arg1 .. argN) for that command
  kubectl run nginx --image=nginx -- <arg1> <arg2> ... <argN>

  # Start the nginx pod using a different command and custom arguments
  kubectl run nginx --image=nginx --command -- <cmd> <arg1> ... <argN>

Options:
    --allow-missing-template-keys=true:
        If true, ignore any errors in templates when a field or map key is missing in the template. Only applies to golang and jsonpath output formats.

    --annotations=[]:
        Annotations to apply to the pod.

    --attach=false:
        If true, wait for the Pod to start running, and then attach to the Pod as if 'kubectl attach ...' were called.
        Default false, unless '-i/--stdin' is set, in which case the default is true. With '--restart=Never' the exit code of the container process is returned.

    --command=false:
        If true and extra arguments are present, use them as the 'command' field in the container, rather than the 'args' field which is the default.

    --dry-run='none':
        Must be "none", "server", or "client". If client strategy, only print the object that would be sent, without sending it. If server strategy, submit server-side request without persisting the resource.

    --env=[]:
        Environment variables to set in the container.

    --expose=false:
        If true, create a ClusterIP service associated with the pod.  Requires `--port`.

    --field-manager='kubectl-run':
        Name of the manager used to track field ownership.

    --image='':
        The image for the container to run.

    --image-pull-policy='':
        The image pull policy for the container.  If left empty, this value will not be specified by the client and defaulted by the server.

    -l, --labels='':
        Comma separated labels to apply to the pod. Will override previous values.

    --leave-stdin-open=false:
        If the pod is started in interactive mode or with stdin, leave stdin open after the first attach completes. By default, stdin will be closed after the first attach completes.

    -o, --output='':
        Output format. One of: (json, yaml, name, go-template, go-template-file, template, templatefile, jsonpath, jsonpath-as-json, jsonpath-file).

    --override-type='merge':
        The method used to override the generated object: json, merge, or strategic.

    --overrides='':
        An inline JSON override for the generated object. If this is non-empty, it is used to override the generated object. Requires that the object supply a valid apiVersion field.

    --pod-running-timeout=1m0s:
        The length of time (like 5s, 2m, or 3h, higher than zero) to wait until at least one pod is running

    --port='':
        The port that this container exposes.

    --privileged=false:
        If true, run the container in privileged mode.

    -q, --quiet=false:
        If true, suppress prompt messages.

    --restart='Always':
        The restart policy for this Pod.  Legal values [Always, OnFailure, Never].

    --rm=false:
        If true, delete the pod after it exits.  Only valid when attaching to the container, e.g. with '--attach' or with '-i/--stdin'.

    --save-config=false:
        If true, the configuration of current object will be saved in its annotation. Otherwise, the annotation will be unchanged. This flag is useful when you want to perform kubectl apply on this object in the future.

    --show-managed-fields=false:
        If true, keep the managedFields when printing objects in JSON or YAML format.

    -i, --stdin=false:
        Keep stdin open on the container in the pod, even if nothing is attached.

    --template='':
        Template string or path to template file to use when -o=go-template, -o=go-template-file. The template format is golang templates [http://golang.org/pkg/text/template/#pkg-overview].

    -t, --tty=false:
        Allocate a TTY for the container in the pod.

Usage:
  kubectl run NAME --image=image [--env="key=value"] [--port=port] [--dry-run=server|client] [--overrides=inline-json] [--command] -- [COMMAND] [args...] [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
--------------------------------------------分割结束线----------------------------------------------
kubectl run kucc8 --image=nginx --dry-run=client -o yaml > davidwatt-pod.yaml
vim davidwatt-pod.yaml
apiVersion: v1
kind: Pod #注意pod这里的p需要大写；
metadata:
  name: davidwatt
spec:
  containers:
  - name: nginx
    image: nginx
    imagePullPolicy: IfNotPresent #需要新增内容；
  - name: redis #需要新增内容；
    image: redis #需要新增内容；
    imagePullPolicy: IfNotPresent #需要新增内容；
  - name: memcached #需要新增内容；
    image: memcached #需要新增内容；
    imagePullPolicy: IfNotPresent #需要新增内容；
  - name: consul #需要新增内容；
    image: consul #需要新增内容；
    imagePullPolicy: IfNotPresent #需要新增内容；
...
kubectl apply -f davidwatt-pod.yaml
123456789101112131415161718192021222324252627282930313233343536373839404142434445464748495051525354555657585960616263646566676869707172737475767778798081828384858687888990919293949596979899100101102103104105106107108109110111112113114115116117118119120121122123124125126127128129130131132133134135136137138139140141142
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
kubectl get pod davidwatt
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
NAME        READY   STATUS    RESTARTS   AGE
davidwatt   4/4     Running   0          11m
--------------------------------------------分割结束线----------------------------------------------
kubectl describe pod davidwatt
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Name:             davidwatt
Namespace:        default
Priority:         0
Service Account:  default
Node:             node02/11.0.1.113
Start Time:       Thu, 18 Jan 2024 16:12:10 +0800
Labels:           <none>
Annotations:      cni.projectcalico.org/containerID: 692e0764b4bb4c0c1a06044c4b3f1aea8eea3116f39a91b17853327806969fb9
                  cni.projectcalico.org/podIP: 10.244.140.71/32
                  cni.projectcalico.org/podIPs: 10.244.140.71/32
Status:           Running
IP:               10.244.140.71
IPs:
  IP:  10.244.140.71
Containers:
  nginx:
    Container ID:   containerd://d864fbf18580534abe90e2387d8ff8c8dabeea105d5b694bd487b0fef1a8c431
    Image:          nginx
    Image ID:       sha256:448a08f1d2f94e8db6db9286fd77a3a4f3712786583720a12f1648abb8cace25
    Port:           <none>
    Host Port:      <none>
    State:          Running
      Started:      Thu, 18 Jan 2024 16:12:11 +0800
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-7q9jw (ro)
  redis:
    Container ID:   containerd://fd063873b6efc675d066e79b25918a5461bc60ed113ef52d1e8f0d8a4c6d19f2
    Image:          redis
    Image ID:       docker.io/library/redis@sha256:b5ddcd52d425a8e354696c022f392fe45fca928f68d6289e6bb4a709c3a74668
    Port:           <none>
    Host Port:      <none>
    State:          Running
      Started:      Thu, 18 Jan 2024 16:13:02 +0800
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-7q9jw (ro)
  memcached:
    Container ID:   containerd://2a97518e356330db79379279d8286ef89bf7e47b1f0877de4fb2341daccfc0b8
    Image:          memcached
    Image ID:       docker.io/library/memcached@sha256:482b94566745f9cf2e524e5a07b6dc948a835fa1f0b35d9ee4aa923133446406
    Port:           <none>
    Host Port:      <none>
    State:          Running
      Started:      Thu, 18 Jan 2024 16:13:16 +0800
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-7q9jw (ro)
  consul:
    Container ID:   containerd://1334a2dfc426b6ef3372a68a52f1963dab7017c26dade7e1e5522c508441f817
    Image:          consul
    Image ID:       sha256:c90b65cf94569cb74e2385cf536270955f34035cbef796424dba86d1c2597cc9
    Port:           <none>
    Host Port:      <none>
    State:          Running
      Started:      Thu, 18 Jan 2024 16:13:16 +0800
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-7q9jw (ro)
Conditions:
  Type              Status
  Initialized       True
  Ready             True
  ContainersReady   True
  PodScheduled      True
Volumes:
  kube-api-access-7q9jw:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   BestEffort
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  11m   default-scheduler  Successfully assigned default/davidwatt to node02
  Normal  Pulled     11m   kubelet            Container image "nginx" already present on machine
  Normal  Created    11m   kubelet            Created container nginx
  Normal  Started    11m   kubelet            Started container nginx
  Normal  Pulling    11m   kubelet            Pulling image "redis"
  Normal  Pulled     10m   kubelet            Successfully pulled image "redis" in 50.593s (50.593s including waiting)
  Normal  Created    10m   kubelet            Created container redis
  Normal  Started    10m   kubelet            Started container redis
  Normal  Pulling    10m   kubelet            Pulling image "memcached"
  Normal  Pulled     10m   kubelet            Successfully pulled image "memcached" in 13.187s (13.187s including waiting)
  Normal  Created    10m   kubelet            Created container memcached
  Normal  Started    10m   kubelet            Started container memcached
  Normal  Pulled     10m   kubelet            Container image "consul" already present on machine
  Normal  Created    10m   kubelet            Created container consul
  Normal  Started    10m   kubelet            Started container consul
--------------------------------------------分割结束线----------------------------------------------
123456789101112131415161718192021222324252627282930313233343536373839404142434445464748495051525354555657585960616263646566676869707172737475767778798081828384858687888990919293949596979899100101102103104105106107108109110111112113
```

# 第16题：PV

## 1. 分值权重：4%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context pvk8s`

### 2.2 Context

无

### 2.3 Task

创建名为app-davidwatt 的PersistentVolume，容量为1Gi，访问模式为ReadWriteOnce，volume 类型为hostPath，位于/srv/app-davidwatt-pv

## 3. 考点解析

创建hostpath类型的PV

> RWX 是 ReadWriteMany，RWO 是 ReadWriteOnce
> 

## 4. 考点参考链接

[配置 Pod 以使用 PersistentVolume 作为存储](https://kubernetes.io/zh-cn/docs/tasks/configure-pod-container/configure-persistent-volume-storage/)

## 5. 操作命令和结果

### 5.1 必背操作命令

本题较为简单，必背操作命令和详细操作步骤相同，参考5.2即可；

### 5.2 详细操作步骤和结果

```
kubectl config use-context pvk8s
vim app-davidwatt-pv.yaml
#复制粘贴官网的pods/storage/pv-volume.yaml文件，按照题目要求进行编辑修改
apiVersion: v1
kind: PersistentVolume
metadata:
  name: app-davidwatt #第一处需要修改，由原来的task-pv-volume修改为题目要求的app-davidwatt；
spec:
  capacity:
    storage: 1Gi #第二处需要修改，由原来的10Gi修改为题目要求的1Gi；
  accessModes:
    - ReadWriteOnce
  hostPath:
    path: "/srv/app-davidwatt-pv" #第三处需要修改，由原来的10Gi修改为题目要求的1Gi；
...
kubectl apply -f app-davidwatt-pv.yaml
12345678910111213141516
```

## 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
kubectl get pv
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
NAME            CAPACITY   ACCESS MODES   RECLAIM POLICY   STATUS      CLAIM   STORAGECLASS      REASON   AGE
app-davidwatt   1Gi        RWO            Retain           Available                                      4s
pv01            10Mi       RWO            Retain           Available           csi-hostpath-sc            242d
--------------------------------------------分割结束线-----------------------------------------------
12345678
```

# 第17题：RBAC

## 1. 分值权重：4%

## 2. 考题内容

### 2.1 设置配置环境

[student@node01] $ `kubectl config use-context rbk8s`

### 2.2 Context

为部署管道创建一个新的ClusterRole并将其绑定到范围为特定的namespace 的特定 ServiceAccount

### 2.3 Task

创建一个名为 deployment-clusterrole 且仅允许创建以下资源类型的新ClusterRole :

- Deployment
- StatefulSet
- DaemonSet

在现有的 namespace app-team1 中创建一个名为 cicd-token 的新ServiceAccount 。

在限于 namespace app-team1中 , 将新的ClusterRole deployment-clusterrole 绑定到新的 ServiceAccount cicd-token。

## 3. 考点解析

RBAC鉴权，注意区分是rolebinding，还是clusterrolebinding；

（1）`kubectl create clusterrole -h`

（2）`kubectl create serviceaccount -h`

（3）`kubectl create rolebinding -h`

## 4. 考点参考链接

[使用 RBAC 鉴权](https://kubernetes.io/docs/reference/access-authn-authz/rbac/#kubectl-create-clusterrole)

## 5. 操作命令和结果

### 5.1 必背操作命令

```
kubectl config use-context rbk8s
kubectl create clusterrole deployment-clusterrole --verb=create --resource=deployment,statefulset,daemonset
kubectl create serviceaccount cicd-token -n app-team1
kubectl create rolebinding cicd-rolebinding --clusterrole=deployment-clusterrole --serviceaccount=app-team1:cicd-token -n app-team1
1234
```

### 5.2 详细操作步骤和结果

```
kubectl config use-context rbk8s
#操作步骤学习1
kubectl create clusterrole -h
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Create a cluster role.

Examples:
  # Create a cluster role named "pod-reader" that allows user to perform "get", "watch" and "list" on pods
  kubectl create clusterrole pod-reader --verb=get,list,watch --resource=pods

  # Create a cluster role named "pod-reader" with ResourceName specified
  kubectl create clusterrole pod-reader --verb=get --resource=pods --resource-name=readablepod
--resource-name=anotherpod

  # Create a cluster role named "foo" with API Group specified
  kubectl create clusterrole foo --verb=get,list,watch --resource=rs.apps

  # Create a cluster role named "foo" with SubResource specified
  kubectl create clusterrole foo --verb=get,list,watch --resource=pods,pods/status

  # Create a cluster role name "foo" with NonResourceURL specified
  kubectl create clusterrole "foo" --verb=get --non-resource-url=/logs/*

  # Create a cluster role name "monitoring" with AggregationRule specified
  kubectl create clusterrole monitoring --aggregation-rule="rbac.example.com/aggregate-to-monitoring=true"

Options:
    --aggregation-rule=:
        An aggregation label selector for combining ClusterRoles.

    --allow-missing-template-keys=true:
        If true, ignore any errors in templates when a field or map key is missing in the template. Only applies to golang and jsonpath output formats.

    --dry-run='none':
        Must be "none", "server", or "client". If client strategy, only print the object that would be sent, without sending it. If server strategy, submit server-side request without persisting the resource.

    --field-manager='kubectl-create':
        Name of the manager used to track field ownership.

    --non-resource-url=[]:
        A partial url that user should have access to.

    -o, --output='':
        Output format. One of: (json, yaml, name, go-template, go-template-file, template, templatefile, jsonpath, jsonpath-as-json, jsonpath-file).

    --resource=[]:
        Resource that the rule applies to

    --resource-name=[]:
        Resource in the white list that the rule applies to, repeat this flag for multiple items

    --save-config=false:
        If true, the configuration of current object will be saved in its annotation. Otherwise, the annotation will be unchanged. This flag is useful when you want to perform kubectl apply on this object in the future.

    --show-managed-fields=false:
        If true, keep the managedFields when printing objects in JSON or YAML format.

    --template='':
        Template string or path to template file to use when -o=go-template, -o=go-template-file. The template format is golang templates [http://golang.org/pkg/text/template/#pkg-overview].

    --validate='strict':
        Must be one of: strict (or true), warn, ignore (or false).              "true" or "strict" will use a schema to validate the input and fail the request if invalid. It will perform server side validation if ServerSideFieldValidation is enabled on the api-server, but will fall back to less reliable client-side validation if not.
        "warn" will
        warn about unknown or duplicate fields without blocking the request if server-side field validation is enabled on the API server, and behave as "ignore" otherwise.            "false" or "ignore" will not perform any schema validation, silently dropping any unknown or duplicate fields.

    --verb=[]:
        Verb that applies to the resources contained in the rule

Usage:
  kubectl create clusterrole NAME --verb=verb --resource=resource.group [--resource-name=resourcename] [--dry-run=server|client|none] [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
--------------------------------------------分割结束线----------------------------------------------
#核心步骤1
kubectl create clusterrole deployment-clusterrole --verb=create --resource=deployment,statefulset,daemonset
clusterrole.rbac.authorization.k8s.io/deployment-clusterrole created
...
#操作步骤学习2
kubectl create serviceaccount -h
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Create a service account with the specified name.

Aliases:
serviceaccount, sa

Examples:
  # Create a new service account named my-service-account
  kubectl create serviceaccount my-service-account

Options:
    --allow-missing-template-keys=true:
        If true, ignore any errors in templates when a field or map key is missing in the template. Only applies to golang and jsonpath output formats.

    --dry-run='none':
        Must be "none", "server", or "client". If client strategy, only print the object that would be sent, without sending it. If server strategy, submit server-side request without persisting the resource.

    --field-manager='kubectl-create':
        Name of the manager used to track field ownership.

    -o, --output='':
        Output format. One of: (json, yaml, name, go-template, go-template-file, template, templatefile, jsonpath, jsonpath-as-json, jsonpath-file).

    --save-config=false:
        If true, the configuration of current object will be saved in its annotation. Otherwise, the annotation will be unchanged. This flag is useful when you want to perform kubectl apply on this object in the future.

    --show-managed-fields=false:
        If true, keep the managedFields when printing objects in JSON or YAML format.

    --template='':
        Template string or path to template file to use when -o=go-template, -o=go-template-file. The template format is golang templates [http://golang.org/pkg/text/template/#pkg-overview].

    --validate='strict':
        Must be one of: strict (or true), warn, ignore (or false).              "true" or "strict" will use a schema to validate the input and fail the request if invalid. It will perform server side validation if ServerSideFieldValidation is enabled on the api-server, but will fall back to less reliable client-side validation if not.
        "warn" will warn about unknown or duplicate fields without blocking the request if server-side field validation is enabled on the API server, and behave as "ignore" otherwise.            "false" or "ignore" will not perform any schema validation, silently dropping any unknown or duplicate fields.

Usage:
  kubectl create serviceaccount NAME [--dry-run=server|client|none] [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
--------------------------------------------分割结束线----------------------------------------------
#核心步骤2
kubectl create serviceaccount cicd-token -n app-team1
serviceaccount/cicd-token created
...
#操作步骤学习3
kubectl create rolebinding -h
--------------------------------------------分割起始线----------------------------------------------
#操作结果如下：
Create a role binding for a particular role or cluster role.

Examples:
  # Create a role binding for user1, user2, and group1 using the admin cluster role
  kubectl create rolebinding admin --clusterrole=admin --user=user1 --user=user2 --group=group1

  # Create a role binding for serviceaccount monitoring:sa-dev using the admin role
  kubectl create rolebinding admin-binding --role=admin --serviceaccount=monitoring:sa-dev

Options:
    --allow-missing-template-keys=true:
        If true, ignore any errors in templates when a field or map key is missing in the template. Only applies to golang and jsonpath output formats.

    --clusterrole='':
        ClusterRole this RoleBinding should reference

    --dry-run='none':
        Must be "none", "server", or "client". If client strategy, only print the object that would be sent, without sending it. If server strategy, submit server-side request without persisting the resource.

    --field-manager='kubectl-create':
        Name of the manager used to track field ownership.

    --group=[]:
        Groups to bind to the role. The flag can be repeated to add multiple groups.

    -o, --output='':
        Output format. One of: (json, yaml, name, go-template, go-template-file, template, templatefile, jsonpath, jsonpath-as-json, jsonpath-file).

    --role='':
        Role this RoleBinding should reference

    --save-config=false:
        If true, the configuration of current object will be saved in its annotation. Otherwise, the annotation will be unchanged. This flag is useful when you want to perform kubectl apply on this object in the future.

    --serviceaccount=[]:
        Service accounts to bind to the role, in the format <namespace>:<name>. The flag can be repeated to add multiple service accounts.

    --show-managed-fields=false:
        If true, keep the managedFields when printing objects in JSON or YAML format.

    --template='':
        Template string or path to template file to use when -o=go-template, -o=go-template-file. The template format is golang templates [http://golang.org/pkg/text/template/#pkg-overview].

    --user=[]:
        Usernames to bind to the role. The flag can be repeated to add multiple users.

    --validate='strict':
        Must be one of: strict (or true), warn, ignore (or false).              "true" or "strict" will use a schema to validate the input and fail the request if invalid. It will perform server side validation if ServerSideFieldValidation is enabled on the api-server, but will fall back to less reliable client-side validation if not.
        "warn" will warn about unknown or duplicate fields without blocking the request if server-side field validation is enabled on the API server, and behave as "ignore" otherwise.            "false" or "ignore" will not perform any schema validation, silently dropping any unknown or duplicate fields.

Usage:
  kubectl create rolebinding NAME --clusterrole=NAME|--role=NAME [--user=username] [--group=groupname] [--serviceaccount=namespace:serviceaccountname] [--dry-run=server|client|none] [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
--------------------------------------------分割结束线----------------------------------------------
#核心步骤3
kubectl create rolebinding cicd-rolebinding --clusterrole=deployment-clusterrole --serviceaccount=app-team1:cicd-token -n app-team1
rolebinding.rbac.authorization.k8s.io/cicd-rolebinding created
123456789101112131415161718192021222324252627282930313233343536373839404142434445464748495051525354555657585960616263646566676869707172737475767778798081828384858687888990919293949596979899100101102103104105106107108109110111112113114115116117118119120121122123124125126127128129130131132133134135136137138139140141142143144145146147148149150151152153154155156157158159160161162163164165166167168169170171172173174175176177178179180181182183184185186187188
```

# 6. 验证命令和结果

```
#检查操作是否成功，考试时如果时间紧张可以不用检查；
kubectl describe rolebinding cicd-rolebinding -n app-team1
--------------------------------------------分割起始线-----------------------------------------------
#操作结果如下：
Name:         cicd-rolebinding
Labels:       <none>
Annotations:  <none>
Role:
  Kind:  ClusterRole
  Name:  deployment-clusterrole
Subjects:
  Kind            Name        Namespace
  ----            ----        ---------
  ServiceAccount  cicd-token  app-team1
--------------------------------------------分割结束线-----------------------------------------------
123456789101112131415
```

# 个人练习错误备忘

- RBAC那道题，记得加命名空间；
- CPU那道题，记得加上-A；
- NetworkPolicy那道题，记得给ns打上标签；
- 服务暴露那道题，ports跟image是一列的，记得确认下Deployment和service的SELECTOR是否一致；
- Ingress那道题，记得看下是否已经存在ingressclass，且需要写上ns；
- nodeselector那道题，注意nodeSelector的n需要小写，且与container对齐；
- 多容器那道题，每个容器前都要有- ，且最好IfNotPresent；
- Sidecar日志那道题，先备份，然后先删除已有的pod然后再apply；
- etcd那道题，恢复需要sudo权限才能操作；
- NotReady那道题，先start后enable；
- 集群升级那道题，可参考官网，但记得加上 --ignore-daemonsets和–etcd-upgrade=false；

### 官网链接参考：

[常见问题：CKA 和 CKAD 和 CKS](https://docs.linuxfoundation.org/tc-docs/certification/faq-cka-ckad-cks)

[重要说明：CKA 和 CKAD](https://docs.linuxfoundation.org/tc-docs/certification/tips-cka-and-ckad)

[LF 认证考试攻略｜认证考试流程全介绍–购买、注册及预约考试篇（建议收藏）](https://training.linuxfoundation.cn/news/308)

[LF 认证考试攻略｜认证考试前准备全介绍–自助签到篇（建议收藏）](https://training.linuxfoundation.cn/news/309)

[LF 认证考试攻略｜认证考试前准备全介绍–考试DOs & DON’Ts（建议收藏)](https://training.linuxfoundation.cn/news/310)

[LF 认证考试攻略｜认证考试流程全介绍–检查系统环境 + 下载PSI浏览器篇（建议收藏）](https://training.linuxfoundation.cn/news/307)

[PSI 在线监考经验](https://psi.wistia.com/medias/5kidxdd0ry)

![https://www.notion.so./【CKA认证考试参考题库及万字详解】_cka题库-CSDN博客_files/closeBt.png](https://www.notion.so./【CKA认证考试参考题库及万字详解】_cka题库-CSDN博客_files/closeBt.png)