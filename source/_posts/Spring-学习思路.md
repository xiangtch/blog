---
title: Spring 学习思路
date: 2019-11-26 10:44:17
categories: 
  - spring 源码分析
tags:
  - spring
  - framework
---

# Spring 学习思路

## Spring 项目模块

![springframework](https://raw.githubusercontent.com/xiangtch/blog/master/source/_posts/image/springframework.png)



- **spring-core:** Spring 项目的核心，包含有通用的工具类、公共的参数定义、JDK 动态代理和 cglib 的对接等。其他模块都会依赖这个模块
- **spring-beans:** Spring 的 Bean 模块，包含 Spring 的 Bean 工厂和 Bean 定义相关的类。
- **spring-expression:** Spring 的 EL 表达式模块
- **spring-aop:** Spring 的切面模块
- **spring-context:** Spring 的 IOC 容器模块
- **spring-tx:** Spring 的事务模块

## 学习 Spring 的 IOC 容器需要重点了解的接口

- **ApplicationContext:** IOC 容器的上下文
- **BeanFactory:** Bean 工厂接口，IOC 容器的 Bean 都是通过 Bean 工厂创建
- **BeanFactoryPostProcessor:** Bean 工厂后置处理器，一般用于 Bean 工厂创建 Bean 实例后，对 BeanFactory 实例的处理
- **BeanDefinition:** Spring 的 Bean 定义接口，Spring 中的 Bean 会带来一些方便 Spring 管理的属性
- **BeanDefinitionParser:** Bean 声明处理器，将 XML 配置转化为 BeanDefinition 并绑定到对应的上下文
- **BeanDefinitionRegistry:** 将 Bean 注册到 Spring 的 IOC 容器中
- **BeanPostProcessor:** Bean 后置处理器，一般与 BeanFactory 绑定，用于对 Bean 的加工
- **ResourceLoader:** 资源加载器
- **ApplicationEventPublisher:** Spring 的 IOC 容器是基于事件机制，这个是事件发布器接口