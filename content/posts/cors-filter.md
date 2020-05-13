---
title: "Cors Header Support using a filter"
date: 2020-05-13T13:44:46+03:00
draft: false
tags: ["cors", "filter"]
---

Add the following to your `web.xml` to enable CORS header support in an app:
<!--more-->

```
<filter>
    <filter-name>CorsFilter</filter-name>
    <filter-class>org.apache.catalina.filters.CorsFilter</filter-class>
    <init-param>
        <param-name>cors.allowed.origins</param-name>
        <param-value>*</param-value>
    </init-param>
    <init-param>
        <param-name>cors.allowed.methods</param-name>
        <param-value>DELETE,GET,HEAD,OPTIONS,PATCH,POST,PUT</param-value>
    </init-param>
    <init-param>
        <param-name>cors.allowed.headers</param-name>
        <param-value>Content-Type,X-Requested-With,accept,Origin,Access-Control-Request-Method,Access-Control-Request-Headers,X-Amz-Date,Authorization,X-Api-Key,X-Amz-Security-Token,x-ep-user-id,x-ep-user-roles,x-ep-user-scopes,x-ep-user-traits,x-forwarded-base</param-value>
    </init-param>
    <init-param>
        <param-name>cors.exposed.headers</param-name>
        <param-value>Access-Control-Allow-Origin,Access-Control-Allow-Credentials</param-value>
    </init-param>
</filter>

<filter-mapping>
    <filter-name>CorsFilter</filter-name>
    <url-pattern>/*</url-pattern>
</filter-mapping>
```