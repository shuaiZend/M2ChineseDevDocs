---
layout: default
group: install2
subgroup: Getting Started
title: 安装概述
menu_title: 安装概述
menu_node: 
menu_order: 1
github_link: install-gde/bk-install-guide.md
redirect_from: /guides/v1.0/install-gde/bk-install-guide.html
---

<h2>Magento软件安装</h2>
你好,欢迎你选择全球240000家商家共同的使用和信任的Magento.我们收集了一些信息，帮助您入门 Magento 与 Magento 安装。

我们这里有一些资源以帮助您开始使用未来的电子商务平台&mdash;Magento 2.

It’s what we do.

<h2 id="install-how-install">第一步,选择如何安装您的Magento</h2>
<a href="{{ site.gdeurl }}install-gde/continue.html">选择如何安装您的Magento</a>.

<h2 id="install-verify-prereq">第二步,Magento运行需要的一些必备组件</h2>
使用下表来验证您具有正确的Magento需要的系统必备组件。如果您使用共享的托管服务提供商，您可以跳过此步骤。

<table>
	<tbody>
		<tr>
			<th>前提条件</th>
			<th>如何检查</th>
			<th>更多信息</th>
		</tr>
	<tr>
		<td><p>Apache 2.2 or 2.4</p></td>
		<td><p>Ubuntu: <code>apache2 -v</code></p>
		<p>CentOS: <code>httpd -v</code></p></td>
		<td><p><a href="{{ site.gdeurl }}install-gde/prereq/apache.html">Apache</a></p>
			<p>(不要忘了<a href="{{ site.gdeurl }}install-gde/prereq/apache.html#apache-help-rewrite">激活rewrites和 <code>.htaccess</code></a>!)</p></td>
	</tr>
	<tr>
		<td><p>PHP 5.6.x or 5.5.x PHP7+ (PHP 5.4已不支持)</p>
			<p>如何<a href="{{ site.gdeurl }}install-gde/trouble/tshoot_install-issues.html#known-devrc-php">查看自己的php版本</a></p></td>
		<td><p><code>php -v</code></p></td>
		<td><a href="{{ site.gdeurl }}install-gde/prereq/php-ubuntu.html">PHP Ubuntu</a><br><a href="{{ site.gdeurl }}install-gde/prereq/php-centos.html">PHP CentOS</a></td>
	</tr>
	<tr><td><p>MySQL 5.6.x</p></td>
	<td><p><code>mysql -u &lt;root user name> -p</code></p></td>
	<td><a href="{{ site.gdeurl }}install-gde/prereq/mysql.html">MySQL</a></td>
	</tr>
</tbody>
</table>

<h2>第三步，安装 Magento</h2>
*	简单安装: <a href="{{ site.gdeurl }}install-gde/install/web/install-web.html">使用Magento向导进行安装</a>

	<a href="{{ site.gdeurl }}install-gde/install/web/install-web-sample-data.html">安装演示数据(基于Magento向导)</a>
*	高级安装: <a href="{{ site.gdeurl }}install-gde/install/cli/install-cli.html">使用命令行安装Magento</a>

	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-sample-data.html">安装演示数据(基于命令行)</a>

<h2>安装后</h2>
*	<a href="{{ site.gdeurl }}install-gde/install/verify.html">验证安装</a>
*	<a href="{{ site.gdeurl }}install-gde/trouble/tshoot.html">疑难解答</a>
*	<a href="{{ site.gdeurl }}install-gde/install/sample-data-after-magento.html">安装Magento后安装演示数据</a>
*	<a href="{{ site.gdeurl }}install-gde/install/post-install-config.html">配置</a>

<h2>有用的信息</h2>
在您的安装过程中, 可以使用我们的<a href="{{ site.gdeurl }}install-gde/install-quick-ref.html">快速安装参考 (教程)</a>或者<a href="{{ site.gdeurl }}install-gde/install-roadmap_part1.html">安装指南 (引用)</a>. 这些教程都是很简单的，本教程将指导你安装一个带演示数据的Magento。

使用左侧导航，可以安装其他部分。

<h2>必须的服务器权限</h2>
UNIX系统需要 `root` 权限来安装配置PHP,Composer,Grunt等，到你的服务器.如果需要安装,请确保您有 `root`权限.

您不能使用ROOT权限作为Magento的文件权限,因为Root权限可能造成webserver不能访问Magento。

您还需要 `root`权限来创建 <a href="{{ site.gdeurl }}install-gde/prereq/apache-user.html">Magento文件权限所有者(owner)</a>并添加所有者( owner)到您的webserver用户组. 要从命令行(Cli)运行任何命令，并设置 Magento cron，您将使用 Magento 文件系统所有者.
