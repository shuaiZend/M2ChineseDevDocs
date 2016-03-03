---
layout: default
group: install_pre
subgroup: Getting Started
title: 安装快速参考 (教程)
menu_title: 安装快速参考 (教程)
menu_node: parent
menu_order: 1
github_link: install-gde/install-quick-ref.md
---

Magento的安装是比较具有挑战性的，我们想通过简化过程尽可能的多帮助你。

本主题假定:

*	你拥有自己的服务器 (没有使用共享空间).
*	你开始安装使用 `composer create-project`,获取到最新的Magento，如果需要，可以添加您的自定义配置。
*	服务器环境已经搭建好(数据库, web服务器和其他必要的环境).
*	服务器系统是Ubuntu或者CentOS. 

	(您可以使用相同的指令在红帽企业 Linux (RHEL) 或 Debian，像其他 UNIX 发行版上安装，但这些指令不是给 Mac 或 Windows。)
*	服务器的IP地址是 192.0.2.5
*	您安装Magento于 `magento2`子目录，并不是你服务器的docroot根目录.(完整路径为 `/var/www/html/magento2`)

	您可以选择设置了静态路由或虚拟主机，安装到主机名称而不是 IP，如果是就已超出了本主题的范围。

我们已经安装过程分为三个主要部分: 开始, 安装, 和安装以后. 我们希望，接下来可以帮助你; 如果你想要提出改进的建议, 点击页面顶部的 **Edit this page on GitHub**可以修改本页面，并且让我们知道.

## 前提: 您有多高级?
你知道什么是一个"终端"的应用程序?你知道什么您的服务器运行的操作系统吗?Apache 是什么，你知道吗?

如果不知道, 请看 <a href="{{ site.gdeurl }}install-gde/bk-install-guide.html">安装概述</a>.

## 安装第一部分: 开始
1.	请先查看<a href="{{ site.gdeurl }}install-gde/system-requirements.html">系统要求</a>.
2.	如果达不到Magento的系统要求, 请参阅系统必备组件文档:

	*	<a href="{{ site.gdeurl }}install-gde/prereq/apache.html">Apache</a>
	*	<a href="{{ site.gdeurl }}install-gde/prereq/php-ubuntu.html">PHP (Ubuntu)</a>
	*	<a href="{{ site.gdeurl }}install-gde/prereq/php-centos.html">PHP (CentOS)</a>
	*	<a href="{{ site.gdeurl }}install-gde/prereq/mysql.html">MySQL</a>
3.	同样重要的是, 请设置 <a href="{{ site.gdeurl }}install-gde/prereq/apache-user.html">Magento 文件系统所有者</a>在服务器上.
4.	切换到 Magento 文件系统所有者.

### 获取Magento
当已满足所有先决条件时，我们使用Composer获取Magento2 :

	cd <web server docroot directory>
	composer create-project --repository-url=https://repo.magento.com/ magento/project-community-edition

你需要进行身份验证; 查阅；<a href="{{ site.gdeurl }}install-gde/prereq/connect-auth.html">获取您的验证秘钥</a>详情. 只作为下载Magento使用; 它不会安装到Magento上.

<div class="bs-callout bs-callout-tip">
	<p>或者,你可以下载一个<a href="{{ site.gdeurl }}install-gde/install/get-software.html">Magento压缩安装包</a>.</p>
</div>

### 设置文件系统所有权和权限

{% include install/file-system-perms2-how.md %}

## 安装第二部分: 安装Magento
您可以选择<a href="{{ site.gdeurl }}install-gde/install/web/install-web.html">基于WEB的安装向导</a>或者使用<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli.html">命令行</a>进行安装.

下面的示例,演示如何使用带有下列选项的命令行安装:

*	Magento安装于`/var/www/html/magento2` 目录， 且Magento的后台是 `admin`; 因此:

	您的前台地址是 `http://192.0.2.5`

*	数据库和WEB服务器在同一台服务器上

	数据库库名为 `magento`, 用户和密码都是`magento`

*	使用服务器URL重写(rewrites)

*	Magento 管理员具有以下属性:

	*	管理员姓名为 `Magento User`
	*	用户名为`admin`  密码是 `admin123`
	*	E-mail地址是 `user@example.com`

*	默认语言为 `en_US` (U.S. 英语)
*	默认货币为  U.S. dollars (美刀)
*	默认时区为美国中部 (America/Chicago)

		php /var/www/html/magento2/bin/magento setup:install --base-url=http://192.0.2.5/magento2/ \
		--db-host=localhost --db-name=magento --db-user=magento --db-password=magento \
		--admin-firstname=Magento --admin-lastname=User --admin-email=user@example.com \
		--admin-user=admin --admin-password=admin123 --language=en_US \
		--currency=USD --timezone=America/Chicago --use-rewrites=1

选择切换到 <a href="{{ site.gdeurl }}config-guide/cli/config-cli-subcommands-mode.html">开发模式</a>.

	cd <your Magento install dir>/bin
	php magento deploy:mode:set developer

## 安装第三部分: 安装之后
*	<a href="{{ site.gdeurl }}install-gde/install/verify.html">验证安装成功</a>.
*	<a href="{{ site.gdeurl }}install-gde/trouble/tshoot.html">疑难解答问题</a> 如果需要.
*	学习关于<a href="{{ site.gdeurl }}comp-mgr/bk-compman-upgrade-guide.html">组件管理器和系统升级</a>为将来的更新做准备.
