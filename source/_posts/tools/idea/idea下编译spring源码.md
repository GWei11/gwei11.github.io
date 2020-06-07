---
title: idea下编译spring源码
category:
  - - tools
    - idea
tags:
  - tools
  - idea
date: 2019-06-05
abbrlink: b202e3b0
---

步骤

1. 下载`spring`源码
2. 切换阿里云的源

```groovy
buildscript {
	repositories {
		maven { url 'https://maven.aliyun.com/nexus/content/groups/public/' }
		maven{ url 'https://maven.aliyun.com/nexus/content/repositories/jcenter'}
	}
}
```

