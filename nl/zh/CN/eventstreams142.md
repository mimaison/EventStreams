---

copyright:
  years: 2015, 2019
lastupdated: "2018-09-11"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}



# 向 {{site.data.keyword.messagehub}} 团队报告问题 - 经典套餐
{: #report_problem_classic}

如果使用 {{site.data.keyword.messagehub}} 时遇到问题，请首先检查 [{{site.data.keyword.Bluemix_notm}} 状态页面 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://cloud.ibm.com/status?selected=status){:new_window}。 

如果希望获得 {{site.data.keyword.messagehub}} 团队的帮助，请收集以下所有信息。预先提供的信息越多，团队帮助您解决问题的效率就会越高：
{:shortdesc}

1. {{site.data.keyword.messagehub}} 实例是在哪个 {{site.data.keyword.Bluemix_notm}} 位置（区域）供应的？例如，达拉斯或伦敦。 
2. 使用哪个接口时遇到问题？Kafka、REST、AMQP，还是网桥？
3. 第一次出现问题是什么时候（具体到时间、日期和时区）？在此之前，应用程序已经运行了多久？
4. 问题仍会发生吗？能重现问题吗？
5. 您使用的 {{site.data.keyword.messagehub}} 服务的实例标识是什么？可以通过查看服务的 VCAP_SERVICES JSON 中的“instance_id”字段来找到此标识。例如：
 ```
 "instance_id": "e662a61b-d1ff-4cce-aab9-5eae9adb9827"
 ```
6. 应用程序使用的是 Kafka 客户机还是 REST 客户机？版本详细信息是什么？
7. 客户机配置详细信息是什么？
8. 有应用程序日志片段显示此问题吗？
9. 您遇到的问题是什么？哪些主题、客户机标识和组标识受影响？
10. 问题对服务有什么影响？


您可以通过[提交支持请求 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](/docs/get-support?topic=get-support-getting-customer-support#using-avatar){:new_window}，在支持凭单中向 IBM 提供所收集的信息。










