---
layout: default
group: install_cli 
subgroup: 99_contrib
title: 重新安装Magento2
menu_title: 重新安装Magento2
menu_order: 200
menu_node: 
github_link: install-gde/install/cli/dev_reinstall.md
---

贡献开发者重新安装Magento2可以修改`composer.json`中Magento的版本号和组件的版本号并运行 `composer update`. 

贡献开发者重新安装Magento:

2.	使用有权限修改Magento文件的用户登录到Magento的服务器 (演示, 点击<a href="{{ site.gdeurl }}install-gde/prereq/apache-user.html#install-update-depend-user-switch">切换到Magento文件系统拥有者</a>).
3.	切换到Magento安装目录并备份 `composer.json`文件:

		cd <your Magento install dir>
		cp composer.json composer.json.bak

4.	打开 `composer.json` 并编辑.
5.	找到下面一行:

		 "require": {
        	"magento/product-community-edition": "<version>"
    	},

5.	替换 `<version>` 到您想更新到的版本号, `<version>` 是要使用的产品版本。. 
	
	(版本号的格式为 `2.0.x`)
<!-- is the `magento/product-community-edition` version from -->.
5.	保存你对 `composer.json`文件的更改并退出编辑.
6.	输入下面的命令:

		composer update

	等待更新

4.	<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli.html">使用命令行安装Magento</a>.
