---
layout: default
group: install_cli 
subgroup: 99_contrib
title: 更新Magneto
menu_title: 更新Magneto
menu_order: 2
menu_node: 
github_link: install-gde/install/cli/dev_update-magento.md
redirect_from: /guides/v2.0/install-gde/install/cli/instgde-install-magento-update-db
---

本主题讨论贡献开发者如何更新Magento而不用重新安装它。如果你不是开发者又想升级请看 <a href="{{ site.gdeurl }}comp-mgr/bk-compman-upgrade-guide.html">升级Magento和组件</a>.

如果你是贡献开发者又想升级Magento:

1.	使用有权限的用户登录到Magento服务器(for example, the <a href="{{ site.gdeurl }}install-gde/prereq/apache-user.html#install-update-depend-user-switch">切换到Magento文件系统权限拥有者</a>).
2.	
3. 保存任何更改到`composer.json` 因为以下的更改会将其覆盖:

		cd <your Magento install dir>
		cp composer.json composer.json.old

3.	更新你本地的资料库以获取最新的代码::
		
		git pull origin develop

	<div class="bs-callout bs-callout-info" id="info">
		<span class="glyphicon-class">
  			<p>如果使用<code>git pull origin develop</code>失败,请点击<a href="{{ site.gdeurl }}install-gde/trouble/git/tshoot_git-pull-origin.html">疑难解答</a>.</p> </span>
	</div>
				
3.	比较和合并你的 `composer.json.old` 与 `composer.json`。
4.	输入下面命令:

		composer update

5.	更新Magento2数据库:

		php <your Magento install dir>/bin/magento setup:upgrade

<!-- ABBREVIATIONS -->
