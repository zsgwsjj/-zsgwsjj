### Spring相关知识点

#### 1.spring中bean的作用域
**singleton：**

Spring IoC容器中只会存在一个共享的Bean实例，无论有多少个Bean引用它，始终指向同一对象。Singleton作用域是Spring中的缺省作用域。

**prototype：**
每次通过Spring容器获取prototype定义的bean时，容器都将创建一个新的Bean实例，每个Bean实例都有自己的属性和状态，而singleton全局只有一个对象。

**request**
在一次Http请求中，容器会返回该Bean的同一实例。而对不同的Http请求则会产生新的Bean，而且该bean仅在当前Http Request内有效。

**session**
在一次Http Session中，容器会返回该Bean的同一实例。而对不同的Session请求则会创建新的实例，该bean实例仅在当前Session内有效。

**global session**
在一个全局的Http Session中，容器会返回该Bean的同一个实例，仅在使用portlet context时有效。


#### 2.Spring框架中的设计模式

* 代理模式：在AOP和remoting中被用的比较多。
* 单例模式：在spring配置文件中定义的bean默认为单例模式。
* 模板方法模式：用来解决代码重复的问题。
* 前端控制器模式：Spring提供了DispatcherServlet来对请求进行分发。
* 依赖注入模式：贯穿于BeanFactory / ApplicationContext接口的核心理念。
* 工厂模式：BeanFactory用来创建对象的实例。
