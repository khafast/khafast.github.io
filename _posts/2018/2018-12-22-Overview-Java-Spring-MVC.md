This is my notes about **Java Spring MVC**. 
Content is about 30 minutes read, its purpose is:
- To refresh your memory if you already worked on it. 
- Or if you are totally new, it will give you an overview, so you can kick start your first Java Spring MVC application.

## Installation
Windows:
 - [ ] JDK
 - [ ] Download Spring libraries (then add to build path)


## ClassPathXmlApplicationContext

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
- *FileSystemXmlApplicationContext*: Load the Bean configuration xml file from the system file (e.g. folder C:\beans.xml)
- *XmlWebApplicationContext*: Load the Bean configuration over the internet.

## Common issues

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMDc0MzYzOTUsLTE4NjUwMzE2NDQsLT
ExOTY3MTQ3MzYsLTg2MDU3MDA4NywxNDY5NzI3OTA4XX0=
-->