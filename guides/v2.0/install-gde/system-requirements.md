---
layout: default
group: install_pre
subgroup: Getting Started
title: Magento系统需求
menu_title: Magento2系统需求
menu_node: parent
menu_order: 1
github_link: install-gde/system-requirements.md
redirect_from: /guides/v1.0/install-gde/system-requirements.html
---

### 操作系统(Linux x86-64)

RedHat Enterprise Linux (RHEL), CentOS, Ubuntu, Debian等Linux发行版本都可以.

### Composer (最新稳定版)
Composer 是 PHP 用来管理依赖（dependency）关系的工具。你可以在自己的Magento中声明所依赖的外部工具库（libraries），Composer 会帮你安装这些依赖的库文件。

### Web服务器
*	<a href="http://httpd.apache.org/download.cgi" target="_blank">Apache 2.2 or 2.4</a>
	
	apache的`mod_rewrite`模块必须激活. `mod_rewrite`是用来重写URL的.更多信息请浏览<a href="{{ site.gdeurl }}install-gde/prereq/apache.html">我们的Apache文档</a>.
*	nginx 1.8 (或者 <a href="http://nginx.org/en/linux_packages.html#mainline" target="_blank">最新版本</a>)

### 数据库

MySQL 5.6 (Oracle or Percona)
	
### PHP 

*	5.6.x
*	5.5.x 
*	7.0.2 (Magento2.0.1以上版本支持)

安装文档: <a href="{{ site.gdeurl }}install-gde/prereq/php-centos.html" target="_blank">CentOS</a>, <a href="{{ site.gdeurl }}install-gde/prereq/php-ubuntu.html" target="_blank">Ubuntu</a>

#### 需要的PHP扩展:

*	<a href="http://php.net/manual/en/book.bc.php" target="_blank">bc-math</a> <img src="{{ site.baseurl }}common/images/ee-only_small.png">
*	<a href="http://php.net/manual/en/book.curl.php" target="_blank">curl</a>
*	<a href="http://php.net/manual/en/book.image.php" target="_blank">gd</a>, <a href="http://php.net/manual/en/book.imagick.php" target="_blank">ImageMagick 6.3.7</a> (or later) or both
*	<a href="http://php.net/manual/en/book.intl.php" target="_blank">intl</a>
*	<a href="http://php.net/manual/en/book.mbstring.php" target="_blank">mbstring</a>
*	<a href="http://php.net/manual/en/book.mcrypt.php" target="_blank">mcrypt</a>
*	<a href="http://php.net/manual/en/book.mhash.php" target="_blank">mhash</a>
*	<a href="http://php.net/manual/en/book.openssl.php" target="_blank">openssl</a>
*	<a href="http://php.net/manual/en/ref.pdo-mysql.php" target="_blank">PDO/MySQL</a>
*	<a href="http://php.net/manual/en/book.simplexml.php" target="_blank">SimpleXML</a>
*	<a href="http://php.net/manual/en/book.soap.php" target="_blank">soap</a>
*	<a href="http://php.net/manual/en/book.xml.php" target="_blank">xml</a>
*	<a href="http://php.net/manual/en/book.xsl.php" target="_blank">xsl</a>
*	<a href="http://php.net/manual/en/book.zip.php" target="_blank">zip</a> 

#### PHP OPcache
We strongly recommend you verify the  <a href="http://php.net/manual/en/intro.opcache.php" target="_blank">PHP OPcache</a> is enabled for performance reasons. The OPcache is enabled in many PHP distributions. To verify if it is installed, see our PHP documentation for <a href="{{ site.gdeurl }}install-gde/prereq/php-centos.html" target="_blank">CentOS</a> or <a href="{{ site.gdeurl }}install-gde/prereq/php-ubuntu.html" target="_blank">Ubuntu</a>.

If you must install it separately, see the <a href="http://php.net/manual/en/opcache.setup.php" target="_blank">PHP OPcache documentation</a>.

#### PHP设置
We recommend particular PHP configuration settings, such as `memory_limit`, that can avoid common problems when using Magento.

For more information, see our recommendations for <a href="{{ site.gdeurl }}install-gde/prereq/php-centos.html#instgde-prereq-timezone">CentOS</a> and <a href="{{ site.gdeurl }}install-gde/prereq/php-ubuntu.html#instgde-prereq-timezone">Ubuntu</a>. 

### SSL
*	A valid security certificate is required for HTTPS.
*	Self-signed SSL certificates are not supported.

### 邮件服务器
Mail Transfer Agent (MTA) or an SMTP server

### Magento2还可以利用以下技术:
*	<a href="{{ site.gdeurl }}config-guide/redis/config-redis.html">Redis</a> version 3.0 for page caching
*	<a href="{{ site.gdeurl }}config-guide/varnish/config-varnish.html">Varnish</a> version 3.5 or latest stable 4.x version for page caching
*	<a href="{{ site.gdeurl }}config-guide/memcache/memcache.html">memcached</a> latest stable version for session storage with either `memcache` or `memcached` PHP extensions (latest stable version)

*	Magento Enterprise Edition (EE) only <img src="{{ site.baseurl }}common/images/ee-only_small.png">

	*   Apache Solr 
 
    	<a href="{{ site.gdeurl }}config-guide/solr/solr-overview.html">Solr search</a> can be used as a search provider. Available for Magento Enterprise Edition (EE) only.

	*	RabbitMQ 

		<a href="{{ site.gdeurl }}config-guide/mq/rabbitmq-overview.html">RabbitMQ</a> can be used to publish messages to queue and to define the consumers that receive the messages asynchronously. Available for Magento EE only.

	*	Three master databases 

		These <a href="{{ site.gdeurl }}config-guide/multi-master/multi-master.html">master databases</a> provide scalability advantages for different functional areas of the Magento application: checkout, orders, and product data. Available for Magento EE only.

###可选项，但是建议使用的:

*	<a href="http://xdebug.org/download.php" target="_blank">php_xdebug2.2.0</a> or later (development environments only; can have an adverse effect on performance)

<div class="bs-callout bs-callout-info" id="info">
	<p>There is a known issue with <code>xdebug</code> that can affect Magento installations or access to the storefront or Magento Admin after installation.</p>
	<p>For details, see <a href="{{ site.gdeurl }}install-gde/trouble/tshoot_install-issues.html#known-devbeta-xdebug">Known issue with xdebug</a>.</p>
</div>

*	PHPUnit (as a command-line tool) 4.1 or later

### 文档

<a href="{{ site.gdeurl }}install-gde/prereq/prereq-overview.html">安装Magento2必备组件</a>
