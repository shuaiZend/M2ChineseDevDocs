---
layout: default
group: install_cli 
subgroup: 05_Command-line installation
title: 备份还原Magento文件, media和数据库
menu_title: 备份还原Magento文件, media和数据库
menu_node: 
menu_order: 100
github_link: install-gde/install/cli/install-cli-backup.md
redirect_from:
  -  /guides/v1.0/install-gde/install/install-cli-backup.html
  -  /guides/v2.0/install-gde/install/install-cli-backup.html
---

  
<h4>内容索引</h4>

请参见以下各节之一:

*	<a href="#instgde-cli-uninst-back-over">备份概述</a>
*	<a href="#instgde-cli-before">第一步</a>
*	<a href="#instgde-cli-uninst-back">备份</a>
*	<a href="#instgde-cli-uninst-roll">还原</a>

<h2 id="instgde-cli-uninst-back-over">备份概述</h2>
使用这个将备份以下内容:

*	Magento系统文件 (包括 <code>var</code> 和 <code>pub/static</code>目录)
*	<code>pub/media</code> 目录
*	Magento的数据库

备份文件将储存于`var/backups` 目录并可以使用 <a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-uninstall-mods.html#instgde-cli-uninst-mod-roll">magento setup:rollback</a> 命令进行还原.

备份之后, 你可以<a href="#instgde-cli-uninst-roll">回滚还原</a>到之前.

<h2 id="instgde-cli-before">第一步</h2>
{% include install/first-steps-cli.html %}
请参见<a href="{{ site.gdeurl }}install-gde/install/install-cli-subcommands.html#instgde-cli-subcommands-common">命令参数</a>.

<h2 id="instgde-cli-uninst-back">备份</h2>
命令使用:

	magento setup:backup [--code] [--media] [--db]

该命令将执行以下任务:

1.	将商店切换于维护模式。
2.	执行以下命令选项之一。

	<table>
	<col width="25%">
	<col width="40%">
	<col width="35%">
	<tbody>
		<tr>
			<th>命令参数</th>
			<th>意思</th>
			<th>备份文件的名字和位置</th>
		</tr>
		
	<tr>
		<td><p>--code</p></td>
		<td><p>备份Magento2文件系统(包括<code>var</code>和<code>pub/static</code> 目录).</p></td>
		<td><p>var/backups/&lt;timestamp>_filesystem.tgz</p></td>
	</tr>
	<tr>
		<td><p>--media</p></td>
		<td><p>备份<code>pub/media</code>目录.</p></td>
		<td><p>var/backups/&lt;timestamp>_filesystem_media.tgz</p></td>
	</tr>
	<tr>
	<tr>
		<td><p>--db</p></td>
		<td><p>备份Magento2的数据库.</p></td>
		<td><p>var/backups/&lt;timestamp>_db.gz</p></td>
	</tr>
	<tr>
	</tbody>
	</table>

3.	关闭维护模式。

演示, 备份文件和数据,

	magento setup:backup --code --db

会回显类似于下面的显示消息:

	Enabling maintenance mode
	Code backup is starting...
	Code backup filename: 1434133011_filesystem.tgz (The archive can be uncompressed with 7-Zip on Windows systems)
	Code backup path: /var/www/html/magento2/var/backups/1434133011_filesystem.tgz
	[SUCCESS]: Code backup completed successfully.
	DB backup is starting...
	DB backup filename: 1434133011_db.gz (The archive can be uncompressed with 7-Zip on Windows systems)
	DB backup path: /var/www/html/magento2/var/backups/1434133011_db.gz
	[SUCCESS]: DB backup completed successfully.
	Disabling maintenance mode

<h2 id="instgde-cli-uninst-roll">回滚还原</h2>
本节讨论如何回滚到以前创建的备份。你必须知道要还原的备份文件的文件名称。

找到备份文件的文件名称输入:

	magento info:backups:list

备份文件的文件名中的第一个字符串是时间戳。

要回滚到以前的备份，请输入:

	magento setup:rollback [-c|--code-file="<name>"] [-m|--media-file="<name>"] [-d|--db-file="<name>"]

演示, 要回滚还原的文件名为 `1440611839_filesystem_media.tgz`, 输入

	magento setup:rollback -m 1440611839_filesystem_media.tgz

会回显类似于下面的显示的消息:

	[SUCCESS]: Media rollback completed successfully.
	Please set file permission of bin/magento to executable
	Disabling maintenance mode

<div class="bs-callout bs-callout-info" id="info">
  <p>如果回显的消息中显示<code>Segmentation fault</code>, 请点击<a href="{{ site.gdeurl }}install-gde/trouble/tshoot_segfault.html">Magento回滚还原失败</a>.</p>
</div>

#### 相关主题

*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-install.html">使用命令行安装Magento2</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-enable.html">激活或禁用Magento2模块</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-maint.html">激活或关闭Magento2维护模式</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-deployment.html">创建部署配置</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-db.html">创建 Magento2 数据库架构</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-store.html">配置储存</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-admin.html">创建Magento2管理员账号</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-uninstall.html#instgde-install-uninstall">卸载Magento2</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-uninstall.html#instgde-install-magento-update">更新Magento2</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-uninstall.html#instgde-install-magento-reinstall">重装Magento2</a>
