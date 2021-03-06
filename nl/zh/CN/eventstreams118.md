---

copyright:
  years: 2015, 2019
lastupdated: "2018-01-16"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


# 分区领导权
{: #partition_leadership }

每个分区在集群中都有一台服务器充当分区的领导者，其他服务器充当追随者。分区的所有生产和使用请求都由领导者进行处理。追随者会复制领导者的分区数据，目的是与领导者保持同步。如果追随者跟上了分区领导者的进度，那么追随者的副本就是同步副本。
{: shortdesc}

消息发送到分区领导者时，该消息不会立即可供使用者使用。领导者会将消息的记录附加到分区，并为其分配该分区的下一个偏移量数字。等到同步副本的所有追随者都已复制记录并确认已将记录写入自己的副本后，记录就会变为*已落实*。消息可供使用者使用。

如果分区的领导者失败，那么拥有同步副本的其中一个追随者会自动接管并成为该分区的领导者。实际上，每台服务器对于一些分区是领导者，而对于其他分区是追随者。分区的领导权是动态的，随着服务器的变化而变化。

应用程序无需执行特定操作来处理分区领导权的变化。Kafka 客户机库会自动重新连接到新的领导者，只不过您会在集群调整领导者期间看到等待时间增加了。
