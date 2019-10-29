<!--
 * @Author: dannyding
 * @Date: 2019-08-27 16:12:56
 * @LastEditTime: 2019-08-27 16:12:56
 * @Description: 
 -->
---
layout: post
title: PHP 常用资源
category: 资源
tags: PHP
keywords: PHP
description: 
---

## 常用资源

### 常用扩展

1. [phpDocumentor](http://www.phpdoc.org)
2. [PHPUnit](https://phpunit.de)
3. [Guzzle](https://github.com/guzzle/guzzle)

### 好文
1. [PHP之道](http://wulijun.github.io/php-the-right-way/)
2. [Cookie/Session机制详解](http://blog.csdn.net/fangaoxin/article/details/6952954)

### 优秀的类库
1. [PHP中文分词: 自动打标签功能](http://jingwentian.com/t-145)

### 判断是否为空
```
+--------------+-----------+---------+-----------+---------+--------+
| 真值表        | gettype() | empty() | is_null() | isset() | (bool) |
+--------------+-----------+---------+-----------+---------+--------+
| $x = ""      | string    | true    | false     | true    | false  |
| $x=null      | NULL      | true    | true      | false   | false  |
| var $x       | NULL      | true    | true      | false   | false  |
| $x = array() | array     | true    | false     | true    | false  |
| $x = false   | boolean   | true    | false     | true    | false  |
| $x = 15      | integer   | false   | false     | true    | true   |
| $x = 1       | integer   | false   | false     | true    | true   |
| $x = 0       | integer   | true    | false     | true    | false  |
| $x = -1      | integer   | false   | false     | true    | true   |
| $x = '15'    | string    | false   | false     | true    | true   |
| $x = '1'     | string    | false   | false     | true    | true   |
| $x = '0'     | string    | true    | false     | true    | false  |
| $x = '-1'    | string    | false   | false     | true    | true   |
| $x = 'foo'   | string    | false   | false     | true    | true   |
| $x = 'true'  | string    | false   | false     | true    | true   |
| $x = 'false' | string    | false   | false     | true    | true   |
+--------------+-----------+---------+-----------+---------+--------+
```

## 常用命令
### Time
```
echo(strtotime("now")); //現在時間
echo(strtotime("3 October 2005")); //2015-10-03
echo(strtotime("+5 hours")); //現在時間+5小時
echo(strtotime("+1 week")); //現在時間+1星期
echo(strtotime("+1 week 3 days 7 hours 5 seconds")); //現在時間 +1星期3天7小時5秒
echo(strtotime("next Monday")); //下個星期的星期一
echo(strtotime("last Sunday")); //上個星期的星期天
```
```
echo $time1="2015-11-18 23:00:00";
echo $time2="2015-11-22 05:00:00";

echo (strtotime($time1) - strtotime($time2)); //計算相差之秒數
echo (strtotime($time1) - strtotime($time2))/ (60); //計算相差之分鐘數
echo (strtotime($time1) - strtotime($time2))/ (60*60); //計算相差之小時數
echo (strtotime($time1) - strtotime($time2))/ (60*60*24); //計算相差之天數

//目前時間 加 1小時
echo date('Y-m-d H:i:s', strtotime('+1 hours'));
```

### 修改phpunit内存限制    

    phpunit -d memory_limit=512M


## PHPStorm 常用快捷键

- Quick Command

    `Command + Shift + A`

- Quick File

    `Command + Shift + O`

- Quick Class

    `Command + O`

- Quick Symbol

    `Command + Option + O`