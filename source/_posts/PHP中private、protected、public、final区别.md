---
title: PHP中private、protected、public、final区别
date: 2018-11-08 13:16:58
tags: PHP-Interview-Best-Practices-in-China
date: 2014-03-03 19:07:43
comments: true
categories: Blog
tags: [Hexo]
keywords: PHP,private,protected,public,final
description: 生命在于折腾，又把博客折腾到Hexo了。给Hexo点赞。
---

## 变量与方法的关键字public,private,protected

 public的权限最大，既可以让子类使用，也可以支持实例化之后的调用，
 protected表示的是受保护的，访问的权限是只有在子类和本类中才可以被访问到
 private 表示的是私有，只能够是在当前的类中可以被访问到

## 类与方法的关键字 final

 PHP 5 新增了一个 final 关键字。如果父类中的方法被声明为 final，则子类无法覆盖该方法。
 如果一个类被声明为 final，则不能被继承。
