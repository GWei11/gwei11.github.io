---
title: maven使用手册
categories:
	- [tools, maven]
tags:
	- tools
	- maven
---

# `maven`配置默认的jdk版本

在`maven`的安装目录下修改`settings.xml`文件，修改内容如下：

```xml
<profile>    
    <id>jdk-1.8</id>    
    <activation>    
        <activeByDefault>true</activeByDefault>    
        <jdk>1.8</jdk>    
    </activation>    
    <properties>    
        <maven.compiler.source>1.8</maven.compiler.source>    
        <maven.compiler.target>1.8</maven.compiler.target>    
        <maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>    
    </properties>    
</profile>
```

这个节点需要加载在`profiles`节点下。

<!--more-->