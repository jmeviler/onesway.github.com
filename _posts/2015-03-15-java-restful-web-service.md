---
layout: post
title: Java Jersey使用
categories: [Jersey]
tags: [Jersey]
description: Java Jersey's use.
---

**简介**
    Jersey是JAX-RS标准的参考实现，是Java领域中开发REST式的Web服务的“正统”工具。<a href="https://jersey.java.net" target="_blank">传送门</a>

-----
**配置**

单纯的Jersey使用，需要导入的以下的包（版本根据自己实际项目定）
<img src="/img/jersey.png" width="306" height="180">   
1)写一个资源测试类类（在JAVA Restful中称为资源）

    @Path("/test")
        public class HelloResource {
        @GET
        @Produces(MediaType.TEXT_PLAIN)
        public String sayHello() {
            return "Hello World ! This is a test by Ben Li.";
        }
    }

2)编写JAX-RS application（此处有两种方式）
1.不许要配置web.xml的方式：

    @ApplicationPath("/services/*")
        public class AirResourceConfig extends ResourceConfig {
            public AirResourceConfig() {
            packages("xyz.onesway.resource");//此处是资源文件的包路径
        }
    }

2.需要配置web.xml的方式：

    public class APIApplication extends ResourceConfig{
        public APIApplication() {
            //加载Resource资源类
            register(HelloResource.class);
            //注册数据转换器
            register(JacksonJsonProvider.class);
        }
    }

需要在web.xml的配置有：

    <servlet>
    <servlet-name>JerseyServlet</servlet-name>
    <servlet-class>org.glassfish.jersey.servlet.ServletContainer</servlet-class>
    <init-param>
    <param-name>javax.ws.rs.Application</param-name>
    <!--APIApplication位置-->
    <param-value>xyz.onesway.resource.APIApplication</param-value>
    </init-param>

    <load-on-startup>1</load-on-startup>
    </servlet>
    <servlet-mapping>
    <servlet-name>JerseyServlet</servlet-name>
    <!--统一入口-->
    <url-pattern>/services/*</url-pattern>
    </servlet-mapping>

测试（此处使用Postman工具,关于Postman使用请参考<a href="http://blog.onesway.xyz/tools/2015/03/10/postman-api-tool.html">《Postman--API测试工具》</a>）   
<img src="/img/test-result.png" width="719" height="238">   


此处仅介绍其基本使用和配置。


