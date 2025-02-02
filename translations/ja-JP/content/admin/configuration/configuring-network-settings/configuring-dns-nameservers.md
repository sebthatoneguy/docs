---
title: DNSネームサーバの設定
intro: '{% data variables.product.prodname_ghe_server %} は、動的ホスト構成プロトコル (DHCP) のリースがネームサーバーを提供するときに、DNS 設定に対して DHCP を使用します。 ネームサーバがDHCPのリースで提供されない場合、あるいは特定のDNS設定を使う必要がある場合は、手動でネームサーバを指定できます。'
redirect_from:
  - /enterprise/admin/guides/installation/about-dns-nameservers
  - /enterprise/admin/installation/configuring-dns-nameservers
  - /enterprise/admin/configuration/configuring-dns-nameservers
  - /admin/configuration/configuring-dns-nameservers
versions:
  ghes: '*'
type: how_to
topics:
  - Enterprise
  - Fundamentals
  - Infrastructure
  - Networking
shortTitle: Configure DNS servers
---

指定するネームサーバは、{% data variables.product.product_location %}のホスト名を解決できなければなりません。

{% data reusables.enterprise_installation.changing-hostname-not-supported %}

## 仮想マシンのコンソールを使ったネームサーバの設定

{% data reusables.enterprise_installation.open-vm-console-start %}
2. インスタンスに対してネームサーバーを設定します。
{% data reusables.enterprise_installation.vm-console-done %}

## 管理シェルを使ったネームサーバの設定

{% data reusables.enterprise_installation.ssh-into-instance %}

2. To edit your nameservers, use the `ghe-setup-network` command in visual mode. 詳しい情報については、「[コマンドラインユーティリティ](/admin/configuration/configuring-your-enterprise/command-line-utilities#ghe-setup-network)」を参照してください。

  ```shell
  ghe-setup-network -v
  ```

5. To add your new nameserver entries to {% data variables.product.product_location %}, run the following:

  ```shell
  sudo service resolvconf restart
  sudo service dnsmasq restart
  ```
