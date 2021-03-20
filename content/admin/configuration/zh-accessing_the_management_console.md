---
title: Accessing the management console
intro: '你可以使用这个Management Console来管理应用的设置，如域名，授权和SSL'
redirect_from:
  - /enterprise/admin/articles/about-the-management-console/
  - /enterprise/admin/articles/management-console-for-emergency-recovery/
  - /enterprise/admin/articles/web-based-management-console/
  - /enterprise/admin/categories/management-console/
  - /enterprise/admin/articles/accessing-the-management-console/
  - /enterprise/admin/guides/installation/web-based-management-console/
  - /enterprise/admin/installation/accessing-the-management-console
  - /enterprise/admin/configuration/accessing-the-management-console
versions:
  enterprise-server: '*'
topics:
  - enterprise
---

# Note

* 有两种方式可以访问Mangement Console,作为网站的管理员和一个直到ip地址的随机用户，都是需要输入Management Console的密码才能登入。

### About the {% data variables.enterprise.management_console %}

Use the {% data variables.enterprise.management_console %} for basic administrative activities:
- **Initial setup**: Walk through the initial setup process when first launching {% data variables.product.product_location %} by visiting {% data variables.product.product_location %}'s IP address in your browser.
- **Configuring basic settings for your instance**: Configure DNS, hostname, SSL, user authentication, email, monitoring services, and log forwarding on the Settings page.
- **Scheduling maintenance windows**: Take {% data variables.product.product_location %} offline while performing maintenance using the {% data variables.enterprise.management_console %} or administrative shell.
- **Troubleshooting**: Generate a support bundle or view high level diagnostic information.
- **License management**: View or update your {% data variables.product.prodname_enterprise %} license.

### 关于Management Console

使用这个Management Console用来作为基本的管理员设置
- **初始化设置**: 在你的浏览器首次访问GitHub企业版服务instance的IP地址时，完成初始化设置的过程。
- **为你的instance配置基本的设置**: 在设置页面配置DNS,主机名字,SSL,用户授权,邮件,监视服务,和日志。
- **调度维护窗口**: 使用Management Console或者administrative shell来维护时，把你的GitHub企业版instance离线。
- **Troubleshooting**: 查看诊断报告。
- **证书管理**: 查看和更新你的GitHub企业版证书。

You can always reach the {% data variables.enterprise.management_console %} using {% data variables.product.product_location %}'s IP address, even when the instance is in maintenance mode, or there is a critical application failure or hostname or SSL misconfiguration.

你总是可以使用GitHub企业版服务instance的IP地址来访问Management Console，即使这个instance在mainntenace模式，或者有个严重的
应用错误，主机名字或者SSL错误配置。

To access the {% data variables.enterprise.management_console %}, you must use the administrator password established during initial setup of {% data variables.product.product_location %}. You must also be able to connect to the virtual machine host on port 8443. If you're having trouble reaching the {% data variables.enterprise.management_console %}, please check intermediate firewall and security group configurations.

为了获取到Managemant Console,你一定要使用你在一开始设置GitHub企业版instance使用的管理员密码。
你要可以接入虚拟主机的8443端口。

### Accessing the {% data variables.enterprise.management_console %} as a site administrator

The first time that you access the {% data variables.enterprise.management_console %} as a site administrator, you must upload your {% data variables.product.prodname_enterprise %} license file to authenticate into the app. For more information, see "[Managing your {% data variables.product.prodname_enterprise %} license](/enterprise/{{ currentVersion }}/admin/guides/installation/managing-your-github-enterprise-license)."

{% data reusables.enterprise_site_admin_settings.access-settings %}
{% data reusables.enterprise_site_admin_settings.management-console %}
{% data reusables.enterprise_management_console.type-management-console-password %}

### 作为网站管理员来访问Management Console

你第一次作为网站管理员来访问Management Console,要上传你的GitHub企业版证书文件来授权到这个app。
更多的信息，查看"管理你的GitHub企业版证书"。

### Accessing the {% data variables.enterprise.management_console %} as an unauthenticated user

1. Visit this URL in your browser, replacing `hostname` with your actual {% data variables.product.prodname_ghe_server %} hostname or IP address:
  ```shell
  http(s)://HOSTNAME/setup
  ```
{% data reusables.enterprise_management_console.type-management-console-password %}

### 作为一个没有授权的用户登入Management Console

### Unlocking the {% data variables.enterprise.management_console %} after failed login attempts

The {% data variables.enterprise.management_console %} locks after ten failed login attempts are made in the span of ten minutes. You must wait for the login screen to automatically unlock before attempting to log in again. The login screen automatically unlocks as soon as the previous ten minute period contains fewer than ten failed login attempts. The counter resets after a successful login occurs.

To immediately unlock the {% data variables.enterprise.management_console %}, use the `ghe-reactivate-admin-login` command via the administrative shell. For more information, see "[Command line utilities](/enterprise/{{ currentVersion }}/admin/guides/installation/command-line-utilities#ghe-reactivate-admin-login)" and "[Accessing the administrative shell (SSH)](/enterprise/{{ currentVersion }}/admin/guides/installation/accessing-the-administrative-shell-ssh/)."

### 在超过登录失败次数后解锁Management Console

10分钟内登录失败10次后，Management Console将会被锁定。

立即解锁Management Console,通过administrative shell使用ghe-reactivate-admin-login命令。
对于更多信息，查看"命令行程序"和"接入administrative shell"。
