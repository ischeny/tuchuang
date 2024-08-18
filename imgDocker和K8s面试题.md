## Docker & K8s面试题

---

**Docker 和虚拟机有什么区别？**

**答案：** Docker 容器共享主机操作系统内核，而虚拟机则模拟完整的计算机系统，每个虚拟机都有自己的操作系统。

**Docker 镜像和容器有什么区别？**

**答案：** Docker 镜像是一个静态的文件，用于构建 Docker 容器；Docker 容器是运行时实例化的镜像，包含应用程序和其依赖项。

**Docker Registry 是什么？**

**答案：** Docker Registry 是用于存储 Docker 镜像的集中式存储库，可以是公共的（如 Docker Hub）或私有的。

**Docker 的网络模式有哪些？**

**答案：** Docker 的网络模式包括 bridge、host、none、container等。

**如何查看 Docker 容器的日志？**

**答案：** 可以使用 Docker CLI 的 `docker logs` 命令来查看容器的日志。

**Docker 中的镜像层是什么？**

**答案：** Docker 镜像由多个只读层（Layer）组成，每个层都包含了对文件系统的修改。容器启动时会在最顶层添加一个可写层，用于存储容器的运行时状态。

**Docker 中的 Dockerfile 中的 WORKDIR 指令的作用是什么？**

**答案：** WORKDIR 指令用于设置容器中的工作目录，后续的命令会在该目录下执行。

**Docker 中的 Dockerfile 中的 COPY 指令和 ADD 指令有什么区别？**

**答案：** COPY 指令用于复制文件和目录到容器中，而 ADD 指令除了复制文件和目录外，还支持解压文件、URL 下载等功能。

**如何删除 Docker 中的未使用镜像和容器？**

**答案：** 可以使用 Docker CLI 的 `docker image prune` 和 `docker container prune` 命令来删除未使用的镜像和容器。

**Docker 中的容器和虚拟机的性能差异是什么？**

**答案：** Docker 容器与虚拟机相比更加轻量级，启动更快，占用资源更少，但不具备完全隔离性。虚拟机则更加隔离，但启动和资源消耗较多。

---

**Kubernetes 中的 Service 是什么？它的作用是什么？**

**答案：** Service 是一种抽象，用于定义一组 Pod 的访问方式。它可以提供负载均衡、服务发现和路由功能，使得应用程序能够稳定地对外提供服务。

**Kubernetes 中的 Ingress 是什么？它的作用是什么？**

**答案：** Ingress 是 Kubernetes 中用于管理集群入口流量的 API 对象，它允许外部流量访问集群中的服务，并提供了路由、负载均衡、SSL 终止等功能。

**Kubernetes 中的 Deployment 和 StatefulSet 有什么区别？**

**答案：** Deployment 用于管理无状态应用程序的部署和伸缩，而 StatefulSet 用于管理有状态应用程序的部署和伸缩，它提供了稳定的网络标识和有序的部署和扩展。

**Kubernetes 中的 Namespace 是什么？它的作用是什么？**

**答案：** Namespace 是 Kubernetes 中用于多租户和资源隔离的一种机制，它可以将集群中的资源划分为多个逻辑分区，以便不同的用户或团队能够独立使用和管理资源。

**Kubernetes 中的 Secret 和 ConfigMap 是什么？它们的作用是什么？**

**答案：** Secret 用于存储敏感数据，如密码、密钥等，以 Base64 编码形式存储在 etcd 中；ConfigMap 用于存储非敏感的配置信息，如环境变量、配置文件等，以键值对的形式存储在 etcd 中。

**Kubernetes 中的 RBAC 是什么？它的作用是什么？**

**答案：** RBAC（Role-Based Access Control）是 Kubernetes 中的一种访问控制机制，用于定义和管理用户对集群资源的访问权限，通过角色、角色绑定和授权规则来实现对资源的控制。

