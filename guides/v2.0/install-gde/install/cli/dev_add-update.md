---
layout: default
group: install_cli 
subgroup: 99_contrib
title: 添加或更新组件
menu_title: 添加或更新组件
menu_order: 5
menu_node: 
github_link: install-gde/install/cli/dev_add-update.md
---


贡献代码开发者可以通过修改设置Magento的 `composer.json`文件来指定组件的版本。

普通开发者, 请点击<a href="{{ site.gdeurl }}comp-mgr/bk-compman-upgrade-guide.html">更新Magento及其组件</a>.

你也可以向`composer.json`添加 `require` 代码片段或者使用 `composer require` 命令，像这样:

1.	登录Magento服务器, 切换到Magento文件权限所有者.
2.	切换到Magento的安装目录. 演示,

		cd /var/www/magento2

可以使用下列选项:

### 使用 `composer require` 命令
Command usage:

	composer require <vendor>/<name>:<version>

演示,

	composer require example/module:1.0.0

等待Composer更新依赖项和安装组件。

### 添加一个`require` 代码片段到 `composer.json`
打开 `composer.json` 并编辑.

像这样添加一个 `require` 代码片段:

```JSON
	"require": {
		"<vendor>/<name>": "<version>",
		"<vendor>/<name>": "<version>"
	}
```

保存你的更改到 `composer.json`, 退出编辑状态,再命令行输入 `composer update`

### 更多信息
如果你有问题, 请点击<a href="https://getcomposer.org/doc/articles/troubleshooting.md" target="_blank">Composer疑难解答</a>.

<!-- ABBREVIATIONS -->

*[贡献代码开发者]: 向Magento2代码库贡献过代码的开发者
