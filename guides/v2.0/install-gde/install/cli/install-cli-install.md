---
layout: default
group: install_cli 
subgroup: 05_Command-line installation
title: 命令行安装Magento2
menu_title: 命令行安装Magento2
menu_order: 4
github_link: install-gde/install/cli/install-cli-install.md
redirect_from:
  -  /guides/v1.0/install-gde/install/install-cli-install.html
  -  /guides/v2.0/install-gde/install/install-cli-install.html
---

<div class="bs-callout bs-callout-tip">
  <p>感到迷茫? 需要帮助? 试试我们的<a href="{{ site.gdeurl }}install-gde/install-quick-ref.html">安装快速参考 (教程)</a> 或 <a href="{{ site.gdeurl }}install-gde/install-roadmap_part1.html">安装指南 (参考)</a>.</p>
</div>
  
<h4>内容索引</h4>

请参见以下各节之一:

*	<a href="#instgde-install-cli-prereq">开始安装之前</a>
*	<a href="#instgde-install-cli-magento">使用命令行(CLI)安装Magento2</a>

请参见 <a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-uninstall.html">更新, 重装, 卸载</a>.


<h2 id="instgde-install-cli-prereq">开始安装之前</h2>

你在开始之前，请确保:

1.	您的系统满足<a href="{{ site.gdeurl }}install-gde/system-requirements.html">Magento2 系统要求</a>.
2.	您已经完成安装<a href="{{ site.gdeurl }}install-gde/prereq/prereq-overview.html">Magento2系统必备组件</a>.
3.	您知道<a href="{{ site.gdeurl }}install-gde/install/pre-install.html">您的安装或升级路径</a>.
4.	登录到Magento服务器后, <a href="{{ site.gdeurl }}install-gde/prereq/apache-user.html#install-update-depend-user-switch">切换到Magento文件系统拥有者</a>.
5.	查阅更多信息请点击<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands.html">开始使用命令行安装</a>.

<div class="bs-callout bs-callout-info" id="info">
<span class="glyphicon-class">
  <p>你必须安装<code>bin</code>子目录在你的Magento2中.</p></span>
</div>

安装程序被设计为可以运行多次，如果必要这样你就可以:

*	提供不同的值

	演示, 在配置您的 web 服务器的安全套接字层 (SSL) 后，您可以运行安装程序以设置 SSL 选项。
*	更改以前安装中的错误
*	在不同的数据库实例中安装 Magento

<div class="bs-callout bs-callout-info" id="info">
<span class="glyphicon-class">
  <ul><li>默认情况下，安装程序不会覆盖 Magento 数据库，如果你在相同的数据库实例中安装 Magento 软件。你可以使用可选的<code>cleanup-database</code> 参数来更改此行为。</li>
  <li>如果您在安装过程中出现错误,请查阅<a href="{{ site.gdeurl }}install-gde/trouble/tshoot.html">疑难解答</a>.</li></ul></span>
</div>

<h2 id="instgde-cli-help-cmds">安装程序的帮助命令</h2>

您可以运行下面的命令来寻找一些必需的参数:

<table>
<tbody>
	<tr>
		<th>安装程序参数</th>
		<th>命令</th>
	</tr>
<tr>
	<td>Language</td>
	<td><code>magento info:language:list</code></td>
</tr>
<tr>
	<td>Currency</td>
	<td><code>magento info:currency:list</code></td>
</tr>
<tr>
	<td>Time zone</td>
	<td><code>php  magento info:timezone:list</code></td>
</tr>
</tbody>
</table>

<div class="bs-callout bs-callout-info" id="info">
<span class="glyphicon-class">
  <p>如果当您运行这些命令，显示的错误,请确保您已 <a href="{{ site.gdeurl }}install-gde/install/prepare-install.html">更新安装依赖包</a>.</p></span>
</div>

	
<h2 id="instgde-install-cli-magento">使用命令行(CLI)安装Magento2</h2>
Magento2的命令行安装格式是这样的:

	magento setup:install --<option>=<value> ... --<option>=<value>

