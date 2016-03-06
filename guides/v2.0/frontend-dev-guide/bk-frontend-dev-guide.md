---
layout: default
group: fedg
title: Magento前端开发手册
menu_title: 介绍
menu_order: 1
github_link: frontend-dev-guide/bk-frontend-dev-guide.md
redirect_from: /guides/v1.0/frontend-dev-guide/bk-frontend-dev-guide.html
---

<h2 id="overview-introduction">介绍</h2>
本文档提供了创建和安装自定义店面主题的 Magento 应用说明。它描述了 Magento 的内容呈现过程，如何高效地创建一个主题所需要的系统的视图层。该文档还是Magento前端开发人员的必读手册。

开发一个自定义模块的视图部分和定制 Magento 管理员面板设计是超出了本手册的范围.

前端开发人员可以使用本指南来创建自定义主题，来为特定客户量身定制的Magento店面.

<p>根据不同开发技能水平,您可以自定义不同的内容到您的网店:</p>
<ul>
<li><p>您可以使用层叠样式表 (CSS) 来更改颜色和各种接口组件，替换图像，外观和感觉的网站相对简单的更改。</p>
<p>对页面进行任何结构的更改 &mdash; 需要加载默认模块到你的网站.</p>
<p>这是需要最少知识和和精力的一个知识点.</p></li>
<li><p>只需要这一小步就可以更改模块HTML所呈现的样式和图片.</p>
<p>这就要求基本的 PHP 技能来调整 PHTML 模板文件.</p>
<p>虽然涉及 PHP 编码，这通常是复制和粘贴到一个新的模板文件.</p>
<p>这可能是因为现有的HTML代码没有足够的css类来提供给你更改模板样式.</p></li>
<li><p>下一个等级的开发水平，需要作出结构性的更改，比如需要做到页面之间功能的移动功能或完全不同的页面.</p>
<p>这是使用 Magento 布局引擎实现。不需要进行 PHP 编码进行布局的更改，但布局引擎是比较复杂。</p></li>
<li><p>最后，您可以开发新的模块，将新的自定义功能添加到您的网站或扩展现有的 Magento2 或第三方模块所提供的功能.</p>
<p>本指南不解决这三个级别的自定义.</p>
<p>有关如何开发新模块请参阅开发者指南的详细信息.</p>
<p>这就要求除了前述领域各种知识的 PHP 编程知识.</p></li>
</ul>

<div class="bs-callout bs-callout-info" id="info">
<p>There have been some inquiries about the status of the Visual Design Editor (VDE), which is currently part of the Magento development code base. The VDE enables assigning and unassigning themes, editing theme CSS and JS files, changing page layouts, and managing blocks and their positions on pages in a WYSIWYG mode. We'd like to clarify that to meet higher priority objectives, the VDE will <em>not</em> be part of the initial Magento release. Future plans for the VDE will be communicated at a later point in time. You are welcome to continue to provide input on the VDE, but please note that we will not be actively reviewing or actioning these comments in the near term.</p>
</div>

<h2 id="fedg-prereqs">前端开发系统必备组件</h2>

要执行本指南中讨论的内容，您需要运行安装 Magento2和在您的设备上安装以下浏览器版本:

*	Internet Explorer 9 or later (Windows)
*	Mozilla Firefox latest, latest-2 (any operating system)
*	Google Chrome latest, latest-2 (any operating system)
*	Apple Safari 5 or later (Mac OS)
*	Apple Safari Mobile for iPad, iPad Mini, iPad with Retina Display (iOS 6 or later), for Desktop Frontend
*	Apple Safari Mobile for iPhone 4 or later; iOS 6 or later, for Mobile Frontend

使用手册，您需要熟悉以下技能:

*	CSS and CSS 3
*	HTML and HTML 5
*	XML
*	JavaScript
*	Responsive Web Design (RWD) 响应式网页设计

#### 相关主题:

*	<a href="{{ site.gdeurl }}frontend-dev-guide/themes/theme-general.html">主题(Theme)</a>
*	<a href="{{ site.gdeurl }}frontend-dev-guide/css-topics/theme-ui-lib.html">Magento UI库</a>
*	<a href="{{ site.gdeurl }}frontend-dev-guide/css-topics/css-overview.html">样式表(CSS) </a>
*	<a href="{{ site.gdeurl }}coding-standards/code-standard-javascript.html">JavaScript编码标准</a>
*	<a href="{{ site.gdeurl }}frontend-dev-guide/responsive-web-design/rwd_overview.html">响应式网页设计(RWD)</a>
*	<a href="{{ site.gdeurl }}architecture/behavior/xlate.html">翻译</a>

