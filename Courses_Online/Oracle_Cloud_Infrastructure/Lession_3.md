＃OCI计算服务

## 裸机裸机

一个没有任何虚拟化功能的物理服务器，您必须设置一个虚拟化层，然后您必须管理所有事情：操作系统，运行时等。Oracle提供了现成的虚拟化功能< SUP > ** 1 ** </上> 


###用例

具有OCI的所有安全性，功能，弹性和可伸缩性的直接硬件访问。

- 工作负载是性能密集型性能密集型工作负载-工作负载未虚拟化-需要一个特定的虚拟机管理程序的工作负载-需要自带酒水许可工作负载





## 专用虚拟主机专用虚拟主机

 主机服务器，具有虚拟化功能，您可以在其上运行VM。

## 虚拟机

虚拟机是具有基于虚拟机管理程序的虚拟化的主机服务器上的访客。 

###                                                                                                                                                         用例

虚拟机需要工作-操作系统路径管理，安全性配置，监视，应用程序配置和扩展，以处理可变流量，如果您要：
- 控制环境的各个方面-在Windows或Linux上运行的旧版应用程序-将应用程序从本地迁移到OCI




## 容器引擎

您要管理代码，然后当然要管理App容器< sup > ** 2 ** </ sup>。 


## 函数

您只需在其中编写代码的Oracle函数。您可以使用不同的语言编写代码，而不必担心任何基础架构。
- 小但功能强大的代码块-作为Docker映像存储在指定的Docker初始化中。-为响应CLI命令或签名的HTTP请求而调用（以响应CLI命令或签名的HTTP请求而调用）


<div style =“总是分页后中断；”> </ div> ##实例基础


计算实例相对其他OCI服务，例如数据块量和虚拟云网络（VCN）

！[instance]（https://imgur.com/zrghb9s.png ）

## 垂直缩放

支持按比例放大和按比例缩小实例形状（实例尺寸），在调整实例大小之前必须停止实例。

## 自动缩放
这实际上是水平缩放。通过自动配置从分割黄金映像启用**虚拟机的扩展部署**，称为横向扩展或垂直扩展。

！[横向扩展或初步扩展]（https://imgur.com/YbKBZMG.png ）

### 如何自动缩放

![How to autoscaling](https://imgur.com/SZ5sl1f.png)
1. You have an instance running --> what you do is create **a configuration**.
The configuration is nothing but an operating system image, your metadata, storage disks, all  that stuff. It basically earns about what you  instance looks like. You're creating this thing called a *gold image* here.

2. The take this configuration and you create what is called an **instance pool**  and  as you can  see here, instead of one instance, now we have two. And you could do many more.

3. Put these instances in different ADs. Then define your **scaling rules** to  manage hundreds of VMs together as one unit. 


##  VM vs Container 

There were some downsides to VM, you were **repeating the operating system** everywhere. And so these became **bulky** (笨重的). For example if you have 10 VMs, basically you're packaging the operating system 10 times.

The concept of containers where we raised the abstraction one more level, and now we **abstract/virtualize** the **operating system**.  It **shares** the **kernel** or the **operating system** with other containers.

![VM vs Container ](https://imgur.com/ZIPLBR8.png)





---
<sup>**1:**</sup> **off-box virtualization:**  we off-load network and storage to a separate hardware card in the server. People also  call it  as  custom  silicon. 我们把网络和储存卸货到一个单独的硬件卡上.

<sup>**2 :**</sup> **App container:** is a container runtime which executes container and manages container images on a node. The most widely, known app container or container runtime is Docker.



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg5MDIzMTcxMiwtNDEwNjI3NzA3XX0=
-->