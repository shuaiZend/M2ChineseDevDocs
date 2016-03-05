---
layout: default
group: install_pre
subgroup: T_Developer
title: 更新安装依赖
menu_title: 更新安装依赖
menu_node:
menu_order: 10
github_link: install-gde/install/prepare-install.md
redirect_from: /guides/v1.0/install-gde/install/prepare-install.html
---

#### 内容索引

*	<a href="#install-update-depend">Magento 安装依赖简介</a>
*	<a href="#install-composer-install">运行`composer install`更新安装依赖</a>
*	<a href="#instgde-prereq-compose-access">设置文件系统所有权和权限</a>

  
<h2 id="install-update-depend">Magento 安装依赖简介</h2>
我们现在使用<a href="http://getcomposer.org">Composer</a>解决Magento和其扩展安装之前的依赖关系。

Composer是一个单独的应用程序，管理 PHP 的依赖关系. 你安装 Magento 软件之前，您必须按显示的顺序执行以下任务:

1.	<a href="{{ site.gdeurl }}install-gde/prereq/dev_install.html">安装Composer</a>.
2.	<a href="{{ site.gdeurl }}install-gde/prereq/apache-user.html">创建Magento文件权限拥有者</a> 让Composer有正确的权限可以写入Magento的安装目录.
2.	在Magento的根目录,运行<a href="#install-composer-install"><code>composer install</code> 命令</a> (演示: `/var/www/magento2/`).

	Magento安装于docroot的子目录.需要定位docroot? 点击 <a href="{{ site.gdeurl }}install-gde/basics/basics_docroot.html">这里</a>.

	<div class="bs-callout bs-callout-info" id="info">
  		<p>如果显示以下的错误, 请看 <a href="{{ site.gdeurl }}install-gde/trouble/tshoot_composer-fail.html">疑难解答</a>:</p>
  		<pre>file_get_contents(app/etc/NonComposerComponentRegistration.php): failed to open stream: No such file or directory</pre>
	</div>

为了Magento能正常运行，请确保web服务器有权限可以写入Magento的文件目录. 这个方法可以作为测试 <a href="{{ site.gdeurl }}install-gde/prereq/apache-user.html#install-update-depend-user-switch">切换到Magento文件拥有者用户</a>.

<h2 id="install-composer-install">运行 <code>composer install</code>更新依赖包</h2>
更新安装依赖包,请跟着下面操作:

1.	登录到您的Magento文件系统拥有者或者<a href="{{ site.gdeurl }}install-gde/prereq/apache-user.html">切换到这个用户</a>.
2.	切换到Magento根目录之后运行 `composer install`. 演示:

	CentOS:

		cd /var/www/html/magento2 && composer install

	Ubuntu:

		cd /var/www/magento2 && composer install

	此命令更新包的依赖包，并且可能需要几分钟才能完成.

	如果显示以下错误:

		[Composer\Downloader\TransportException]
			The "https://repo.magento.com/archives/magento/composer/magento-composer-1.0.2.0.zip" file could not be downloaded (HTTP/1.1 404 Not Found)

	如果是这样，请创建 <a href="{{ site.gdeurl }}install-gde/prereq/dev_install.html#instgde-prereq-compose-clone-auth">`auth.json`</a>文件在你的Magento文件系统拥有者的用户目录下 `<home>/.composer` 之后再次运行 `composer install`.

<h2 id="instgde-prereq-compose-access">设置文件系统所有权和权限</h2>
以下各节讨论如何设置文件系统所有权和权限:

*	<a href="#install-perms-import">为什么我们建议您设置文件系统权限</a>
*	<a href="#install-perms-set">文件系统权限和所有权</a>

<h3 id="install-perms-import">为什么我们建议您设置文件系统权限</h3>
{% include install/file-system-perms1-why.html %}

<h3 id="install-perms-set">文件系统权限和所有权</h3>
{% include install/file-system-perms2-how.md %}

#### 下一步
安装Magento软件:

*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli.html">命令行</a>
*	<a href="{{ site.gdeurl }}install-gde/install/web/install-web.html">安装向导</a>
