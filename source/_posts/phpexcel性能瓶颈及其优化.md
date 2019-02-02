---
title: phpexcel性能瓶颈及其优化
date: 2019-02-02 10:25:32
tags: phpexcel,500,502
---
## PHP导出excel常见报错
### 导出报错 Fatal error: Out of memory
Fatal error: Out of memory (allocated 1048576) (tried to allocate 393216 bytes)
在程序中添加 ini_set("memory_limit","2080M");
或者直接修改php.ini中的memory_limit
memory_limit参数PHP可以占用的内存数，注意不要超过机器的实际内存。
### 导出报错 502bad gateway
502是程序运行超时是nginx和php-fpm配置的问题。
一般我们设置一下php-fpm.conf中的request_terminate_timeout之后重启PHP-FPM和nginx服务就可以了。
### 导出报错 该网页无法正常运作 目前无法处理此请求。HTTP ERROR 500
在测试环境下修改php.ini开启
display_errors = On
display_startup_errors = On
并重启服务，然后根据报错相应处理

## 由以上报错我们可以得出 php的性能瓶颈在于服务器性能，当导出数量大于1W条的时候，随着PHP使用服务器内存的增加，导出速度在相应的下降。
## PHP导出EXCEL的优化
### 不要在写入EXCEL的时候进行计算
### 不要再大数据的时候设置单元格样式
### 分批次写入
### 使用PHPExcel_Settings::setCacheStorageMethod() 降低程序对内存的消耗


