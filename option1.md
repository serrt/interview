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

- [原文](https://laravel.com/docs/5.6)
- [中文翻译](https://laravel-china.org/docs/laravel/5.6)
- [速查表](https://cs.laravel-china.org/)
- [API源码](https://laravel.com/api/5.6/)

### 路由

- `as`, `name` 路由命名
- `prefix` 路由前缀
- `namespace` 命名空间
- `middleware` 中间件
- `resource` 资源路由
    1. `Route::get('example', ['uses' => 'ExampleController@index'])`
    2. `Route::get('example/create', ['uses' => 'ExampleController@create'])`
    3. `Route::post('example', ['uses' => 'ExampleController@store'])`
    4. `Route::get('example/{example}', ['uses' => 'ExampleController@show'])`
    5. `Route::get('example/{example}/edit', ['uses' => 'ExampleController@edit'])`
    6. `Route::put('example/{example}', ['uses' => 'ExampleController@update'])`
    7. `Route::delete('example/{example}', ['uses' => 'ExampleController@destroy'])`
- `routes\admin.php` 路由文件
- `App\Providers\RouteServiceProvider` 路由服务
- `php artisan route:list` 查看当前网站的所有路由

### 控制器

- `php artisab make:controller Admin\ExampleController -r` 创建控制器, `-r` 代表添加**资源路由**需要的方法 `index, create, store, show, edit, update, destroy`

### 表单验证

在控制器里面添加表单验证

- `php artisan make:request ExampleRequest` 为单个请求生成独立的验证文件

### 模型

- `php artisan make:model Models\ExampleModel -m` 创建模型文件, `-m` 代表同时创建模型的**迁移文件**, `Models` 是指模型文件所在的目录
- `protected $table = 'example_am'` 模型所指向的数据表名, 默认是**模型名小写的复数**形式
- `protected $fillable = ['id', 'name']` 填写模型的需要批量添加的字段, `php artisan model:fillable 数据表名` 可以自动生成(项目自己写的命令)

### 数据迁移

用代码创建数据表

- `php artisan make:migration create_users_table` 创建数据表的迁移文件
- `php artisan migrate:generate 表名` 逆向生成迁移文件(来源扩展[xethron/migrations-generator](https://github.com/xethron/migrations-generator))

### 数据填充

- 添加默认的数据
- 添加随机数据

### 扩展

项目中用到的一些扩展

#### [arcanedev/log-viewer](https://github.com/ARCANEDEV/LogViewer)

日志扩展, 可以简单方便的管理日志

#### [maatwebsite/excel](https://laravel-excel.maatwebsite.nl/)

Excel 支持

- 2.1: 支持Excel导入导出
- 3.0: 不支持Excel的导入
- 3.1(最新): 支持Excel导入导出

#### [tucker-eric/eloquentfilter](https://github.com/tucker-eric/eloquentfilter)

封装Eloquent模型查询

#### [barryvdh/laravel-debugbar](https://github.com/barryvdh/laravel-debugbar)

debug 调试工具, 可以看到页面执行的sql

#### [barryvdh/laravel-ide-helper](https://github.com/barryvdh/laravel-ide-helper)

Laravel 代码提示, 推荐在PhpStorm中使用

#### [xethron/migrations-generator](https://github.com/xethron/migrations-generator)

可以将我们的数据库里表结构, 生成 migration 文件

- 全部数据表 `php artisan migrate:generate`
- 单张数据表 `php artisan migrate:generate table1`
- 多张数据表 `php artisan migrate:generate table1,table2`
- 忽略某张数据表 `php artisan migrate:generate --ignore=table1,table2`

### 前端插件

项目中用到的前端插件

#### [file-input](http://plugins.krajee.com/file-input)

文件预览, 文件上传

#### 日期选择器

- [date-picker](https://github.com/uxsolutions/bootstrap-datepicker)
- [datetime-picker](https://www.malot.fr/bootstrap-datetimepicker/)

#### 编辑器

[Froala Editor](https://github.com/froala/wysiwyg-editor)

- 引用
    ```
    <!-- 引入编辑器 style: 样式文件, script: 脚本文件, element: 元素选择器 -->
    @component('component.editor', ['style' => true, 'script' => true, 'element' => '#inputContent'])
    @endcomponent
    ```

- 内容预览
    ```
    <!-- 引入编辑器样式文件 -->
    @component('component.editor', ['style' => true])
    @endcomponent

    <!-- class:fr-view 必须 -->
    <div class="fr-view">编辑器内容</div>
   ```

#### [jquery表单验证](http://www.runoob.com/jquery/jquery-plugin-validate.html)

- remote:url 异步验证
- decimal:2 保留2位小数

#### [select2](https://select2.org/)

下拉框的扩展
