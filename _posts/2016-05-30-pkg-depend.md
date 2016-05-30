---
layout: post
title: [Solaris] IPS パッケージが、どの IPS パッケージに依存しているかを確認する
---

ターゲットとなる IPS パッケージが、どのようなパッケージに依存しているかを確認する。
pkg contents -m でもいいけど、depend だけを抜き出す方法。

```bash

 $ pkg contents -H -t depend -o fmri openstack

```

インストールされていない IPS パッケージについては、`-r` オプションを付ける必要あり。

```bash

  $ pkg contents -r -H -t depend -o fmri openstack
  cloud/openstack/cinder
  cloud/openstack/glance
  cloud/openstack/heat
  cloud/openstack/horizon
  cloud/openstack/ironic
  cloud/openstack/keystone
  cloud/openstack/neutron
  cloud/openstack/nova
  cloud/openstack/swift
  database/mysql-55
  database/mysql-55/client
  library/python/barbicanclient
  library/python/ceilometerclient
  library/python/cinderclient
  library/python/glanceclient
  library/python/heatclient
  library/python/ironicclient
  library/python/keystoneclient
  library/python/neutronclient
  library/python/novaclient
  library/python/openstackclient
  library/python/python-mysql
  library/python/saharaclient
  library/python/swiftclient
  library/python/troveclient
  network/amqp/rabbitmq
  pkg:/cloud/openstack@0.2014.2.2
  release/evaluation
  system/management/rad/module/rad-evs-controller

```
