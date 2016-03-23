### 国际化

EAD 平台国际化即指多语言的支持。当前 EAD 引擎多语言支持是基于 ResourceBundleMessageSource 实现的，通过对不同应用语言的配置，动态获取内容。当前支持平台只支持中文和 English。

### I18N 配置

Spring 相关内容配置在 i18n.xml 文件中，内容如下：

```
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://www.springframework.org/schema/beans 
  http://www.springframework.org/schema/beans/spring-beans-4.0.xsd ">
  
  <bean id="messageSource"
    class="org.springframework.context.support.ResourceBundleMessageSource">
    <property name="basenames">
      <list>
        <value>i18n/message</value>
        <value>i18n/exceptions</value>
        <value>i18n/windows</value>
      </list>
    </property>
  </bean>
</beans>
```

语言包包括 message（消息提醒）、exceptions（异常）、windows（默认）。

如需扩展语言，只需要把相应的语言包放置到 i18n 文件夹下即可；