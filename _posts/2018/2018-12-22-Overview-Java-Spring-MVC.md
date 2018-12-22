This is my notes about **Java Spring MVC**. 
Content is about 30 minutes read, its purpose is:
- To refresh your memory if you already worked on it. 
- Or if you are totally new, it will give you an overview, so you can kick start your first Java Spring MVC application.

## Installation
Windows:
 - [ ] JDK
 - [ ] Download Spring libraries (then add to build path)


## ClassPathXmlApplicationContext

At first, in Java Spring Core module, there is a  BeanFactory. You can imagine the Bean is like Object in OOP. BeanFactory allows you to access objects defined in Xml bean configuration file. 

> So why using object (Bean) defined in XML Bean Configuration file but not instantiate the objects in source code directly?

Using this approach, you can de-couple dependencies 

> You mentioned about BeanFactory, but what is its relation with ClassPathXmlApplicationContext?

The ClassPathApplicationContext provides additional functionalities over the BeanFactory. For example, you can use getBean function just like with BeanFactory -
``` java
ApplicationContext context = new ClassPathXmlApplicationContext('bean-config.xml');
Object obj = (Object) context.getBean('beanID');
```

## Common issues

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg2MDU3MDA4NywxNDY5NzI3OTA4XX0=
-->