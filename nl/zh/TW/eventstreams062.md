---

copyright:
  years: 2015, 2019
lastupdated: "2019-01-14"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# 選擇 Kafka 用戶端以搭配 {{site.data.keyword.messagehub}} 使用
{: #kafka_clients}

若要使用 Kafka API 搭配 {{site.data.keyword.messagehub}}，請選擇下列其中一種用戶端：

* 官方 Java 用戶端。這是最佳的選項，因為它包含可用於 Apache Kafka 的最新特性。
* 其中一個[建議的協力廠商用戶端](/docs/services/EventStreams?topic=eventstreams-kafka_clients#clients_table)。

針對兩種用戶端，我們建議一律選擇最新的用戶端版本。
{: shortdesc}

## 連接至事件串流的用戶端需求

若要連接至 {{site.data.keyword.messagehub}}，用戶端必須支援使用 SASL Plain 機制的鑑別，且使用 TLSv1.2 通訊協定的「伺服器名稱指示 (SNI)」延伸。

我們支援的最低 Kafka 通訊協定是 0.10。

	
## 協力廠商用戶端
{: #third_party_clients}

如果您無法執行官方的 Java 用戶端，我們建議執行其中一個[建議的協力廠商用戶端](/docs/services/EventStreams?topic=eventstreams-kafka_clients#clients_table)，這些全都進行過 {{site.data.keyword.messagehub}} 的詳細測試。 

支援最少用戶端需求集的其他協力廠商用戶端也可能適用於 {{site.data.keyword.messagehub}}。不過，我們只測試過建議的協力廠商用戶端並具有其經驗。

## 所有建議用戶端的支援摘要
{: #client_summary}

<table id="clients_table">
    <caption>表 2. 用戶端支援摘要</caption>
      <tr>
		    <th id="client" scope="col">用戶端</th>
		    <th id="language" scope="col">語言</th>
			<th id="version" scope="col">建議版本</th>
		    <th id="minimum version" scope="col">支援的最低版本 [<sup>1</sup>](/docs/services/EventStreams?topic=eventstreams-kafka_clients#footnote1)</th>
			<th id="sample link" scope="col">範例鏈結</th>
        </tr>
			<tr>
			<td colspan="3">**官方用戶端**</td>
			</tr>
	  		<tr>
			<td>[Apache Kafka 用戶端 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://kafka.apache.org/downloads)</td>
			<td>Java</td>
			<td>最新</td>
			<td>0.10.2<p> 如需較舊用戶端的相關資訊，請參閱[舊版相容性](/docs/services/EventStreams?topic=eventstreams-kafka_clients_classic#compatibility_classic)。</p></td>
			<td>[Java 主控台範例 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/ibm-messaging/event-streams-samples/tree/master/kafka-java-console-sample)<br/>
			[Liberty 範例 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/ibm-messaging/event-streams-samples/tree/master/kafka-java-liberty-sample)
			</td>
			</tr>
			<tr>
			<td colspan="3">**協力廠商用戶端**</td>
			</tr>
	  		<tr>
			<td>[node-rdkafka ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/Blizzard/node-rdkafka)</td>
			<td>Node.js</td>
			<td>最新</td>
			<td>2.2.2</td>
			<td>[Node.js 範例 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/ibm-messaging/event-streams-samples/tree/master/kafka-nodejs-console-sample)</td>
		</tr>
		<tr>
			<td>[confluent-kafka-python ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/confluentinc/confluent-kafka-python)</td>
			<td>Python</td>
			<td>最新</td>
			<td>0.11.0</td>
			<td>[Kafka Python 範例 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/ibm-messaging/event-streams-samples/tree/master/kafka-python-console-sample)</td>
		</tr>
		<tr>
			<td>[confluent-kafka-go ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/confluentinc/confluent-kafka-go)</td>
			<td>Golang</td>
			<td>最新</td>
			<td>0.11.0</td>
			<td></td>
		</tr>
		<tr>
			<td>[librdkafka ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/edenhill/librdkafka)</td>
			<td>C 或 C++</td>
			<td>最新</td>
			<td>0.11.0</td>
			<td></td>
		</tr>

</table>
### 註腳
1. {: #footnote1}此版本是我們已在持續測試中驗證過的最早版本。通常這是在過去 12 個月內可用的起始版本，但如果已知有重要的問題存在，可能會更新。


<!--
## Unsupported clients

The following clients are not supported by {{site.data.keyword.messagehub}}:

### kafka-node
The kafka-node client does not fully support SASL authentication with the PLAIN mechanism so cannot currently be used with {{site.data.keyword.messagehub}}.


### no-kafka 
The no-kafka client does not fully support SASL authentication with the PLAIN mechanism so cannot currently be used with {{site.data.keyword.messagehub}}.

-->

## 將用戶端連接至 {{site.data.keyword.messagehub}}
{: #connect_client}

如需如何配置 Java 用戶端以連接至 {{site.data.keyword.messagehub}} 的相關資訊，請參閱[配置用戶端](/docs/services/EventStreams?topic=eventstreams-kafka_connect)。












