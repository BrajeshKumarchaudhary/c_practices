# SpringMvC_Minimal_setup
# This is Basic SetUp for Spring Mvc Project in Spring Tool Suite.Please Follow these Step To set up Project in your system.
#step1:goto file->new
#step2:select Maven Categeory project 
#step3:add following dependency:SpringMvc,Spring-beans,Spring-core,servlet-api,jsp api,jstl,Spring-context in pom.xml
#create web.xml in  /WebContent/WEB-INF/web.xml. and add the following code 

<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://java.sun.com/xml/ns/j2ee" xmlns:web="http://xmlns.jcp.org/xml/ns/javaee" xsi:schemaLocation="http://java.sun.com/xml/ns/j2ee http://java.sun.com/xml/ns/j2ee/web-app_2_4.xsd" id="WebApp_ID" version="2.4">
  <servlet>
    <servlet-name>SpringSample</servlet-name>
    <servlet-class>
         org.springframework.web.servlet.DispatcherServlet
      </servlet-class>
    <init-param>
      <param-name>contextConfigLocation</param-name>
      <param-value>/WEB-INF/SpringSample-servlet.xml</param-value>
    </init-param>
    <load-on-startup>1</load-on-startup>
  </servlet>
  
  <servlet-mapping>
    <servlet-name>SpringSample</servlet-name>
    <url-pattern>/</url-pattern>
  </servlet-mapping>
</web-app>
#step4:create /WEB-INF/SpringSample-servlet.xml and add following code

<beans xmlns="http://www.springframework.org/schema/beans"
   xmlns:context="http://www.springframework.org/schema/context"
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
   xsi:schemaLocation="
   http://www.springframework.org/schema/beans     
   http://www.springframework.org/schema/beans/spring-beans.xsd
   http://www.springframework.org/schema/context 
   http://www.springframework.org/schema/context/spring-context.xsd">
   
   <!-- Adding Support for Component Scan -->
   <context:component-scan base-package="org.study" />
   
   <!-- Configure View Resolver -->
   <bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
      <property name="prefix" value="/WEB-INF/" />
      <property name="suffix" value=".jsp" />
   </bean>
 
   </beans>
   #step5:create a package org.study under this package create a Controller class which return hello.jsp
   #create hello.jsp
