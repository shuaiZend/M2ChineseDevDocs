---
layout: default
group: fedg
subgroup: D_CSS_G
title: 自定义主题样式的简单方法
menu_title: 自定义主题样式的简单方法
menu_order: 1
github_link: frontend-dev-guide/css-guide/css_quick_guide_approach.md
---
<h2>本主题是什么</h2>
假设您创建了一个新的主题从默认的Magento主题Magento blank或luma继承，并选择 <a href="{{site.gdeurl}}frontend-dev-guide/css-guide/css_quick_guide_mode.html">LESS编译模式</a>.下一个是什么?在何处添加样式更改?本主题提供快速解答。

<h3>内容索引</h3>
- <a href="#simple_extend">最简单的方式来扩展父样式</a> 
- <a href="#simple_override">最简单的方法来重写父样式 (即，重写默认 Magento UI 库变量)</a>
- <a href="#structured_changes">添加组织结构的变化</a>
	- <a href="#structured_extend">扩展组件的样式</a>
	- <a href="structured_override">重写组件的样式</a>


<h2 id="simple_extend">最简单的方式来扩展父样式</h2> 

要扩展父主题的样式在你的主题:
<ol>
<li>在你的主题目录创建<code>web/css/source</code> 子目录. </li>
<li>创建一个<code>_extend.less</code> 文件. 它的路径看起来像以下: 

<pre>
&lt;theme_dir&gt;/
│&nbsp;&nbsp;├──&nbsp;web/
│&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├──&nbsp;css/
│&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├──&nbsp;source/
│&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├──_extend.less
...
</pre>
</li>
<li>添加你的Less代码到这个文件.</li>
</ol>

扩展主题使用 <code>_extend.less</code>最简单的办法是一切使用默认主题的样式, 但是你想更改或者增加更多的样式.

<h2 id="simple_override">最简单的方法来重写父样式</h2>

重写父样式 (即，重写默认 Magento UI 库变量):
<ol>
<li>在你的主题目录创建<code>web/css/source</code>子目录. </li>
<li>并在这个文件下创建一个<code>_theme.less</code>文件. 然后看起来像下面的路径:

<pre>
&lt;theme_dir&gt;/
│&nbsp;&nbsp;├──&nbsp;web/
│&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├──&nbsp;css/
│&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├──&nbsp;source/
│&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├──_theme.less
...
</pre>
</li>

但是你要记住 <code>_theme.less</code> 重写父级 <code>_theme.less</code>. 

<li>Copy all variables you need from the parent <code>_theme.less</code>, including those which will not be changed. For example if your theme inherits from Blank, the <code>_theme.less</code> you should copy from is located at <code>&lt;Magento_Blank_theme_dir&gt;/web/css/source/_theme.less</code></li>
<li>Make the necessary changes.</li>
</ol>

The drawback of this approach is that you need to monitor and manually update your files whenever the parent's <code>_theme.less</code> is updated.

<h2 id="structured_changes">Adding structured changes</h2>

To make your changes easier to read and support, structure them by adding a separate overriding or extending <code>.less</code> files for each <a href="{{site.gdeurl}}frontend-dev-guide/css-topics/theme-ui-lib.html#library_elements" target="_blank">Magento UI library component</a> you change. Let's use the <code>button</code> component implemented in <code>_button.less</code> as an illustration.

<h3 id="structured_extend">扩展组件的样式</h3>
<ol>
<li>In your theme directory, create a <code>web/css/source</code> sub-directory. </li>
<li>Add <code>_buttons_extend.less</code> and <code>_extend.less</code> here. The path to the files looks like following: 

<pre>
&lt;theme_dir&gt;
│&nbsp;&nbsp;├──&nbsp;web/
│&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├──&nbsp;css/
│&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├──&nbsp;source/
│&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├──_buttons_extend.less
│&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├──_extend.less
...
</pre>
</li>
<li>In <code>_buttons_extend.less</code> add your styles for the button component.</li>
<li>
In <code>_extend.less</code> register the <code>_buttons_extend.less</code> by adding the following code: 
<pre>
@import '_buttons_extend.less'; 
</pre>
</li>
</ol>

<h3 id="structured_override">重写组件的样式</h3>
To extend the parent theme's styles for buttons in your theme:
<ol>
<li>In your theme directory, create a <code>web/css/source</code> sub-directory. </li>
<li>Create a <code>_buttons.less</code> file here. The path to it looks like following: 

<pre>
&lt;theme_dir&gt;/
│&nbsp;&nbsp;├──&nbsp;web/
│&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├──&nbsp;css/
│&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├──&nbsp;source/
│&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├──_buttons.less
...
</pre>
This file overrides the <code>_buttons.less</code> of the parent theme.
</li>

<li>添加您的按钮组件的样式。如果该文件为空，然后为该组件没有样式应用.</li>
</ol>

<h2>推荐的阅读</h2>
<ul>
<li><a href="{{site.gdeurl}}frontend-dev-guide/css-topics/css_debug.html" target="_blank">调试样式</a></li>
<li><a href="{{site.gdeurl}}frontend-dev-guide/css-topics/css-preprocess.html" target="_blank">CSS 预处理</a></li>
<li><a href="{{site.gdeurl}}frontend-dev-guide/css-topics/theme-ui-lib.html" target="_blank">Magento UI 库</a></li>
</ul>
