---
layout: default
group: install_cli 
subgroup: 05_Command-line installation
title: 创建或者解锁Magento2后台管理员账号
menu_title: 创建或者解锁Magento2后台管理员账号
menu_node: 
menu_order: 50
github_link: install-gde/install/cli/install-cli-subcommands-admin.md
---

  
<h4>内容索引</h4>
请参见以下各节之一:

*	<a href="#instgde-install-cli-first">第一步</a>
*	<a href="#instgde-cli-admin-prereq">系统必备组件</a>
*	<a href="#instgde-cli-admin">命令行创建Magento2管理员账号</a>
*	<a href="#instgde-cli-admin-unlock">命令行解锁Magento2管理员账号</a>


<h2 id="instgde-cli-before">第一步</h2>
{% include install/first-steps-cli.html %}
关于命令行的参数,请查阅<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands.html#instgde-cli-subcommands-common">Magento2命令行参数</a>.

<h2 id="instgde-cli-admin-prereq">系统必备组件</h2>
使用命令行之前,您需要做以下步骤:

*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-deployment.html">创建部署配置</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-enable.html">激活minimum， Magento_Authorization 和 Magento_User 模块</a>
*	创建 Magento 数据库架构

	<div class="bs-callout bs-callout-info" id="info">
		<span class="glyphicon-class">
  		<p>创建数据库的最简单方法是使用命令: <code>magento setup:upgrade</code>.</span>
	</div>

<h2 id="instgde-cli-admin">创建Magento2的后台管理员</h2>
使用命令:

	magento admin:user:create [--<parameter_name>=<value>, ...]

下表定义了参数和值。

<table>
	<col width="25%">
	<col width="65%">
	<col width="10%">
	<tbody>
		<tr>
			<th>名</th>
			<th>值</th>
			<th>是否必须?</th>
		</tr>
		<tr>
		<td><p>--admin-firstname</p></td>
		<td><p>Magento administrator user's first name.</p></td>
		<td><p>Yes</p></td>
	</tr>
	<tr>
		<td><p>--admin-lastname</p></td>
		<td><p>Magento administrator user's last name.</p></td>
		<td><p>Yes</p></td>
	</tr>
	<tr>
		<td><p>--admin-email</p></td>
		<td><p>Magento administrator user's e-mail address.</p></td>
		<td><p>Yes</p></td>
	</tr>
	<tr>
		<td><p>--admin-user</p></td>
		<td><p>Magento administrator user name.</p></td>
		<td><p>Yes</p></td>
	</tr>
	<tr>
		<td><p>--admin-password</p></td>
		<td><p>Magento administrator user password.</p>
		<p>The password must be at least 7 characters in length and must include at least one alphabetic and at least one numeric character.</p>
		<p>We recommend a longer, more complex password. Enclose the entire password string in single quotes and escape special characters with <code>/</code>. For example, <code>--admin-password=''A0b9\%t_3\`g'</code></p></td>
		<td><p>Yes</p></td>
	</tr>

	</tbody>
</table>

<h2 id="instgde-cli-admin-unlock">解锁Magento2后台管理员账号</h2>
使用此命令可以解锁被锁定，通常由于管理员帐户密码被多次输错或者被暴力破解。

	magento admin:user:unlock {user name}

您必须指定管理员的用户名称。示例:

	magento admin:user:unlock admin
	The user account "admin" has been unlocked

如果该帐户没有被锁定，将回显以下消息:

	The user account "admin" was not locked or could not be unlocked

Verify the user is an administrator, the user is active, and that the account is currently locked. To view the list of locked users in the Admin, log in as an administrator and click **System** > Permissions > **Locked Users**.

If the account doesn't exist, the following message displays:

	Couldn't find the user account "bob"

#### 相关阅读

*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-install.html">使用命令行安装Magento2</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-enable.html">激活或者禁用Magento2模块</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-uninstall-mods.html">卸载模块</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-deployment.html">创建部署配置</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-maint.html">Enable or disable maintenance mode</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-db.html">创建 Magento 数据库架构</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-store.html">配置存储</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-backup.html">备份文件, media和数据库</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-theme-uninstall.html">卸载Magento2主题</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-uninstall-langpk.html">卸载Magento2语言包</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-uninstall.html#instgde-install-uninstall">卸载Magento2</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-uninstall.html#instgde-install-magento-update">更新Magento2</a>
*	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-uninstall.html#instgde-install-magento-reinstall">重装Magento2</a>
