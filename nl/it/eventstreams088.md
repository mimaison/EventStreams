---

copyright:
  years: 2015, 2019
lastupdated: "2018-11-08"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Collegamento ad altri servizi utilizzando i bridge sul piano Classic 
{: #bridges}

I bridge ** {{site.data.keyword.messagehub}} sono disponibili solo come parte del piano Classic.**
<br/>

Il piano {{site.data.keyword.messagehub}} Classic supporta anche i bridge a una selezione di altri sistemi. I bridge sono dei link unidirezionali tra {{site.data.keyword.messagehub}} e un altro servizio. I bridge consentono
di leggere i dati da {{site.data.keyword.messagehub}} e di scriverli in
un altro servizio o di leggere i dati da un servizio e di scriverli in {{site.data.keyword.messagehub}}. Un bridge può prendere i messaggi dall'altro sistema e pubblicarli su un argomento o consumare
i messaggi da un argomento e inviarli all'altro sistema. In questo modo, puoi utilizzare {{site.data.keyword.messagehub}} per l'integrazione con altri sistemi senza dover scrivere il codice.
{:shortdesc}

I vantaggi fondamentali dell'utilizzo dei bridge {{site.data.keyword.messagehub}} sono i seguenti:  

* Puoi definire i bridge in modo amministrativo, pertanto non hai bisogno di scrivere il codice applicativo.
* Il ciclo di vita di ogni bridge è monitorato e gestito dal servizio {{site.data.keyword.messagehub}}. Ad esempio, se un bridge rileva un errore, viene riavviato automaticamente da {{site.data.keyword.messagehub}}.
* I bridge sono integrati con la piattaforma {{site.data.keyword.Bluemix_short}}. Ad esempio, le informazioni di registrazione e di monitoraggio generate dai bridge vengono indirizzate ai dashboard Kibana e Grafana.

Potresti trovare i bridge particolarmente utili nei seguenti due scenari comuni:

* Consumo di dati da una o più origini dati in {{site.data.keyword.messagehub}}.
* Trasferimento di dati da {{site.data.keyword.messagehub}} in un altro servizio. Ad esempio, nell'archiviazione di lungo termine.

## Bridge {{site.data.keyword.messagehub}}
{: notoc}

* Forniamo i seguenti tipi di bridge: 
  - [Bridge MQ](/docs/services/EventStreams?topic=eventstreams-mq_bridge), che prende i dati dei messaggi da {{site.data.keyword.IBM}} MQ e li trasferisce in un argomento in {{site.data.keyword.messagehub}}. Abbiamo intenzione di supportare una gamma di bridge più ampia in futuro.
  - [Bridge Cloud Object Storage](/docs/services/EventStreams?topic=eventstreams-cloud_object_storage_bridge), che trasferisce i dati {{site.data.keyword.messagehub}} a un'istanza del servizio [{{site.data.keyword.IBM_notm}} Cloud Object Storage ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](docs/services/cloud-object-storage?topic=cloud-object-storage-about#about){:new_window}. 
  - Il [Bridge {{site.data.keyword.objectstorageshort}}](/docs/services/EventStreams?topic=eventstreams-object_storage_bridge) è diventato obsoleto dal primo agosto 2018. Per ulteriori informazioni, vedi l'[annuncio di funzionalità deprecata: {{site.data.keyword.objectstorageshort}} OpenStack Swift (PaaS) ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/blogs/bluemix/2018/05/end-marketing-object-storage-openstack-swift-paas/){:new_window}.
* Attualmente, i bridge sono disponibili in tutti gli ambienti {{site.data.keyword.Bluemix_notm}} pubblici. I bridge non sono disponibili in {{site.data.keyword.Bluemix_short}} dedicato.
* Puoi amministrare i bridge nei seguenti due modi:
  - Utilizzando un'[API REST ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/ibm-messaging/event-streams-docs){:new_window}, che è un'estensione dell'attuale API di amministrazione {{site.data.keyword.messagehub}}. Puoi anche trovare esempi su come utilizzare curl per gestire il ciclo di vita dei bridge all'indirizzo [message-hub-docs ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/ibm-messaging/event-streams-docs){:new_window}. Potremmo cambiare questa API REST mentre continuiamo a sviluppare i bridge. Intendiamo stabilizzare questa API.
  - Utilizzando il dashboard {{site.data.keyword.messagehub}} nella console {{site.data.keyword.Bluemix_notm}}.
* Puoi associare un massimo di due bridge di qualsiasi tipo a un'istanza del servizio {{site.data.keyword.messagehub}}. Continueremo a riesaminare questa limitazione mentre continuiamo a sviluppare i bridge.
* Non è previsto alcun costo aggiuntivo per l'utilizzo dei bridge oltre le loro operazioni di messaggistica.
* Il bridge MQ non supporta l'utilizzo di SSL/TLS per proteggere la riservatezza e l'integrità dei dati mentre vengono trasferiti tra il bridge e il gestore code MQ. Abbiamo intenzione di aggiungere il supporto per l'utilizzo di SSL / TLS al bridge. 
* Tuttavia, puoi utilizzare il servizio [{{site.data.keyword.SecureGatewayfull}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](/docs/services/SecureGateway?topic=securegateway-getting-started-with-sg#getting-started-with-sg){:new_window} per inviare i tuoi dati
attraverso un tunnel protetto tra {{site.data.keyword.Bluemix_notm}}
e un client {{site.data.keyword.SecureGateway}} che puoi installare
in loco. In questa configurazione, la comunicazione su entrambe le estremità del tunnel non è
protetta con SSL/TLS.
* Il bridge Cloud Object Storage concatena i messaggi utilizzando i caratteri di nuova riga come separatori mentre scrive i dati in Cloud Object Storage. Ciò rende questo bridge inadatto per i messaggi che contengono caratteri di nuova riga incorporati e per i dati dei messaggi binari.
* Le convenzioni di denominazione degli oggetti attualmente utilizzate dal bridge Cloud Object Storage potrebbero cambiare in futuro.

## Bridge da altri servizi in {{site.data.keyword.messagehub}}
{: notoc}

* {{site.data.keyword.iot_full}} fornisce un suo bridge [ in {{site.data.keyword.messagehub}}](/docs/services/EventStreams?topic=eventstreams-consuming_messages). Il bridge fornisce un collegamento unidirezionale in {{site.data.keyword.messagehub}} che ti consente di archiviare i dati cronologici. Connettendo {{site.data.keyword.messagehub}} a {{site.data.keyword.iot_short_notm}}, puoi utilizzare {{site.data.keyword.messagehub}} come una pipeline di eventi per consumare i tuoi eventi dispositivo da Watson IoT Platform e rendere gli eventi disponibili in tempo reale al resto della piattaforma. 


