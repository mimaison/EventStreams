---

copyright:
  years: 2015, 2019
lastupdated: "2019-05-09"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# SLA (service level agreement) per la disponibilità {{site.data.keyword.messagehub}}  
{: #sla}

## Piano Standard
Il servizio {{site.data.keyword.messagehub}} viene fornito con una disponibilità del 99.95% sul piano Standard.
Per ulteriori informazioni su SLA per l'elevata disponibilità dei servizi in {{site.data.keyword.Bluemix}}, vedi
[{{site.data.keyword.Bluemix_notm}} service description ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www-03.ibm.com/software/sla/sladb.nsf/8bd55c6b9fa8039c86256c6800578854/c4ceb9f019f9eb4c862582f9001b3994/$FILE/i126-6605-16_04-2019_en_US.pdf){:new_window}.


## Piano Enterprise
Il servizio {{site.data.keyword.messagehub}} viene fornito con una disponibilità del 99.95% sul piano Enterprise come un ambiente pubblico ad alta disponibilità.
Per ulteriori informazioni su SLA per l'elevata disponibilità dei servizi in {{site.data.keyword.Bluemix}}, vedi
[{{site.data.keyword.Bluemix_notm}} service description ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www-03.ibm.com/software/sla/sladb.nsf/8bd55c6b9fa8039c86256c6800578854/c4ceb9f019f9eb4c862582f9001b3994/$FILE/i126-6605-16_04-2019_en_US.pdf){:new_window}.

## Piano Classic
Il servizio {{site.data.keyword.messagehub}} viene fornito con una disponibilità del 99.5% sul piano Classic.
Per ulteriori informazioni su SLA per {{site.data.keyword.Bluemix}}, vedi
[{{site.data.keyword.Bluemix_notm}} service description ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www-03.ibm.com/software/sla/sladb.nsf/8bd55c6b9fa8039c86256c6800578854/c4ceb9f019f9eb4c862582f9001b3994/$FILE/i126-6605-16_04-2019_en_US.pdf){:new_window}.

<!--
## What does 99.95% availability mean?
Availability refers to the ability of applications to produce and consume messages from Kafka topics.
-->

## Come la misuriamo?
Le istanze del servizio sono monitorate continuamente per prestazioni, frequenze di errore e loro risposte alle operazioni di sintesi. Vengono registrate le interruzioni del servizio. Per ulteriori informazioni, vedi [Stato del servizio per Event Streams ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://cloud.ibm.com/status?component=messagehub&selected=status){:new_window}.

La disponibilità si riferisce alla capacità delle applicazioni di produrre ed utilizzare i messaggi dagli argomenti Kafka.

## Cosa devi prendere in considerazione per ottenere questa disponibilità?
Per ottenere alti livelli di disponibilità dalla prospettiva dell'applicazione, dovresti considerare [connettività](/docs/services/EventStreams?topic=eventstreams-sla#connectivity), [velocità effettiva](/docs/services/EventStreams?topic=eventstreams-sla#throughput) e [congruenza e durabilità dei messaggi](/docs/services/EventStreams?topic=eventstreams-sla#message_consistency). Gli utenti sono responsabili della progettazione delle loro applicazioni per ottimizzare questi tre elementi per il proprio business.

### Connettività
{: #connectivity}

A causa della natura dinamica del cloud, le applicazioni devono attendersi delle interruzioni della connessione. Un'interruzione della connessione non è considerata un malfunzionamento del servizio.

**Nuovi tentativi**<br/>
I client Kafka forniscono la logica di riconnessione, ma devi abilitare esplicitamente le riconnessioni per i produttori. Per ulteriori informazioni, vedi la [ proprietà <code>retries</code> ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://kafka.apache.org/11/documentation.html#producerconfigs){:new_window}. Le connessioni vengono rieffettuate entro 60 secondi.
 
**Duplicati**<br/>
Abilitando i nuovi tentativi potrebbero crearsi dei messaggi duplicati. A seconda di quando una connessione è stata persa, il produttore potrebbe non essere in grado di determinare se un messaggio è stato elaborato correttamente dal server e pertanto deve inviare nuovamente il messaggio quando si riconnette. Ti consigliamo di progettare le applicazioni per aspettarsi dei messaggi duplicati. 

Se non possono essere tollerati dei duplicati, puoi utilizzare la funzione del produttore <code>idempotent</code> (da Kafka 1.1) per impedire i duplicati durante i nuovi tentativi. Per ulteriori informazioni, vedi la [ proprietà <code>enable.idempotence</code> ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://kafka.apache.org/11/documentation.html#producerconfigs){:new_window}.

### Velocità effettiva
{: #throughput}

La velocità effettiva viene espressa come il numero di byte al secondo che può essere inviato e ricevuto in un cluster.

**Guida specifica per il piano Standard**<br/>
Per informazioni di orientamento sulla velocità effettiva, vedi [Limiti e quote- Standard](/docs/services/EventStreams?topic=eventstreams-kafka_quotas#kafka_quotas#standard_throughput). 

**Guida specifica per il piano Enterprise**<br/>

Per informazioni di orientamento sulla velocità effettiva, vedi [Limiti e quote - Enterprise](/docs/services/EventStreams?topic=eventstreams-kafka_quotas#enterprise_throughput). 

**Misurazione**<br/>
Ti consigliamo di strumentare le applicazioni per tenere conto di come vengono elaborate. Ad esempio, il numero di messaggi inviati e ricevuti, le dimensioni del messaggio e i codici di ritorno. Comprendere l'utilizzo di un'applicazione ti aiuta a configurare le sue risorse appropriatamente, come il tempo di conservazione per i messaggi sugli argomenti.

**Saturazione**<br/>
Quando il limite del traffico che può essere prodotto nel cluster viene raggiunto, i produttori iniziano ad essere limitati, la latenza aumenta ed infine si verificano dei malfunzionamenti come degli errori di timeout. A seconda della configurazione, anche la congruenza e la durabilità del messaggio potrebbero essere influenzate. Per ulteriori informazioni, vedi [Congruenza e durabilità dei messaggi](/docs/services/EventStreams?topic=eventstreams-sla#message_consistency).

### Congruenza e durabilità dei messaggi
{: #message_consistency}

Kafka ottiene la propria disponibilità e durabilità replicando i messaggi che riceve tra gli altri nodi del cluster, che possono poi essere utilizzati in caso di errore. {{site.data.keyword.messagehub}} utilizza tre repliche (default.replication.factor = 3), questo significa che il messaggio ricevuto da un nodo viene replicato su altri due nodi in zone di disponibilità diverse. In questo modo, la perdita di un nodo o di una zona di disponibilità può essere tollerata senza la perdita di dati o funzioni.

**Modalità <code>acks</code> del produttore**<br/>
Sebbene tutti i messaggi vengano replicati, le applicazioni possono controllare quanto solidamente i messaggi che producono vengono trasferiti al servizio utilizzando la proprietà della modalità <code>acks</code> del produttore. Questa proprietà fornisce una scelta tra velocità e rischio di perdita dei messaggi. L'impostazione predefinita è <code>acks=1</code>, il che significa che il produttore restituisce un esito positivo non appena il nodo connesso riconosce di aver ricevuto il messaggio, ma prima che sia stata completata la replica. L'impostazione consigliata e più sicura è <code>acks=all</code> in cui il produttore restituisce un esito positivo solo dopo che il messaggio è stato copiato in tutte le repliche. Questo garantisce che le repliche vengano mantenute aggiornate, evitando la perdita del messaggio se un errore causa un passaggio a una replica.