**Kubernetes 中的 PersistentVolume 和 PersistentVolumeClaim 是什么？它们的作用是什么？**

**答案：** PersistentVolume 用于存储集群中的持久化数据，而 PersistentVolumeClaim 用于声明和请求 PersistentVolume，使得 Pod 能够使用持久化存储。

**Kubernetes 中的 HorizontalPodAutoscaler 是什么？它的作用是什么？**

**答案：** HorizontalPodAutoscaler 用于根据资源利用率或自定义指标自动调整 Pod 的副本数量，以保持应用程序的性能和可用性。

**Kubernetes 中的 DaemonSet 是什么？它的作用是什么？**

**答案：** DaemonSet 是 Kubernetes 中的一种控制器，用于确保集群中的每个节点上都运行一个副本的 Pod，通常用于运行守护进程或基础设施服务。

**Kubernetes 中的 CNI（Container Network Interface）是什么？它的作用是什么？**

**答案：** CNI 是 Kubernetes 中的一种网络插件接口，用于实现容器网络的配置和管理，支持各种不同的容器网络实现，如 Calico、Flannel、Cilium 等。

**Kubernetes 中的 Pod 的 QoS 类型有哪些？它们的区别是什么？**

**答案：** Kubernetes 中的 Pod 的 QoS（Quality of Service）类型包括 Guaranteed、Burstable 和 BestEffort 三种，分别对应着严格保证、可扩展和最佳尝试的资源分配策略。

**Pod有哪些状态？**

1. **ContainerCreating（容器创建中）：** Pod 的容器正在创建中，还未完全准备好。
2. **Terminating（终止中）：** Pod 正在被终止，但尚未完全清理完成。
3. **ImagePullBackOff（镜像拉取失败）：** Pod 无法从容器镜像仓库中拉取所需的镜像，可能是因为镜像不存在或拉取过程中发生了错误。
4. **ErrImagePull（镜像拉取错误）：** Pod 在尝试拉取容器镜像时遇到了错误，可能是由于镜像仓库的凭据错误、网络问题等。
5. **ImageInspectError（镜像检查错误）：** Pod 在尝试检查容器镜像时遇到了错误，可能是由于镜像不存在或格式不正确。
6. **CrashLoopBackOff（容器崩溃回退）：** Pod 中的容器持续崩溃并重新启动，导致 Pod 进入了一个循环状态。
7. **OOMKilled（内存超限）：** Pod 中的容器由于内存使用超过限制而被系统终止。
8. **Pending（等待中）：** Pod 已被创建，但尚未分配到节点上运行。
9. **Running（运行中）：** Pod 已经被调度到节点上并且至少有一个容器正在运行。
10. **Succeeded（成功）：** Pod 中的所有容器都已成功执行并且已退出（退出状态码为 0）。
11. **Failed（失败）：** Pod 中的所有容器都已经退出，并且至少有一个容器是因为错误而退出（退出状态码不为 0）。
12. **Unknown（未知）：** Kubernetes 无法获取 Pod 的当前状态，可能由于与节点通信失败等原因导致。

**k8s中有哪些Controller ？**

