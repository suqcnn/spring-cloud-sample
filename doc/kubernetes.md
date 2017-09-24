### 简介
Kubernetes是容器编排和调度领域的王者，
它击败了竞争对手Docker Swarm和Apache Mesos，开启了闪耀的未来，
微服务可以自修复，可以自动扩展，可以跨zone，region甚至跨云供应商进行federate。
在这样的云原生应用程序的新纪元里，能够以简单的方式洞察服务之间是如何交互的变得日益重要——这可和大海捞针般大范围寻找导致性能问题的某个特定的原因是不一样的。

### 与springcloud关系
在微服务旅程中，
Spring Cloud独自拥有一个小范围，为了一个完整的微服务体验，
开发人员也将需要考虑自动部署、调度、资源管理、进程隔离、自我修复、构建管道等等。
对于这点，我认为比较单独Spring Cloud和Kubernetes是不公平的，
一个更公平的比较是Spring Cloud+ Cloud Foundry (或Docker Swarm)与Kubernetes。
但那也意味着一个完整的端到端微服务体验，
Spring Cloud必须补充一个应用程序平台，就像Kubernetes那样！！！！

两个平台在核心领域都很强，并且在其他领域改进。Spring Cloud可以快速使用、对开发者友好的平台，
然而Kubernetes对DevOps友好，艰难的学习曲线，但是覆盖更广泛的微服务障碍。

通过这样一种结合，Spring提供应用程序打包，Docker和Kubernetes提供部署和调度。

Spring通过Hystrix线程池提供应用程序内隔板，Kubernetes通过资源、进程和命名空间隔离提供隔板。Spring为每个微服务提供健康终端，Kubernetes执行健康检查并且为健康服务通信路由。
Spring外部化且升级配置，Kubernetes给每个微服务分配配置。这样的还有很多。

https://www.kubernetes.org.cn/img/2016/12/20161220145337.jpg

我最喜欢哪个微服务平台？两个都喜欢。
我喜欢Spring框架带来的开发者体验。全部都是注解驱动的，类库覆盖所有种类的功能需求。
我也喜欢Apache Camel（宁愿Spring Spring Integration）为集成、连接器、消息、路由、弹性和在应用层的容错所做的。
然后与集群和多种应用程序实例管理，我更喜欢Kubernetes神奇的力量。
每当有一个功能重叠，例如服务发现、负载均衡、配置管理，我试着使用Kubernetes提供的多语言原语。

### 技术栈对比
微服务关注方面有：配置管理、服务发现与负载平衡、弹性和失败冗余、API管理、安全服务、中央集中日志、集中测量、分布式跟踪、调度部署和自动扩展self Healing等几个方面。

根据这些观点，得出Spring Cloud和Kubernetes两个平台映射：


1.配置管理：配置服务器、Consul和Netflix Archaius（Spring Cloud）；Kubernetes ConfigMap&Secrets ;

2.服务发现: Netflix Eureka,Hashicorp Consul(Spring Cloud);Kubernetes Service&Ingress Resource;

3.负载平衡：Netflix Ribbon（Spring Cloud）；Kubernetes Service

4.API网关：Netflix Zuul（SpringCloud）；Kubernetes Service&Ingress Resource

5.安全服务：SpringCloud Security

6.中央集中日志：ELK Stack（LogStash）；EFKstack（Fluentd）。

7.集中测量：Netflix Spectator& Atlas；Heapster、Prometheus、Grafana。

8.分布式跟踪：SpringCloud Sleuth，Zipkin；OpenTracing、Zipkin

9.弹性和失败冗余：Netflix Hystrix、Turbine&Ribbon；Kubernetes Health Check&resource isolation

10.自动扩展self Healing：Spring Cloud无；Kubernetes Health Check、SelfHealing、Autoscaling

11.打包 部署和调度部署：Spring Boot；Docker／Rkt、Kubernetes Scheduler&Deployment

12.任务工作管理：Spring Batch；Kubernetes Jobs&Scheduled Jobs

13.单个应用：Spring Cloud Cluster ；Kubernetes Pods


有些情况下这两个平台是互补的，并且可以结合在一起，创造一个更加强大的解决方案,例如，Spring Boot提供了用于构建单个JAR应用程序包的Maven插件。
结合Docker和Kubernetes的声明性部署和调度功能，使微服务运行变得轻而易举。 
类似地，Spring Cloud具有应用程序库，用于使用Hystrix（断路器）和Ribbon（用于负载平衡）创建弹性的，容错的微服务。
但是单单这是不够的，当它与Kubernetes的健康检查，进程重新启动和自动扩展功能相结合时，微服务成为一个真正的抗脆弱的系统。


有了这样的组合，Spring提供了应用程序打包，而Docker和Kubernetes提供了部署和调度。
 Spring通过Hystrix线程池提供应用程序防火墙，Kubernetes通过资源，进程和命名空间隔离提供防火墙。
 Spring为每个微服务提供健康端点，Kubernetes执行健康检查和流量路由到健康的服务。 
Spring负责外部化和更新配置，Kubernetes将配置分发到每个微服务。 


### 非常推荐度的讲解Kubernetes的好书

《Kubernetes权威指南：从Docker到Kubernetes实践全接触》











