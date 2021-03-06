---

copyright:
  years: 2015, 2019
lastupdated: "2018-06-06"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Choix entre les trois API dans le plan Classic  
{: #choose_api_classic}

Dans le plan Classic, {{site.data.keyword.messagehub}} prend en charge trois API différentes. Les informations suivantes vous aideront à choisir celle qui vous convient le mieux :
{: shortdesc}

## Pourquoi utiliser l'API Kafka ?
{: #why_kafka_classic notoc}

Plusieurs raisons peuvent justifier l'utilisation de l'API Kafka par rapport aux autres interfaces fournies par {{site.data.keyword.messagehub}}. Ces raisons sont les suivantes :
{:shortdesc}


* Il est plus facile d'intégrer votre application à des systèmes existants qui prennent en charge Kafka, par exemple {{site.data.keyword.IBM}} {{site.data.keyword.streaminganalyticsshort}} et {{site.data.keyword.sparks}}.
* Les temps d'attente sont moins longs et le débit plus élevé qu'avec les autres API.
* Elle est plus riche que l'API REST Kafka.

## Pourquoi utiliser l'API REST Kafka ?
{: #why_rest_classic notoc}

** L'API REST Kafka est uniquement disponible dans le plan Classic.**
<br/>

L'API REST Kafka est une interface pratique qui peut être utilisée dans les situations suivantes :

* Lorsqu'un développeur souhaite s'initier à {{site.data.keyword.messagehub}}
* Dans certains cas d'utilisation à faible débit pour lesquels le temps d'attente n'est pas un facteur critique
* Pour le débogage et la détection des incidents

L'API REST Kafka n'est pas conçue pour être une interface offrant un débit élevé et de faibles temps d'attente. Pour ce type de besoins, il est recommandé d'utiliser l'API Kafka pour établir une connexion vers et depuis {{site.data.keyword.messagehub}}. Pour plus d'informations, voir [Utilisation d'un client Kafka](/docs/services/EventStreams?topic=eventstreams-kafka_using#kafka_using).

## Pourquoi utiliser l'API {{site.data.keyword.mql}} ?
{: #why_mql_classic notoc}

**L'API MQ Light est uniquement disponible dans le plan Classic.**
<br/>

L'API {{site.data.keyword.mql}} propose une interface de messagerie basée sur AMQP pour Java™, Node.js, Python et Ruby. Elle permet la compatibilité avec les versions antérieures du service {{site.data.keyword.mql}}.
















