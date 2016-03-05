---
layout: default
group: install
subgroup: A_Verify
title: 验证安装成功
menu_title: 验证安装成功
menu_node: parent
menu_order: 1
github_link: install-gde/install/verify.md
redirect_from: /guides/v1.0/install-gde/install/verify.html
---

<!-- This topic is referred to from Magento 2 code! Don't change the URL without informing engineering! -->
<!-- Referring file: README.md owned by core -->

#### 内容索引 

*	<a href="#instgde-verify-front-sample">验证前台 (有演示数据)</a>
*	<a href="#instgde-verify-front">验证前台 (没有演示数据)</a>
*	<a href="#instgde-verify-admin">验证Magento后台</a>

<h2 id="instgde-verify-front-sample">验证前台 (有演示数据)</h2>
从浏览器打开网店前台. 演示, 如果你安装的Magento的域名是 `http://www.example.com`, 输入该地址进你的浏览器。

如果如下图显示,恭喜你安装成功了!

<p><img src="{{ site.baseurl }}common/images/install-success_store-luma.png" alt="Magento storefront with the Luma theme"></p>


<h2 id="instgde-verify-front">验证前台 (没有演示数据)</h2>

从浏览器打开网店前台. 演示, 如果你安装的Magento的域名是 `http://www.example.com`, 输入该地址进你的浏览器。

如果如下图显示,恭喜你安装成功了!

<p><img src="{{ site.baseurl }}common/images/install-success_store.png" width="450px" alt="Magento storefront which verifies a successful installation"></p>

如果不像上图所示 (只有文字，没有样式), 请看<a href="{{ site.gdeurl }}install-gde/trouble/tshoot_no-styles.html">安装之Magento2静态文件不加载样式和图片不显示;只有文字没有图片和图形</a>.

<h2 id="instgde-verify-admin">验证Magento后台</h2>

使用浏览器进入后台.演示, 如果你安装的Magento域名是 `http://www.example.com`, 后台地址是 `admin_au1nT`, 请输入 `http://www.example.com/admin_au1nT` 进你的浏览器地址栏。

(Mageno后台地址是一个固定的值，`backend-frontname`安装中会有提示.)


下图显示了示例 Magento 管理页面.如果是这样显示，恭喜您安装成功了!

<p><img src="{{ site.baseurl }}common/images/install_success_admin.png" alt="Magento Admin which verifies a successful installation"></p>

如果页面显示乱 (只有文字没有样式或图片), 请看<a href="{{ site.gdeurl }}install-gde/trouble/tshoot_no-styles.html">安装之Magento2静态文件不加载样式和图片不显示;只有文字没有图片和图形</a>.

如果显示页面找不到 404 (Not Found), 请点击<a href="{{ site.gdeurl }}install-gde/trouble/tshoot_access-browser.html">不能访问Magento2页面</a>.

`The requested URL /magento2/index.php/admin/admin/dashboard/index/key/0c81957145a968b697c32a846598dc2e/ was not found on this server.`
