---
title: PHP
abbrlink: 11574
date: 2021-04-19 10:56:47
tags:
  - 复习
categories: PHP
hide: true
---

不会，看菜鸟教程吧

<a href="https://www.runoob.com/php/php-tutorial.html">PHP教程</a>

<!-- more -->

考试（选择10 * 3 判断10 * 2 简答3 * 10 编程 20）

大题重点：数据库（mysql或者PDO）与session

# 基础

### web工作原理

通过网络运行

服务器，客户端模型B/S

URL如何对应服务器文件

PHP在哪里运行，结果是什么

HTML,JS,CSS前端技术

URL包含哪些部分远程调用，参数

HTTP协议

### 静态与动态页面

get post方法

服务器端的区别

### PHP服务器

LAMP

运行平台

如何安装与配置

phpinfo函数

# 语言基础

### html与php混合编程

如何解析

分段

一段不完整语法（循环/判断）

include和include_once

### 数据类型

#### 基本类型

boolean

integer

float

字符串：

单引号双引号区别

字符串连接

字符串操作

object

array

特殊类型

resource

null

#### 类型转换

强制转换

隐含

字符串与数字类型

检测数据类型（39页）

### 常量（40）

声明

使用

检测

预定义常量（41）

### 变量

#### 如何声明变量

变量声明无类型

测试未声明的变量

引用变量

#### 变量作用域（44）

全局

静态

#### 可变变量（46）

#### 预定义变量

$_POST

$_GET

$_REQUEST

$_SESSION

$_COOKIE

$_FILE

### 运算

大多与C差不多

字符串

逻辑===

== 与 ===的区别

！ ==

所有类型的变量都可以参与逻辑运算

### 函数定义与调用

默认参数

传值/引用

变量函数（58）

### 流程控制

注意forreach语法

注意rand函数（66）

### 字符串操作

trim/ltrim/rtrim

转义还原函数（85）

长度

截取

查找

替换

分割/合成（98）

### 数组

数组类型可以任意

数组基本操作

长度

foreache

把数组当堆栈

删除重复等操作

下表和键值的区别，下标可以不连续

# 与WEB交互

### 表单的使用

from基本参数

基本表单元素

表单中使用数组/多选

### POST和GET

### 如何在服务器得到WEB传递的参数

### URL传递参数与POST的区别

### 文件上传

### URL编码/解码

# 与JS集成

### 哪里运行

### 什么作用

### 嵌入与外部引用

# 日期和时间

### 时区设置

### timepestamp

### 时间类型与时间函数

time函数

date函数

# cookie与session

### cookie原理

### session是什么

### 如何操作session

# 文件和目录

### 打开关闭文件

### 读文件

redfile

file

file_get_contents

### 写文件fwrite

### 文件和目录

scandir

is_dir

### 如何上传文件

# 面向对象

大多与JAVA一样

### 定义类需要在一个PHP区块中

### 析构函数的特殊性

### 常量

### 静态方法

### 静态函数

### $this和 ： :

### parent/self/类名

### 对象成员访问符号

### 魔术方法

_get/ _set

_call



# PHP加密

crypt

md5

sha1

# PHP操作数据库

### mysql基础

安装

访问

WEB客户端

## 传统方式操作数据库

连接

执行SQL

结果集操作

### PDO方式操作数据库

PDO连接数据库以及DSN

执行SQL->参数绑定

结果集操作

错误处理

事务处理



