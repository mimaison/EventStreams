---

copyright:
  years: 2015, 2019
lastupdated: "2018-05-25"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Come effettuare la connessione e l'autenticazione
{: #rest_connect_authenticate}

<!-- info moved to eventstreams025.md because of doc app changes -->
** L'API REST Kafka è disponibile solo come parte del piano Standard.**
<br/>

Per stabilire una connessione a {{site.data.keyword.messagehub}}, l'API REST Kafka utilizza le credenziali <code>api_key</code> e <code>kafka_rest_url</code>
dalla [variabile di ambiente VCAP_SERVICES](/docs/services/EventStreams?topic=eventstreams-connecting).
{: shortdesc}

Per eseguire l'autenticazione con l'API REST Kafka {{site.data.keyword.messagehub}}, devi specificare <code>api_key</code> nell'intestazione X-Auth-Token delle tue richieste.
