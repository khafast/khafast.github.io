
### secur

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
eyJoaXN0b3J5IjpbMTM3MzE5NTc0OV19
-->