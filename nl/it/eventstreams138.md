---

copyright:
  years: 2015, 2019
lastupdated: "2018-07-05"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Utilizzo dell'API REST di amministrazione sul piano Classic
{: #admin_api_standard}

{{site.data.keyword.messagehub}} fornisce
un'API RESTful di amministrazione che puoi usare per creare, eliminare ed elencare argomenti.
{: shortdesc}

Per rilevare l'endpoint dell'API RESTful di amministrazione, la tua applicazione {{site.data.keyword.Bluemix_short}} può utilizzare la proprietà `kafka_admin_url` nella variabile di ambiente VCAP_SERVICES della tua applicazione.

Puoi scaricare la specifica completa per l'API da [admin-rest-api.yaml ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/ibm-messaging/event-streams-docs/blob/master/admin-rest-api/admin-rest-api.yaml){:new_window}.
Per visualizzare il file swagger, utilizzare gli strumenti Swagger, ad esempio l'[editor Swagger ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://editor.swagger.io/#/){:new_window}.

La directory [{{site.data.keyword.messagehub}} admin-rest-api ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/ibm-messaging/event-streams-docs/tree/master/admin-rest-api){:new_window} contiene anche un insieme di esempi utili su come puoi richiamare l'API RESTful di amministrazione.


