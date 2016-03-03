---
layout: default
group: install2
subgroup: Z_continue
title: Next&mdash;Choose how to install the Magento software
menu_title: Next&mdash;Choose how to install the Magento software
menu_node: parent
menu_order: 1
github_link: install-gde/continue.md
redirect_from: 
  - /guides/v1.0/install-gde/continue.html
  - /guides/v2.0/install-gde/install/pre-install.html
---

## 让我们开始吧!
本安装指南可以帮助您在没有安装过 Magento 的服务器上安装 Magento. (已经安装过? 请<a href="{{ site.gdeurl }}install-gde/basics/basics_magento-installed.html">点击这里</a>.)

<h2 id="install-overview-audience">选择如何安装 Magento 软件</h2>
想简单方便的安装 Magento 您需要使用 <a href="https://getcomposer.org/doc/00-intro.md" target="_blank">Composer</a>下载Magento2的代码

如何开始，请参考下表.

<table>
	<!-- <col width="25%">
	<col width="65%">
	<col width="10%"> -->
	<tbody>
		<tr>
			<th>需要</th>
			<th>介绍</th>
			<th>高级安装步骤</th>
			<th>链接</th>
		</tr>
	<tr>
		<td><p>简单安装,不需要使用命令行, 有自己的服务器</p></td>
		<td><p>一些技术的专业知识，能对 Magento 服务器进行命令行访问.</p></td>
		<td><ol><li>下载一个压缩的文件，包含的 Magento .</li>
			<li>在服务器上解压缩文件,如果不会可以咨询服务器管理员.</li>
			<li>使用命令行或者安装向导进行安装.</li></ol>
		</td>
		<td><p><a href="{{ site.gdeurl }}install-gde/prereq/zip_install.html">简单安装(拥有服务器)</a></p></td>
	</tr>
	<tr>
		<td><p>共享空间,简单安装, 没有命令行访问权限</p></td>
		<td><p>使用共享空间, 拥有较少的技术支持, 对Magento服务器的权限有限.</p></td>
		<td><ol><li>下载Magento安装压缩包到服务器.</li>
			<li>在服务器上解压缩安装包.</li>
			<li>使用安装向导进行安装.</li></ol>
		</td>
		<td><p><a href="{{ site.gdeurl }}install-gde/install/hosted/hosted_start.html">简单安装 (共享空间)</a></p></td>
	</tr>
	<tr>
		<td><p>系统集成商, 软件包</p></td>
		<td><p>想要完全控制所有组件安装，完整的Magento服务器权限，技术很强，可能会与其他组件打包 Magento CE.</p></td>
		<td><ol><li>创建Composer<em>项目</em>包含所有的组件.</li>
			<li>使用 Composer更新依赖包; 使用 <code>composer create-project</code>获取Magento所有的依赖包.</li>
			<li>使用命令行或者安装向导进行安装.</li></ol>
		<td><p><a href="{{ site.gdeurl }}install-gde/prereq/integrator_install.html">获得所有的Magento依赖包</a></p></td>
	</td>

	</tr>
	<tr>
		<td><p>协助开发人员</p></td>
		<td><p>贡献代码到Magento代码仓库, 较高的技术水平, 有自己的Magento开发服务器,懂Github和Composer.</p></td>
		<td><ol><li>从Github克隆Magento2的代码.</li>
			<li>使用Composer安装依赖包.</li>
			<li>使用命令行或者安装向导进行安装.</li></ol>
		<td><p><a href="{{ site.gdeurl }}install-gde/prereq/dev_install.html">克隆Magento代码</a></p></td>
	</td>
	</tr>
	
	
	</tbody>
</table>
