# 通过Laravel-DM8为Laravel 提供 达梦数据库驱动程序包

**前置条件：**

> 请确保当前环境的PHP 已正确加载DM PHP 模块，即执行php -m 需要显示一下拓展已开启：
>
> ```shell
> PDO                                                                                                                     
> PDO_DM  
> ```
>
> 如果没有请先安装达梦php驱动和拓展。[安装文档](https://eco.dameng.com/document/dm/zh-cn/pm/php-rogramming-guide.html#6.2%20DM%20PHP%20%E6%A8%A1%E5%9D%97%E5%8A%A0%E8%BD%BD)

## 关于Laravel-DM8

Laravel-DM8 是 [Laravel](http://laravel.com/) 的达梦数据库驱动程序包。它是 
 [Illuminate/Database](https://github.com/illuminate/database) 的拓展，它使用 [DM8](https://eco.dameng.com/document/dm/zh-cn/pm/php-rogramming-guide.html#) 拓展与 达梦数据库通信. 基于[Laravel的Oracle的数据库驱动程序包](https://github.com/yajra/laravel-oci8)修改而来 ,感谢 [@yajra](https://github.com/yajra).

## 文档

- [DM8 程序员手册](https://eco.dameng.com/document/dm/zh-cn/pm/programmer-overview.html)

## Laravel 版本兼容性

 Laravel | Package 
:--------|:--------
 5.1.x   | 5.1.x   
 5.2.x   | 5.2.x   
 5.3.x   | 5.3.x   
 5.4.x   | 5.4.x   
 5.5.x   | 5.5.x   
 5.6.x   | 5.6.x   
 5.7.x   | 5.7.x   
 5.8.x   | 5.8.x   
 6.x.x   | 6.x.x   
 7.x.x   | 7.x.x   
 8.x.x   | 8.x.x   
 9.x.x   | 9.x.x   

## 快速安装

```bash
composer require dennyyang/laravel-dm8
```

## 服务提供商（Laravel 5.5+ 上可选）

通过 Composer 安装或更新了您的软件包，您就需要注册 Laravel-DM8。打开`config/app.php`并找到 providers 并添加：

```php
LaravelDm8\\Dm8\\Dm8ServiceProvider::class,
```

## 配置（可选）

您可以选择通过运行以下 Artisan 命令来发布配置文件。如果配置文件未发布，包将自动使用`.env`文件 数据库配置中声明的内容。

```bash
php artisan vendor:publish --tag=dm
```

这会将配置文件复制到`config/dm.php`。

> 然后，您可以在`.env`文件中设置连接数据：

```ini
DB_CONNECTION = dm
DB_HOST = dm.host
DB_PORT = 5236
DB_DATABASE = xe
DB_USERNAME = hr
DB_PASSWORD = hr
DB_CHARSET = UTF8
```

之后可以运行你的Laravel 程序了。

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
