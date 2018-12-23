This is my notes about **Java Spring MVC**. 
Content is about 30 minutes read, its purpose is:
- To refresh your memory if you already worked on it. 
- Or if you are totally new, it will give you an overview, so you can kick start your first Java Spring MVC application.

## # Installation
Windows:
 - [ ] JDK
 - [ ] Download Spring libraries (then add to build path)


## # ClassPathXmlApplicationContext

At first, in Java Spring Core module, there is a  Bean Factory (an objects container). You can imagine the Bean is like Object in OOP. BeanFactory allows you to access objects defined in Xml bean configuration file. 

> So why using object (Bean) defined in XML Bean Configuration file but not instantiate the objects in source code directly?

Using this approach, you can de-couple dependencies 

> You mentioned about BeanFactory, but what is its relation with ClassPathXmlApplicationContext?

The ClassPathApplicationContext (another objects container) provides additional functionalities over the BeanFactory. For example, you can use getBean function just like with BeanFactory -

./src/bean-config.xml
``` xml
<?xml version="1.0" encoding="UTF-8"?>
 
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">
 
    <bean id="beanId" class="Object">
       <property name="message" value="Application Context Example"/>
   </bean> 
</beans> 
```
./src/test_application_context.java
``` java
ApplicationContext context = new ClassPathXmlApplicationContext("bean-config.xml");
Object obj = (Object) context.getBean("beanId");
obj.publicMethod();
```

> About advantages of ApplicationContext over the BeanFactory, beside the additional functionalities, any other bold differences?

BeanFactory is lazy loading, it only instantiate the object after calling getBean() method and call a method in the object.
ApplicationContext instantiate the object as soon as the ApplicationContext is created.

> About ApplicationContext, as my observation in your example, an ApplicationContext created by ClassPathXmlApplicationContext method. 
> Is there other methods to instantiate an ApplicationContext?

Yes, you are correct,  the most popular methods:

- *ClassPathXmlApplicationContext*: Load the Bean configuration xml file from class path (e.g. folder ./src).
- *FileSystemXmlApplicationContext*: Load from the system file (e.g. folder C:\beans.xml)
- *XmlWebApplicationContext*: Load over the internet.

> In my imagination, each Bean defined in the XML file has an ID. Is it Singleton Bean (Object)?

It is about scope of Beans. The Spring framework has predefined the following scopes:

 - singleton (default) (different for each ApplicationContext, i.e., different xml bean configuration file)
 - prototype (instantiate new object every time getBean method is called)
 - request (different for each request)
 - session (different for each session)
 - global_session (different for each session)
Example:
``` xml
<bean id="singletonBean" class="MyClass"/>
<bean id="singletonBean1" scope="singleton" class="MyClass"/>
<bean id="singletonBean2" singleton="true" class="MyClass"/>

<bean id="prototypeBean1" scope="prototype" class="MyClass"/>
<bean id="prototypeBean2" singleton="false" class="MyClass"/>
```

> Type of Beans is defined in "class" attribute, I guess that we have to cast the result to desired class when using getBean method (of ApplicationContext). 
>Is it correct?

Yes, you are correct, following is an example (notice the PrototypeBean casting):
```java
public class TestPrototypeBean {
      public static void main(String[] args) {
	      ApplicationContext context = new ClassPathXmlApplicationContext("beans.xml");
	      PrototypeBean prototypeBeanA = (PrototypeBean)context.getBean("prototypeBean");
	      System.out.println(prototypeBeanA); 
	      
	      PrototypeBean prototypeBeanB = (PrototypeBean)context.getBean("prototypeBean");
	      System.out.println(prototypeBeanB);
	         
	      System.out.println("Is Prototype Bean A and Prototype B are same ? " +  (prototypeBeanA==prototypeBeanB));
      }
}
```

> Is the Bean aware its container or current session?
> We might use such information, e.g, for logging.

Yes, there are over-writable  methods from the call to ready-to-use:
![From instantiation to ready to use](https://www.wideskills.com/sites/default/files/subjects/Spring%20Tutorial/Chapter%20-%2007/Image_1.png)

 Also before completely destroyed:
 
![a](https://www.wideskills.com/sites/default/files/subjects/Spring%20Tutorial/Chapter%20-%2007/Image_2.png)

All you have to do is to implement one or some of the following interfaces:

 - InitalizingBean, DisposableBean
 - ApplicationContextAware, BeanNameAware, BeanFactoryAware

> Can I set a custom hook method using .xml file?

Yes, you can change `init-method` and/or `destroy-method` attributes in the .xml file like this: 
``` xml
<bean id="beanID" init-method="myCustomInitMethod" destroy-method="myCustomDestroyMethod" class="MyClass" />
```

## # Spring Bean Configuration Inheritance

> Can we re-use some configuration in Bean configuration file?
> For an example, we have Students, Teachers, Professors. 
> They are all human so they all have name and date-of-birth. 
> Can we re-use it?

Yes, you can. Let take a look at following example:
``` xml
<bean id="humanBean" class="Human">
    <property name="name" value="TBD"/>
    <property name="date-of-birth" value="1900/01/01"/>
</bean>

<bean id="studentBean" parent="humanBean">
```

> Is there other kind of inheritance?

Yes, there is other kind of inheritances you can do a configuration parent Bean by your demand:

| class attr. | abstract attr. | Desc.  |
| ----------- | -------------- | ------------------- |
| yes        | no            | CAN initialize both parent and children, DON'T define "class" attribute in children Bean|
| yes        | yes           | CANNOT initialize parent, HAVE TO define "class" attribute in children Bean)               |
| no         | yes           | Not use (no application)|
| no         | no            | Not use (no application)|

## # Spring Dependency Injection

> As I look in the Bean configuration file, 

## # Common issues

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTkyODE1MjY1OCwtMTkyMTg2OTYxMiwxNT
QyNjUwMjE0LDMzMzE3MDU4MiwtMjk2MzczNDQyLC0xOTg2NTUx
MjcyLC0xNTYyMjcwNTg0LC0xMjg4NjI3ODY2LC0xODIxMDgwMD
I2LC0yODI3MzE5ODksLTEwNDMyNTEzMDUsLTIwOTMzOTE4Mjgs
NTg4MTQyMDk0LC0xMDA3NDM2Mzk1LC0xODY1MDMxNjQ0LC0xMT
k2NzE0NzM2LC04NjA1NzAwODcsMTQ2OTcyNzkwOF19
-->