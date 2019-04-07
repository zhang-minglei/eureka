Eureka
=====
> eureka-client注册流程  

- 主要类是：[DiscoveryClient](./eureka-client/src/main/java/com/netflix/discovery/DiscoveryClient.java)，加了一些注释，可以方便理解
- 查看它的构造类，可以发现它初始化了一些信息和三个线程池，然后调用了**initScheduledTasks**方法
- initScheduledTasks流程可以参照流程图[eureka-client注册流程图](./images/eureka-client注册流程.jpg)

> eureka-client注销流程

- 主要的类是：[DiscoveryClient](./eureka-client/src/main/java/com/netflix/discovery/DiscoveryClient.java)，方法是```shutdown```
- 它调用了内部的```unregister```方法
- 然后通过http请求调用服务端


> eureka-server端注册流程

- 主要类是：[ApplicationResource](./eureka-core/src/main/java/com/netflix/eureka/resources/ApplicationResource.java)，http请求到该类的addInstance方法
- 注册流程可以参考流程图[eureka-server端注册流程](./images/Eureka-server端%20服务注册流程.jpg)

> eureka-server端注销流程

- 主要类：[InstanceResource](./eureka-core/src/main/java/com/netflix/eureka/resources/InstanceResource.java)，方法：``cancelLease``
- 注销流程可以参考流程图[eureka-client注销流程](./images/eureka-client注销流程.jpg)