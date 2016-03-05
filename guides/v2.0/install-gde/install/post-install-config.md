---
layout: default
group: install
subgroup: B_Verify
title: 配置Magento应用
menu_title: 配置Magento应用
menu_node: parent
menu_order: 1
github_link: install-gde/install/post-install-config.md
---

## 配置Magento应用
现在，您已经完成安装 Magento 的应用程序，您需要配置它。本主题提供了一些建议配置设置。

#### Contents
*	<a href="#post-install-cron">设置cron</a>
*	<a href="#post-install-secy">安全配置</a>
*	<a href="#post-install-rewrites">激活Apach重写</a>
*	<a href="#post-install-server">服务器设置</a>
*	<a href="#post-install-ee">设置Magento商业版(Only Magento EE)</a>

<h2 id="post-install-cron">设置cron</h2>
cron(UNIX 任务计划程序)&mdash;对 Magento 的日常运作至关重要。它计划运行重新索引、 通讯、 电子邮件、 站点地图，等等之类。相当于windows下的计划任务.

安装好Magento后, 设置一个 *crontab* 给Magento文件系统所有者.

{% include config/setup-cron.md %}

<h2 id="post-install-secy">安全设置</h2>
安装之后,我们需要做这些:

*	请确保您的文件所有权和权限设置正确。
*	强烈推荐<a href="{{ site.gdeurl }}install-gde/install/cli/install-cli-adminurl.html">更改Magento2的后台地址</a> 把默认的 `admin` 改为其他不易猜测到的。
*	确保<a href="{{ site.gdeurl }}config-guide/secy/secy-xframe.html">`X-Frame-Option` HTTP header</a> 设置正确。
*	采取预防措施，防止跨站点脚本 (XSS),请使用<a href="{{ site.gdeurl }}frontend-dev-guide/templates/template-security.html">安全的模板</a>
<!-- 设置的角色和受限制的用户 (Admin) -->

<h2 id="post-install-rewrites">激活Apache服务器重写(URL rewrite)</h2>
如果你使用 Apache web 服务器，为了Magento能显示正确的页面，您必须激活Apache的URL重写。否则，你看到的是404页面，或者css等静态资源没有被正确加载.

<a href="{{ site.gdeurl }}install-gde/prereq/apache.html#apache-help-rewrite">Apache重写 (URL Rewrite)</a>

<h2 id="post-install-server">服务器设置</h2>
本节简介绍我们建议您服务器上运行的 Magento 的设置。其中一些设置不直接涉及 Magento;这些建议只作为提供。
#### 日志

UNIX `logrotate`能够让你管理服务器生成的大量日志,包括日志切割,压缩，删除并Email发送给你。每个日志文件可以处理每日、 每周、 每月，或者当日志文件超过指定的大小。

更多信息,请看<a href="http://linuxconfig.org/logrotate-8-manual-page" target="_blank">logrotate命令页面</a> 或者看这样一个<a href="http://www.thegeekstuff.com/2010/07/logrotate-examples" target="_blank">教程</a>.

#### 设置 iptables 规则，使不同类型的 Magento 服务间进行通信。.

如果您的Magento配置于多台服务器上，必须使用Iptables打开端口让其通信。例如，如果您使用 Solr 搜索引擎 Magento 企业版 (EE)，您必须启用它与 web 服务器进行通信。如果您有多个网络节点，您必须启用它们来彼此通信。

更多信息:

*	Ubuntu: <a href="https://help.ubuntu.com/community/IptablesHowTo" target="_blank">Ubuntu文档页面</a>.
*	CentOS: <a href="http://wiki.centos.org/HowTos/Network/IPTables" target="_blank">CentOS how-to</a> and <a href="http://www.centos.org/docs/4/4.5/Security_Guide/s1-firewall-ipt-basic.html" target="_blank">CentOS reference page</a>.

#### 安全增强 Linux (SELinux) 规则

我们不论你使用不使用SELinux;如果使用您必须配置为能让 Magento 服务之间能相互通信。

更多信息:

*	Ubuntu: <a href="https://debian-handbook.info/browse/stable/sect.selinux.html" target="_blank">Debian handbook</a>
*	CentOS: <a href="https://wiki.centos.org/HowTos/SELinux" target="_blank">CentOS wiki</a>

#### 设置E-mail服务器

Magento需要一个Email服务器.我们不论你是否使用独立服务器，但是请看下面:

*	Postfix for CentOS (<a href="https://www.digitalocean.com/community/tutorials/how-to-install-postfix-on-centos-6" target="_blank">digitalocean tutorial</a>, <a href="https://www.centos.org/docs/5/html/Deployment_Guide-en-US/ch-email.html" target="_blank">CentOS documentation</a>)	
*	Postfix for Ubuntu (<a href="https://www.digitalocean.com/community/tutorials/how-to-install-and-setup-postfix-on-ubuntu-14-04" target="_blank">digitalocean tutorial</a>, <a href="https://help.ubuntu.com/community/MailServer" target="_blank">Ubuntu documentation</a>)

<h2 id="post-install-ee">Magento商业版的设置</h2>
<img src="{{ site.baseurl }}common/images/ee-only_large.png">

只有当您使用Magento商业版 (Magento EE)，您可以按以下配置:

*	<a href="{{ site.gdeurl }}config-guide/solr/solr-overview.html">Apache Solr search</a>
*	<a href="{{ site.gdeurl }}config-guide/multi-master/multi-master.html">Split databases for checkout, order management, and other Magento database tables</a>
*	<a href="{{ site.gdeurl }}config-guide/mq/rabbitmq-overview.html">Message queues</a>