下表描述了安装选项名称和值的含义。. 比如:<a href="#install-cli-example">本地安装示例</a>.

<div class="bs-callout bs-callout-info" id="info">
<span class="glyphicon-class">
  <p>包含空格或特殊字符的任何选项必须括在单引号或双引号中。</p></span>
</div>
<table>
	<col width="35%">
	<col width="55%">
	<col width="10%">
	<tbody>
		<tr>
			<th>参数名</th>
			<th>值</th>
			<th>必填项?</th>
		</tr>
		<tr>
		<td><p>--admin-firstname</p></td>
		<td><p>管理员账号名</p></td>
		<td><p>Yes</p></td>
	</tr>
	<tr>
		<td><p>--admin-lastname</p></td>
		<td><p>管理员账号姓.</p></td>
		<td><p>Yes</p></td>
	</tr>
	<tr>
		<td><p>--admin-email</p></td>
		<td><p>管理员账号Email地址.</p></td>
		<td><p>Yes</p></td>
	</tr>
	<tr>
		<td><p>--admin-user</p></td>
		<td><p>管理员账号登录名.</p></td>
		<td><p>Yes</p></td>
	</tr>
	<tr>
		<td><p>--admin-password</p></td>
		<td><p>管理员账号的密码.</p>
			<p>密码必须至少 7 个字符的长度，并且必须包含至少一个字母和至少一个数字字符.</p>
			<p>我们建议更长、 更复杂的密码。将整个密码字符串括在单引号和特殊字符的转义<code>/</code>. For example, <code>--admin-password='A0b9\%t_3\`g'</code></p></td>
		<td><p>Yes</p></td>
	</tr>
		<tr>
		<td><p>--base-url</p></td>
		<td><p>Base URL使用来访问你的 Magento 管理员和店面在任何下列格式:</p>
		<ul><li><code>http[s]://&lt;host or ip>/&lt;your Magento install dir>/</code>.</p>
		<p><strong>提示</strong>:(<code>http://</code> or <code>https://</code>)和最后的 <em>斜杠</em> 都是必填项.</p>
		<p><code>&lt;your Magento install dir></code>是在安装 Magento 中 docroot 相对路径。取决于您如何设置您的 web 服务器和虚拟主机, 可能是<code>magento2</code>或者为空白.</p>
		<p>在本地访问Magento2, 请使用 <code>http://127.0.0.1/&lt;your Magento install dir>/</code> 或者 <code>http://127.0.0.1/&lt;your Magento install dir>/</code>.</p></li>
		<li><code>&#123;&#123;base_url&#125;&#125;</code>代表base URL defined by a virtual host setting or by a virtualization environment like Docker. For example, if you set up a virtual host for Magento with the host name <code>magento.example.com</code>, you can install the Magento software with <code>--base-url=&#123;&#123;base_url&#125;&#125;</code> and access the Magento Admin with a URL like <code>http://magento.example.com/admin</code>.</li></ul>

		</td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--backend-frontname</p></td>
		<td><p>Uniform Resource Identifier (<a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec3.html#sec3.2" target="_blank">URI</a>) to access the Magento Admin or omit this parameter to let Magento generate a random URI for you.</p>
			<p>We recommend a random URI for security purposes. A random URI is harder for hackers or malicious software to exploit.</p>
			<p>The URI displays at the end of the installation. You can display it later at any time using the <a href="{{ site.gdeurl }}install-gde/install/install-cli-adminurl.html">magento info:adminuri</a> command.</p>
			<p>If you choose to enter a value, we recommend you <em>not</em> use a common word like <code>admin</code>, <code>backend</code>, and so on. The Admin URI can contain alphanumeric values, the underscore character (<code>_</code>), and the dash character (<code>-</code>) only. It can be up to 255 characters in length.</p></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--db-host</p></td>
		<td><p>Use any of the following:</p>
		<ul><li>The database server's fully qualified host name or IP address.</li>
		<li><code>localhost</code> (default) or <code>127.0.0.1</code> if your database server is on the same host as your web server.<br><code>localhost</code> means the MySQL client library uses UNIX sockets to connect to the database. <code>127.0.0.1</code> causes the client library to use the TCP protocol. For more information about sockets, see the <a href="http://php.net/manual/en/ref.pdo-mysql.php" target="_blank">PHP <code>PDO_MYSQL</code> documentation</a>.</li></ul>
		<p><strong>Note</strong>: You can optionally specify the database server port in its host name like <code>www.example.com:9000</code></p>
</td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--db-name</p></td>
		<td><p>Name of the Magento database instance in which you want to install the Magento database tables.</p>
			<p>Default is <code>magento2</code>.</p></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--db-user</p></td>
		<td><p>User name of the Magento database instance owner.</p>
			<p>Default is <code>root</code>.</p></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--db-password</p></td>
		<td><p>Magento database instance owner's password.</p></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--db-prefix</p></td>
		<td><p>Use only if you're installing the Magento database tables in a database instance that has Magento tables in it already.</p>
		<p>In that case, use a prefix to identify the Magento tables for this installation. Some customers have more than one Magento instance running on a server with all tables in the same database.</p>
		<p>The prefix can be a maximum of five characters in length. It must begin with a letter and can include only letters, numbers, and underscore characters.</p>
		<p>This option enables those customers to share the database server with more than one Magento installation.</p></td>
		<td><p>No</p></td>
	</tr>
	
	<tr>
		<td><p>--language</p></td>
		<td><p>Language code to use in the Admin and storefront. (If you have not done so already, you can view the list of language codes by entering <code>magento info:language:list</code> from the <code>bin</code> directory.)</p></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--currency</p></td>
		<td><p>Default currency to use in the storefront. (If you have not done so already, you can view the list of currencies by entering <code>magento info:currency:list</code> from the <code>bin</code> directory.)</p></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--timezone</p></td>
		<td><p>Default time zone to use in the Admin and storefront. (If you have not done so already, you can view the list of time zones by entering <code>magento info:timezone:list</code> from the <code>bin</code> directory.)</p></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--use-rewrites</p></td>
		<td><p><code>1</code> means you use web server rewrites for generated links in the storefront and Admin.</p>
		<p><code>0</code> disables the use of web server rewrites. This is the default.</p></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--use-secure</p></td>
		<td><p><code>1</code> enables the use of Secure Sockets Layer (SSL) in all storefront URLs. Make sure your web server supports SSL before you select this option.</p>
		<p><code>0</code> disables the use of SSL with Magento. In this case, all other secure URL options are assumed to also be <code>0</code>. This is the default.</p>
		<p>To have a fully secure site, you must enable <em>both</em> <code>--use-secure=1</code> and <code>--base-url-secure=1</code>.</p></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--base-url-secure</p></td>
		<td><p>Secure base URL to use to access your Magento Admin using SSL.</code></p>
		<p>To have a fully secure site, you must enable <em>both</em> <code>--use-secure=1</code> and <code>--base-url-secure=1</code>.</p></td>
		<td><p>No</p></td>
	</tr>

	<tr>
		<td><p>--use-secure-admin</p></td>
		<td><p><code>1</code> means you use SSL to access the Magento Admin. Make sure your web server supports SSL before you select this option.</p>
		<p><code>0</code> means you do not use SSL with the Admin. This is the default.</p></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--admin-use-security-key</p></td>
		<td><p><code>1</code> causes the Magento software to use a randomly generated key value to access pages in the Magento Admin and in forms. These key values help prevent <a href="https://www.owasp.org/index.php/Cross-Site_Request_Forgery_%28CSRF%29" target="_blank">cross-site script forgery attacks</a>. This is the default.</p>
		<p><code>0</code> disables the use of the key.</p></td>
		<td><p>No</p></td>
	</tr>
	<!-- <tr> 
		<td>enable_modules=&lt;list>}</td>
		<td><p>Enable modules that are installed but disabled where <code>&lt;list></code> is a comma-separated list of modules (no spaces allowed). Use <code>php index.php help module-list</code> to list enabled and disabled modules.</p>
		<p>To enable and disable modules after installing Magento, see <a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-enable.html">Enable and disable modules</a>.</p>
		<p>For important information about module dependencies, see <a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-enable.html#instgde-cli-subcommands-enable-modules">About enabling and disabling modules</a>.</p></td>  
		<td>No</td>
	</tr>
	<tr>
		<td>disable_modules=&lt;list>}</td>
		<td><p>Disable modules that are installed and enabled where <code>&lt;list></code> is a comma-separated list of modules (no spaces allowed). Use <code>php index.php help module-list</code> to list enabled and disabled modules.</p>
		<p>To enable and disable modules after installing Magento, see <a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-enable.html">Enable and disable modules</a>.</p>
		<p>For important information about module dependencies, see <a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-subcommands-enable.html#instgde-cli-subcommands-enable-modules">About enabling and disabling modules</a>.</p></td>
		<td>No</td>
	</tr> -->
	<tr>
		<td><p>--session-save</p></td>
		<td><p>Use any of the following:</p>
		<ul><li><code>db</code> to store session data in the <a href="{{ site.gdeurl }}config-guide/database/database.html">database</a>. Choose database storage if you have a clustered database; otherwise, there might not be much benefit over file-based storage.</li>
			
			<li><code>files</code> to store session data in the file system. File-based session storage is appropriate unless the Magento file system access is slow or you have a clustered database.</li>
	</ul></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--key</p></td>
		<td><p>If you have one, specify a key to encrypt personally identifiable data in the Magento database. If you don't have one, Magento generates one for you.</p></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--cleanup-database</p></td>
		<td><p>To drop database tables before installing the Magento software, specify this parameter without a value. Otherwise, the Magento database is left intact.</p></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--db-init-statements</p></td>
		<td><p>Advanced MySQL configuration parameter. Uses database initialization statements to run when connecting to the MySQL database. Consult a reference similar to <a href="http://dev.mysql.com/doc/refman/5.6/en/server-options.html" target="_blank">this one</a> before you set any values.</p>
			<p>Default is <code>SET NAMES utf8;</code>.</p></td>
		<td><p>No</p></td>
	</tr>
	<tr>
		<td><p>--sales-order-increment-prefix</p></td>
		<td><p>Specify a string value to use as a prefix for sales orders. Typically, this is used to guarantee unique order numbers for payment processors.</p></td>
		<td><p>No</p></td>
	</tr>
	<!-- <tr>
		<td><p>--definition_format</p></td>
		<td><p>Type of definitions used by the Object Manager. Possible values are <a href="https://github.com/phadej/igbinary" target="_blank"><code>igbinary</code></a> or <code>serialized</code>.</p></td>
		<td><p>No</p></td>
	</tr> -->