1. **ReplicaSet 控制器：** 确保在集群中维护指定数量的 Pod 副本，用于实现水平扩展和高可用性。
2. **Deployment 控制器：** 用于管理应用程序的部署和更新过程，通过 ReplicaSet 来管理 Pod 副本。
3. **StatefulSet 控制器：** 用于管理有状态应用程序的部署和更新过程，提供了稳定的网络标识和有序的 Pod 部署和扩展。
4. **DaemonSet 控制器：** 确保在集群中的每个节点上运行一个副本的 Pod，通常用于运行守护进程或基础设施服务。
5. **Job 控制器：** 管理一次性任务的运行，确保任务成功完成后自动清理相关的 Pod。
6. **CronJob 控制器：** 管理周期性任务的运行，根据预定的时间表自动创建和销毁相关的 Job。
7. **HorizontalPodAutoscaler（HPA）控制器：** 根据资源利用率或自定义指标自动调整 Pod 的副本数量，以保持应用程序的性能和可用性。
8. **PodDisruptionBudget（PDB）控制器：** 用于限制在维护或故障情况下允许终止的 Pod 数量，以确保应用程序的可用性。
9. **NetworkPolicy 控制器：** 用于定义和管理网络策略，控制 Pod 之间和 Pod 与外部网络之间的通信。
10. **Ingress 控制器：** 管理集群入口流量的路由和负载均衡，允许外部流量访问集群中的服务。
11. **PV（PersistentVolume） 控制器：** 管理持久卷（PersistentVolume）对象的生命周期，负责动态分配、回收和绑定 PV。
12. **PVC（PersistentVolumeClaim） 控制器：** 管理持久卷声明（PersistentVolumeClaim）对象的生命周期，负责将 PVC 绑定到 PV。
13. **StorageClass 控制器：** 管理存储类（StorageClass）对象，用于定义动态存储卷的配置和参数。
14. **Service 控制器：** 确保集群中 Service 对象的状态与定义一致，提供负载均衡和服务发现功能。
15. **Endpoint 控制器：** 管理 Endpoint 对象，将 Service 与后端 Pod 的关联关系转换为网络端点信息。

**使用 Kubernetes 实现自动伸缩，例如通过 HorizontalPodAutoscaler 控制器根据 CPU 使用率自动扩展 Pod 的副本数量。**

```
apiVersion: autoscaling/v1
kind: HorizontalPodAutoscaler
metadata:
  name: nginx-autoscaler
spec:
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: nginx-deployment
  minReplicas: 1
  maxReplicas: 10
  targetCPUUtilizationPercentage: 50
```

**请说一下kubernetes针对pod资源对象的健康监测机制？**

**1） livenessProbe探针**

可以根据用户自定义规则来判定pod是否健康，如果livenessProbe探针探测到容器不健康，则kubelet会根据其重启策略来决定是否重启，如果一个容器不包含livenessProbe探针，则kubelet会认为容器的livenessProbe探针的返回值永远成功。

**2） ReadinessProbe探针**

同样是可以根据用户自定义规则来判断pod是否健康，如果探测失败，控制器会将此pod从对应service的endpoint列表中移除，从此不再将任何请求调度到此Pod上，直到下次探测成功。

**如何控制滚动更新过程？**

**maxSurge**：此参数控制滚动更新过程，副本总数超过预期pod数量的上限。可以是百分比，也可以是具体的值。默认为1。

**maxUnavailable**：此参数控制滚动更新过程中，不可用的Pod的数量。

**简述kube-proxy作用?**

kube-proxy的作用主要是负责service的实现,具体来说,就是实现了内部从pod到service和外部的从node port向service的访问

**简述kube-proxy ipvs和iptables的异同?**

答：iptables 与 IPVS 都是基于 Netfilter 实现的，但因为定位不同，二者有着本质的

差别：iptables 是为防火墙而设计的；IPVS 则专门用于高性能负载均衡，并使用更高效的数据结构（Hash 表），允许几乎无限的规模扩张。

**简述Kubernetes中什么是静态Pod?**

答：静态 pod 是由 kubelet 进行管理的仅存在于特定 Node的Pod，他们不能通过 API Server 进行管理，无法与 ReplicationController、Deployment 或者DaemonSet 进行关联，并且 kubelet 无法对他们进行健康检查。静态 Pod 总是由kubelet 进行创建，并且总是在 kubelet 所在的 Node 上运行

**简述Kubernetes初始化容器（init container）?**

init container的运行方式与应用容器不同，它们必须先于应用容器执行完成，当设置了多个init container时，将按顺序逐个运行，并且只有前一个init container运行成功后才能运行后一个init container。当所有init container都成功运行后，Kubernetes才会初始化Pod的各种信息，并开始创建和运行应用容器。
