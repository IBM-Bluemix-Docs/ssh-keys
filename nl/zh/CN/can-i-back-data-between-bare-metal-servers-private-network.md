---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-13"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# 备份和恢复

{{site.data.keyword.Bluemix_notm}} 提供了各种可扩展的[备份和存储解决方案](https://www.softlayer.com/cloud-storage)，以满足您的备份需求。但是，我们不会完成客户设备的备份。您帐户上的用户必须启动设备上所有安排的备份和一次性备份。

如果一个帐户上存在两个或更多 {{site.data.keyword.baremetal_short}}，那么可以在一个设备上备份另一个设备的数据。专用网络流量没有带宽限制，因此可以在任何时间将数据备份到共享帐户的任何设备或与这些设备之间传输数据。有若干备份解决方案可用于 {{site.data.keyword.baremetal_short}}，包括以下解决方案：

1. [Evault Backup](/infrastructure/backup/index.html) 是一种企业备份解决方案，可以跨多个服务器自动执行备份。数据会存储到企业 SAN（存储区域网络）中。
* [网络连接存储器 (NAS)](/infrastructure/network-attached-storage/nas.html) 是一种业界标准，可在服务器关闭时为关键数据提供存储。数据会存储到企业 SAN（存储区域网络）中。
* [R1Soft CDP](/infrastructure/backup/r1soft.html) 提供高性能磁盘到磁盘服务器备份，支持集中管理和数据存储库。R1Soft CDP 可在块级别保护数据，并且服务器上的唯一磁盘块在所有恢复点中仅存储一次，从而提高存储效率。
