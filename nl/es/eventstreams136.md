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

# Elección entre las tres API en el plan Clásico 
{: #choose_api_classic}

{{site.data.keyword.messagehub}} da soporte a tres API en el plan Clásico. A continuación, encontrará información para ayudarle a decidir qué opción es la más adecuada:
{: shortdesc}

## ¿Por qué utilizar la API Kafka?
{: #why_kafka_classic notoc}

Existen diversas razones por las que puede elegir la API Kafka en vez de elegir otras interfaces proporcionadas
por
{{site.data.keyword.messagehub}}. Estas razones son:
{:shortdesc}


* Es más fácil integrar su app con sistemas existentes que admiten Kafka, por ejemplo {{site.data.keyword.IBM}} {{site.data.keyword.streaminganalyticsshort}} y {{site.data.keyword.sparks}}.
* Ofrece una latencia inferior y un rendimiento mayor que las demás API.
* Ofrece una API más rica que la API REST de Kafka.

## ¿Por qué utilizar la API REST de Kafka?
{: #why_rest_classic notoc}

**La API REST de Kafka solo está disponible como parte del plan Clásico.**
<br/>

La API REST de Kafka es una interfaz conveniente que puede ser utilizada en las siguientes situaciones:  

* Cuando un desarrollador quiera empezar a utilizar {{site.data.keyword.messagehub}}
* En algunos casos de uso de bajo rendimiento donde la latencia no sea un factor importante
* Para depurar y encontrar errores

La API REST de Kafka no está pensada como una interfaz de rendimiento elevado y latencia baja. ​Para estos tipos de requisitos, recomendamos el uso de la API de Kafka para conectarse a y desde {{site.data.keyword.messagehub}}. Para obtener más información, consulte [Uso de un cliente Kafka](/docs/services/EventStreams?topic=eventstreams-kafka_using#kafka_using).

## ¿Por qué utilizar la API {{site.data.keyword.mql}} ?
{: #why_mql_classic notoc}

**La API MQ Light solo está disponible como parte del plan Clásico.**
<br/>

La API {{site.data.keyword.mql}} proporciona una interfaz de mensajería basada en AMQP para Java™, Node.js, Python y Ruby. La API se proporciona por motivos de compatibilidad con versiones anteriores del servicio {{site.data.keyword.mql}}.
