<tr>
<td><p>--amqp-host</p></td>
<td><p>Enterprise Edition only. Do not use the --amqp options unless you have already set up an installation of RabbitMQ. See <a href="{{ site.gdeurl }}install-gde/prereq/install-rabbitmq.html">RabbitMQ installation</a> for more information about .</p>
<p>The host name where RabbitMQ is installed.</p></td>
<td><p>No</p></td>
</tr>
<tr>
<td><p>--amqp-port</p></td>
<td><p>Enterprise Edition only. The port to use to connect to RabbitMQ. The default is <code>5672</code>.</p></td>
<td><p>No</p></td>
</tr>
<tr>
<td><p>--amqp-user</p></td>
<td><p>Enterprise Edition only. The user name for connecting to RabbitMQ. Do not use the default user <code>guest</code>.</p></td>
<td><p>No</p></td>
</tr>
<tr>
<td><p>--amqp-password</p></td>
<td><p>Enterprise Edition only. The password for connecting to RabbitMQ. Do not use the default password <code>guest</code>.</p></td>
<td><p>No</p></td>
</tr>
	</tbody>
</table>

<div class="bs-callout bs-callout-info" id="info">
<span class="glyphicon-class">
  <p>安装 Magento2 后，如果需要激活或者禁用模块, 请点击<a href="{{ site.gdeurl }}install-gde/install/install-cli-subcommands-enable.html">激活和禁用Magento2模块</a>.</p>
  	</span>
