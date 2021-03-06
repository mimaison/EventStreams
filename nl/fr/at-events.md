---

copyright:
  years: 2016, 2018
lastupdated: "2019-05-14"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:table: .aria-labeledby="caption"}

<!-- Name your file `at-events.md` and include it in the Reference nav group in your toc file. -->

# Evénements {{site.data.keyword.cloudaccesstrailshort}} 
{: #at_events}

Utilisez le service {{site.data.keyword.cloudaccesstrailfull}} pour contrôler comment les utilisateurs et les applications interagissent avec le service {{site.data.keyword.messagehub}} dans les plans Standard et Enterprise dans {{site.data.keyword.Bluemix}}.
{: shortdesc}

Le service {{site.data.keyword.cloudaccesstrailfull_notm}} enregistre les activités initiées par l'utilisateur qui changent l'état d'un service dans {{site.data.keyword.Bluemix_notm}}. Pour plus d'informations, voir [{{site.data.keyword.cloudaccesstrailshort}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started){:new_window}.

<!-- You can create different sections to group events by area. -->

## Liste des événements
{: #events}

<!-- Make sure you introduce the table with a detailed description that immediately precedes it. For example, see https://console.bluemix.net/docs/services/cloud-activity-tracker/services/at_events_cf.html#catalog. -->

Sur les plans Standard et Enterprise, {{site.data.keyword.messagehub}} génère automatiquement les événements pour que vous puissiez suivre l'activité sur votre service.

| Action | Description |
|:-------|:------------|
| event-streams.topic.create | Un événement est créé lorsque vous créez un sujet|
| event-streams.topic.delete | Un événement est créé lorsque vous supprimez un sujet|
{: caption="Tableau 1. Evénements de {{site.data.keyword.messagehub}}" caption-side="top"}

## Où peut-on afficher les événements ?
{: #ui}

<!-- For example, choose one of the following two options. -->

<!-- Option 2: Add the following sentence if your service sends events to the account domain. -->

Les événements {{site.data.keyword.cloudaccesstrailshort}} sont disponibles dans le **domaine de compte** {{site.data.keyword.cloudaccesstrailshort}} de l'emplacement (la région) {{site.data.keyword.Bluemix_notm}} où les événements sont générés.










