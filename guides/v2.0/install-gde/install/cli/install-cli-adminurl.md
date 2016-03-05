---
layout: default
group: install_cli
subgroup: 05_Command-line installation
title: 显示或者更改Magento2后台地址
menu_title: 显示或者更改Magento2后台地址
menu_node: 
menu_order: 6
github_link: install-gde/install/cli/install-cli-adminurl.md
redirect_from: /guides/v1.0/install-gde/install/install-cli-adminurl.html
---

  
<h4>内容索引</h4>

请参见以下各节之一:

*	<a href="#instgde-install-cli-first">第一步</a>
*	<a href="#instgde-cli-subcommands-store-prereq">系统必备组件</a>
*	<a href="#instgde-cli-displayurl">显示Magento2后台地址</a>
*	<a href="#instgde-cli-changeurl">更改Magento2后台地址</a>

<h2 id="instgde-cli-before">第一步</h2>
{% include install/first-steps-cli.html %}
这里讨论<a href="{{ site.gdeurl }}install-gde/install/install-cli-subcommands.html#instgde-cli-subcommands-common">命令行参数</a>.

<h2 id="instgde-cli-subcommands-db-prereq">系统必备组件</h2>
运行命令之前,你需要<a href="{{ site.gdeurl }}install-gde/install/install-cli-subcommands-deployment.html">创建或更新的部署配置</a>.

<h2 id="instgde-cli-displayurl">显示Magento2后台地址</h2>
本节讨论如何使用命令行来显示Magento2后台地址 (<a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec3.html#sec3.2" target="_blank">URI</a>).

命令选项:

	magento info:adminuri

演示输入该命令后返回的数据:

	Admin Panel URI: /admin_1wgrah

你也可以在 `<your Magento install dir>/app/etc/env.php`文件中查看你的Magento2后台地址，像这样:

{% highlight php %}
<? php
  'backend' =>
  array (
    'frontName' => 'admin_1wgrah',
  ),
  <?
{% endhighlight %}

<h2 id="instgde-cli-changeurl">更改Magento2的后台地址</h2>
更改Magento2后台地址,使用<a href="{{ site.gdeurl }}/install-gde/install/install-cli-subcommands-deployment.html">magento setup:config:set</a> 命令.