</div>

<h4 id="install-cli-example">示例本地主机安装</h4>

**示例 1**

下面的示例 安装 Magento2 时使用以下配置:

*	Magento2安装于 `magento2` 目录，该目录位于web服务器(本地主机,`localhost`) docroot 目录下。后台路径为`admin`;
*	
*	因此:

	商店前台URL地址为 `http://127.0.0.1`

*	数据库和WEB服务器都在同一台服务器上，也就是本地主机.

	数据库名为 `magento`, 用户名密码都是 `magento`

*	启用服务器重写(rewrites)

*	Magento 管理员账号具有以下属性:

	*	管理员姓名为 `Magento User`
	*	登录用户名 `admin`  密码是 `admin123`
	*	E-mail地址是 `user@example.com`

*	默认语言为 `en_US` (U.S. 英语)
*	默认货币为美刀 (U.S. dollars)
*	默认时区为美国中区 (America/Chicago)

		magento setup:install --base-url=http://127.0.0.1/magento2/ \
		--db-host=localhost --db-name=magento --db-user=magento --db-password=magento \
		--admin-firstname=Magento --admin-lastname=User --admin-email=user@example.com \
		--admin-user=admin --admin-password=admin123 --language=en_US \
		--currency=USD --timezone=America/Chicago --use-rewrites=1

