# introduction

logback log4j

logback-core logback-classic logback-access

----------

# 1

StatusManager 内部状态信息

----------

# 2

Logger Appender Layouts

LoggerContext 树状层级结构

LoggerFactory.getLogger(logger的名字) 静态方法获取logger 名字相同实例相同

trace debug info warn error logger.setLevel()

一条日志的打印级别大于logger的有效级别，打印

全限定名命名

additivity=false 父级的日志不会在子级appender中输出

```
"%-4relative [%thread] %-5level %logger{32} - %msg%n"
```

```
logger.debug("The new entry is {}", entry);
```

```
Object[] paramArray = {newVal, below, above};
logger.debug("Value {} was inserted between {} and {}.", paramArray);
```

----------

# 3

logback-test.xml
logback.groovy 
logback.xml
META_INFO/services/ch/qos.logback.classic.spi.Configurator
BasicConfigurator

```
public static final Logger LOGGER = LoggerFactory.getLogger(MyApp1.class);
```

STDOUT: standard out

如果在解析配置文件的过程当中发生了错误，logback 会在控制台打印出它的内部状态数据。

```<configuration debug="true">```

```<statusListener class="ch.qos.logback.core.status.OnConsoleStatusListener" />```

```java -Dlogback.configurationFile=/path/to/config.xml chapters.configuration.MyApp1```
```
static {
        System.setProperty(ContextInitializer.CONFIG_FILE_PROPERTY, "configurationFile.xml");
    }
```
logger实例前设置

```<configuration scan="true" scanPeriod="30 seconds">```

```<configuration packagingData="true">```

Joran
直接调用 JoranConfigurator 的方式来重写 logback 的默认配置机制

查看内部状态信息:StatusManager; Web配置。
监听状态信息:xml; -Dlogback.statusListenerClass






