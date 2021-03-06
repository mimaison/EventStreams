---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-04"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# 向 {{site.data.keyword.messagehub}} 團隊報告問題 - 標準和企業方案
{: #report_problem_enterprise}


如果您遇到 {{site.data.keyword.messagehub}} 的問題，請先檢查 [{{site.data.keyword.Bluemix_notm}} 狀態頁面 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://cloud.ibm.com/status?selected=status){:new_window}。
{: shortdesc}

如果您需要 {{site.data.keyword.messagehub}} 團隊的協助，請收集下列所有資訊。您可以事先提供的資訊越多，團隊就越可更有效率地協助解決問題：
{:shortdesc}

1. 您正在使用的 {{site.data.keyword.messagehub}} 服務 CRN ID 為何？提供此 ID 的作法是按一下服務之後貼上完整 {{site.data.keyword.Bluemix_notm}} 主控台 URL，或是貼上來自下列 CLI 指令的輸出：<br/>
   <pre class="pre">
   ibmcloud resource service-instance NAME
   </pre>
	{: codeblock}
2. 何時第一次發生問題（明確的時間、日期和時區）？在這之前，應用程式執行多久了？
3. 問題是否仍在發生？可以重現嗎？
4. 您的應用程式使用哪個 Kafka 用戶端？版本詳細資料為何？
5. 您的用戶端配置詳細資料為何？我們需要知道您的生產者及消費者設定，因此請列出您傳遞給生產者或消費者建立的任何非預設選項。
6. 您有顯示該問題的應用程式日誌 Snippet 嗎？
7. 您看到的問題為何？哪些主題、用戶端 ID、群組 ID 和交易 ID 受到影響？
8. 問題對您的服務有什麼影響？

您可以[提交支援要求 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](/docs/get-support?topic=get-support-getting-customer-support#using-avatar){:new_window} 在支援問題單中提供收集的資訊給 IBM。










