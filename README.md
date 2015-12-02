Discourse Chinese Share
=======================

使用此插件请fork本项目。

A Easy plugin to add Chinese share buttons in [Discourse](https://github.com/discourse/discourse).

We can add share buttons like Weibo, Wechat, Renren.

## 在 Docker 镜像上的安装方法

修改你的 `/var/discourse/containers/app.yml` 文件. 默认的 `app.yml` 有一个 `hooks` 属性，如下:

```ruby
hooks:
  after_code:
    - exec:
        cd: $home/plugins
        cmd:
          - mkdir -p plugins
          - git clone https://github.com/discourse/docker_manager.git
```
在那后面添加一行，注意空格对齐。
```
- git clone https://github.com/GITHUB_USER/discourse-chinese-share.git
```
将上面的`GITHUB_USER`改成你的用户名，也就是说，此处添加的是你fork后的git地址。

重建 Discourse：`/var/discourse/launcher rebuild app`

进入管理员页面 -> 设置 -> 基本设置 -> 找到`share links`配置项，输入你想添加的分享按钮，如`weibo`,`wechat`,`renren`。

刷新页面，完成。

## Changelog

Current version: 0.1.1

0.1.1: 修复安装后无法看到分享按钮的问题


