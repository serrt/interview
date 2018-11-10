# Coder
记录一下自己平时总结的笔记

## [Git](#git)
## [资源](#resource)
## [PHP](#php)
## [Linux](#linux)
## [Laravel](#laravel)

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

- 一次性定时计划任务的**at**
- 查看目录大小 `du -h --max-depth=1 /www/wwwroot/`

<a name="laravel"></a>
## Laravel

- `nohup php artisan queue:listen &`
- 生成测试中文数据 `config/app.php` 加入 `faker_locale => 'zh_CN'`, 并不完整
