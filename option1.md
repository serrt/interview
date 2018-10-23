# 项目分享

[项目地址](https://github.com/serrt/admin-iframe.git)

## 环境要求

- php >= 7.1
- composer required
- laravel = 5.6
- mysql >= 5.6

## 分支

- master: 简单的 iframe 模板
- develop: 开发分支(暂不维护)
- permission: 完整的权限分支(主要维护的分支)
- wechat-info: 微信授权留资公用项目, 地址[http://wechat.peidikeji.cn/admin](http://wechat.peidikeji.cn/admin)

## Laravel

### 文档

- [原文]https://laravel.com/docs/5.6)
- [中文翻译](https://laravel-china.org/docs/laravel/5.6)
- [速查表](https://cs.laravel-china.org/)
- [API源码](https://laravel.com/api/5.6/)

### 路由

- `as`, `name` 路由命名
- `prefix` 路由前缀
- `namespace` 命名空间
- `middleware` 中间件
- `resource` 资源路由
    `Route::get('example', ['uses' => 'ExampleController@index'])`
    `Route::get('example/create', ['uses' => 'ExampleController@create'])`
    `Route::post('example', ['uses' => 'ExampleController@store'])`
    `Route::get('example/{example}', ['uses' => 'ExampleController@show'])`
    `Route::get('example/{example}/edit', ['uses' => 'ExampleController@edit'])`
    `Route::put('example/{example}', ['uses' => 'ExampleController@update'])`
    `Route::delete('example/{example}', ['uses' => 'ExampleController@destroy'])`
- `routes\admin.php` 路由文件
- `App\Providers\RouteServiceProvider` 路由服务

### 控制器

- `php artisab make:controller Admin\ExampleController -r` 创建控制器, `-r` 代表添加**资源路由**需要的方法 `index, create, store, show, edit, update, destroy`

### 表单验证

### 模型

### 数据迁移
