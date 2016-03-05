---
layout: default
group: install_cli 
subgroup: 99_contrib
title: 协助开发人员&mdash;更新, 重装Magento
menu_title: 协助开发人员&mdash;更新, 重装Magento
menu_order: 1
menu_node: parent
github_link: install-gde/install/cli/dev_options.md
redirect_from: guides/v2.0/install-gde/install/dev_updater.md
---

以下内容只对使用`git clone`从Github代码库安装的用户适用. 这通常意味着你贡献过代码到Magento CE 代码库。

*	<a href="{{ site.gdeurl }}install-gde/install/cli/dev_update-magento.html">更新Magento</a>, 使用 `git pull origin` 和 `composer update`
*	<a href="{{ site.gdeurl }}install-gde/install/cli/dev_add-update.html">添加, 删除,或者更新组件</a>, 修改 `composer.json` 并运行 `composer update`
*	<a href="{{ site.gdeurl }}install-gde/install/cli/dev_reinstall.html">重新安装Magento</a>, 在 `composer.json`中修改版本号,并运行 `composer update`，重新安装Magento2.

<div class="bs-callout bs-callout-info" id="info">
	<span class="glyphicon-class">
		<p>如果你不是贡献开发者,您执行升级和升级讨论在<a href="{{ site.gdeurl }}comp-mgr/bk-compman-upgrade-guide.html">更新Magento和组件</a>.</p> </span>
</div>

<!-- ABBREVIATIONS -->

*[贡献开发者]: 向Mageno2代码库贡献过代码的开发人员
