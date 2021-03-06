---

copyright:
  years: 2015, 2019
lastupdated: "2018-06-01"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


# Pont de plateforme Watson IoT
{: #consuming_messages_watson}

{{site.data.keyword.iot_full}} fournit un pont géré qui permet de créer une liaison unidirectionnelle vers {{site.data.keyword.messagehub_full}}.
{: shortdesc}

En connectant {{site.data.keyword.messagehub}} to {{site.data.keyword.iot_short_notm}}, vous pouvez utiliser {{site.data.keyword.messagehub}} comme pipeline d'événements pour consommer vos événements de périphérique depuis la {{site.data.keyword.iot_short_notm}} et mettre les événements à disposition en temps réel pour le reste de la plateforme. 

Un schéma classique consiste à utiliser le pont {{site.data.keyword.iot_short_notm}}, {{site.data.keyword.messagehub}} et le pont Cloud Object Storage pour créer un pipeline de bout en bout, qui facilite les interactions en temps réel et sur des lots.

Pour plus d'informations sur la création de ce pont, voir [Connecting and configuring a historian connector to use {{site.data.keyword.messagehub}}  ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/support/knowledgecenter/SSQP8H/iot/platform/message_hub.html){:new_window}.






