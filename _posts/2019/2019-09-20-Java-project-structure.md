
### security/src/main/resources/security-config.properties
```properties
keycloak.url=https://url.com
keycloak.group.interviewer.id=bbceeda4-8160-e5b8-8d08-3f96a818891f
keycloak.group.recruiter.id=b6c76ffa-4e55-4daa-a16b-4ac92e6ac7a6
```

### security/src/main/resources/META-INF/beans.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans 
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
	xmlns="http://xmlns.jcp.org/xml/ns/javaee" 
	xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/beans_1_1.xsd"
	bean-discovery-mode="all">  
</beans>
```

### security/pom.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<project
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd"
    xmlns="http://maven.apache.org/POM/4.0.0"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <modelVersion>4.0.0</modelVersion>
    <parent>
        <groupId>com.parent.groupid</groupId>
        <artifactId>my-project</artifactId>
        <version>1.0.0</version>
    </parent>
    <artifactId>my-project-security</artifactId>
    <packaging>ejb</packaging>
    <name>my-project-security</name>

    <properties>
        <resteasy.version>3.0.24.Final</resteasy.version>
    </properties>
    <dependencies>
        
        <dependency>
            <groupId>javax</groupId>
            <artifactId>javaee-api</artifactId>
            <scope>provided</scope>
        </dependency>

        <dependency>
            <groupId>org.keycloak</groupId>
            <artifactId>keycloak-core</artifactId>
        </dependency>

        <dependency>
            <groupId>org.keycloak</groupId>
            <artifactId>keycloak-adapter-core</artifactId>
        </dependency>

        <dependency>
            <groupId>org.keycloak</groupId>
            <artifactId>keycloak-admin-client</artifactId>
        </dependency>

        <dependency>
            <groupId>org.jasypt</groupId>
            <artifactId>jasypt</artifactId>
            <version>1.9.3</version>
        </dependency>
    </dependencies>
    <build>
        <finalName>my-project-security</finalName>
    </build>
</project>
```

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQxNTcxNTU5NV19
-->