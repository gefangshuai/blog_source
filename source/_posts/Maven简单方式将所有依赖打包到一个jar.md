---
title: Maven简单方式将所有依赖打包到一个jar
date: 2016-10-25 19:45:36
tags: [java, maven]
---

用如下插件
```xml
<plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-assembly-plugin</artifactId>
	<version>2.6</version>
	<configuration>
		<descriptorRefs>
			<descriptorRef>jar-with-dependencies</descriptorRef>
		</descriptorRefs>
		<archive>
			<manifest>
				<addClasspath>true</addClasspath>
				<mainClass>com.ch.Main</mainClass>
			</manifest>
		</archive>
	</configuration>
</plugin>
```
<!-- more -->
运行命令
```bash
clean compile assembly:assembly
```

**搞定！**