回显和下面一样表示Magento安装成功

	Post installation file permissions check...
	For security, remove write permissions from these directories: '/var/www/html/magento2/app/etc'	
	[Progress: 274 / 274]
	[SUCCESS]: Magento installation complete.
	[SUCCESS]: Admin Panel URI: /admin_puu71q


**示例 2** (附加选项)

下面的示例 安装 Magento 时使用以下配置:

*	Magento2安装于 `magento2` 目录，该目录位于web服务器(本地主机,`localhost`) docroot 目录下。后台路径为`admin`;
*	
*	因此:

	商店前台URL地址为 `http://127.0.0.1`

*	数据库和WEB服务器都在同一台服务器上，也就是本地主机.

	数据库名为 `magento`, 用户名密码都是 `magento`

*	Magento 管理员账号具有以下属性:

	*	First and last name are is `Magento User`
	*	User name is `admin` and the password is `admin123`
	*	E-mail address is `user@example.com`

*	默认语言为 `en_US` (U.S. 英语)
*	默认货币为美刀 (U.S. dollars)
*	默认时区为美国中区 (America/Chicago)
*	在安装之前请先清理干净数据库结构和数据库数据
*	给销售订单表增加表前缀 `ORD$` ,因为表前缀有特殊符号 (`$`),所以需要使用双括号转移该值。
*	session保存于数据库中
*	启用服务器URL重写(rewrite)

		magento setup:install --base-url=http://127.0.0.1/magento2/ \
		--db-host=localhost --db-name=magento \
		--db-user=magento --db-password=magento \
		--admin-firstname=Magento --admin-lastname=User --admin-email=user@example.com \
		--admin-user=admin --admin-password=admin123 --language=en_US \
		--currency=USD --timezone=America/Chicago --cleanup-database \
		--sales-order-increment-prefix="ORD$" --session-save=db --use-rewrites=1

回显和下面一样表示Magento安装成功

	Post installation file permissions check...
	For security, remove write permissions from these directories: '/var/www/html/magento2/app/etc'	
	[Progress: 274 / 274]
	[SUCCESS]: Magento installation complete.
	[SUCCESS]: Admin Panel URI: /admin_puu71q


<div class="bs-callout bs-callout-info" id="info">
<span class="glyphicon-class">
  <p>安装命令输入必须为一行，就像上面的代码使用 <code>\</code> 一样.</p></span>
</div>

#### 下一步

<a href="{{ site.gdeurl }}install-gde/install/verify.html">验证安装</a>.
