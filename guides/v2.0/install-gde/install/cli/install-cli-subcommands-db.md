---
layout: default
group: install_cli 
subgroup: 05_Command-line installation
title: 创建 Magento2 数据库架构
menu_title: 创建 Magento2 数据库架构
menu_node: 
menu_order: 15
github_link: install-gde/install/cli/install-cli-subcommands-db.md
redirect_from: 
  -  /guides/v1.0/install-gde/install/install-cli-subcommands-db.html
  -  /guides/v2.0/install-gde/install/install-cli-subcommands-db.html
---

  
<h4>内容索引</h4>

请参见以下各节之一:

*	<a href="#instgde-install-cli-first">第一步</a>
*	<a href="#instgde-cli-subcommands-store-prereq">系统必备组件</a>
*	<a href="#instgde-cli-dbconfig">配置数据库和添加数据</a>


<h2 id="instgde-cli-before">第一步</h2>
{% include install/first-steps-cli.html %}
关于命令行的参数,请看<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands.html#instgde-cli-subcommands-common">Magento2命令行参数</a>.

<h2 id="instgde-cli-subcommands-db-prereq">系统必备组件</h2>
运行命令之前您必须<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-deployment.html">创建或更新的部署配置</a>.

<h2 id="instgde-cli-dbconfig">配置数据库和添加数据</h2>
使用命令:

	magento setup:db-schema:upgrade
	magento setup:db-data:upgrade

如果需要查看数据库状态，请输入

	magento setup:db:status

#### 相关主题

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
