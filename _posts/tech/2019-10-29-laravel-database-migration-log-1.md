---
layout: post
title: laravel 数据库迁移记录
category: 技术
tags: PHP
keywords: laravel migration
description: laravel 数据库迁移记录
---

增加一个新字段

例如，我要给 articles 表增加一个 images 字段。
后期若想修改完善之前的数据表 不能再操作之前的文件，修改或删除字段需要一个新的迁移文件 
```log
php artisan make:migration add_要添加的字段名_to_要添加字段的表名_table --table=要添加字段的表名
```

修改原有字段属性  
```log
php artisan make:migration change_要修改的字段名_on_要修改字段的表名_table --table=要添加字段的表名
```

(ps: migrate的文件名称 上面那样写只是为了尽量规范而已重要的是迁移文件里面的内容)

首先需要生成 migration 文件，执行命令
```bash
php artisan make:migration add_images_to_articles_table --table=articles
```

输出结果为
```log
Created Migration: 2018_03_21_225819_add_images_to_articles_table
```

对应的 database/migrations/ 目录下会自动生成一个文件
```log
database/migrations/2018_03_21_225819_add_images_to_articles_table.php
```

新增字段
```php
public function up()
{
    Schema::table('articles', function (Blueprint $table) {
        $table->string('description')->nullable()->after('title');
    });
}

public function down()
{
    Schema::table('articles', function (Blueprint $table) {
        $table->dropColumn('description');
    });
}
```

修改字段
```php
public function up()
{
    Schema::table('articles', function (Blueprint $table) {
        $table->string('description', 200)->change();
    });
}

public function down()
{
    Schema::table('articles', function (Blueprint $table) {
        //
    });
}
```

最后执行
```bash
php artisan migrate
```