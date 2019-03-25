# Coder
记录一下自己平时总结的笔记, d5f4cf3ed11359f849d7b5f9d61e9fc60e5ce994

## [Git](#git)
## [资源](#resource)
## [PHP](#php)
## [Linux](#linux)
## [Laravel](#laravel)
## [Mac](#mac)

<a name="git"></a>
## Git

- 保存用户名和密码

```
[credential]
     helper = store
```

- windows的下**用户文件**, 一般是 `C:/Users/用户名` ，添加 `_netrc` 文件

```
machine git服务器, 如: gitee.com, github.com
login 用户名, 如: serrt
password 密码, 如: password
```

- 保持ssh长时间的活性: `git安装目录/etc/ssh/ssh_config`, 添加

```
ServerAliveInterval 60
```

- `clone` 项目时, 项目地址加上自己的登录名和密码, 例如 `https://username:password@github.com/serrt/admin-iframe.git`

<a name="resource"></a>
## 图片资源

- [https://colorhub.me](https://colorhub.me)
- [https://www.pexels.com](https://www.pexels.com)
- [https://www.lifeofpix.com](https://www.lifeofpix.com)
- [https://foter.com](https://foter.com)
- [https://picjumbo.com](https://picjumbo.com)
- [https://unsplash.com](https://unsplash.com)

<a name="php"></a>
## PHP

- json不转义汉字: `json_encode($array, JSON_UNESCAPED_UNICODE)`
- emoji表情支持, mysql数据库用 **utf8mb4**, 数据库链接用 **utf8mb4**
- 根据数组的键名导出变量: `extract(['a' => 'b', 'c' => ['d', 'e', 'f']]);`

<a name="linux"></a>
## Linux

- 一次性定时计划任务的 `at`
- 查看目录大小 `du -h --max-depth=1 /www/wwwroot/`

<a name="laravel"></a>
## Laravel

- `nohup php artisan queue:listen &`
- 生成测试中文数据 `config/app.php` 加入 `faker_locale => 'zh_CN'`, 并不完整
- 模型添加的默认值, 仅限 `ExampleModel::create()`, `ExampleModel->save()` 有效
- 配置网站的 **https**: 文件 `app/Providers/AppServiceProvider` 的 `boot` 方法中添加 `$this->app['request']->server->set('HTTPS', str_contains(config('app.url'), 'https://'));`

```php
class ExampleModel extends Model
{
    protected static function boot()
    {
        parent::boot();
        // 监听模型创建事件，在写入数据库之前触发
        static::creating(function ($model) {
        });
    }
}
```

### Auth

```php
Auth::guard('admin') //指定看守 返回Auth对象
Auth::user(); //获取通过验证的用户 Auth::user()->name
Auth::check(); //检查是否验证
Auth::viaRemember(); //判断用户是否使用“记住我”cookie进行认证
Auth::login($user); //将一个已存在的用户实例登录到应用中,传入实例必须是Illuminate\Contracts\Auth\Authenticatable 契约的实现
Auth::loginUsingId($userid);//通过用户ID登录到应用
Auth::once($credentials);//只在单个请求中将用户登录到应用，而不存储任何 Session 和 Cookie
Auth::attempt($credentials);//登录用户 ，$credentials是['email' => $email, 'password' => $password],这个方法会和数据库对比
Auth::logout(); //注销验证用户
Auth::extend(); //自定义看守
Auth::provider(); //自定义用户提供者
```

### Laravel-excel

Excel扩展, 文档地址[https://laravel-excel.maatwebsite.nl](https://laravel-excel.maatwebsite.nl)

- 读取Excel时, 注意Excel文件有多个 **Sheet** 的问题

```php
\Maatwebsite\Excel\Facades\Excel::load($file, function($reader) {
    $data = $reader->get()->first();
});
```

<a name="mac"></a>
## Mac

### 解决homebrew安装时的权限问题

```
sudo chgrp -R admin /usr/local 
sudo chmod -R g+w /usr/local
```

其中 **admin** 代表当前用户所属的用户组, 可以通过 `groups` 命令查看
