---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-15"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Usando o cliente Kafka Java
{: #kafka_java_using}

<!-- 21/06/18 - removing until some content ready

## To do: instructions for getting started, with links for more information


## To do: simple send source and receive source in-line


## How to use, download, and run the Java Kafka API sample

-->

A amostra da API Java&trade; Kafka é um exemplo de produtor e consumidor que são gravados em Java, que usa a API do Kafka diretamente. É possível executar esta amostra localmente ou no {{site.data.keyword.Bluemix_short}}.
{: shortdesc}

O código de amostra está no [projeto do GitHub event-streams-samples ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/ibm-messaging/event-streams-samples/tree/master/kafka-java-console-sample){:new_window}. Embora os usuários de amostra usem a API do Kafka para enviar e receber mensagens, a amostra usa a API de administração do
{{site.data.keyword.messagehub}} para criar o tópico que ela envia mensagens para e recebe
mensagens de.

Para obter informações adicionais sobre a instalação e execução da amostra, consulte [README.md ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/ibm-messaging/event-streams-samples/tree/master/kafka-java-console-sample){:new_window}.

Para obter uma apresentação detalhada de como executar a amostra, consulte [Introdução ao {{site.data.keyword.messagehub}}](/docs/services/EventStreams?topic=eventstreams-getting_started#getting_started_steps).

## Como usar, fazer download e executar a amostra do Liberty para Java
{: #liberty_sample notoc}

A amostra do Liberty for Java implementa um aplicativo simples que é implementado no tempo de execução do Liberty. O aplicativo usa a API do Kafka para o {{site.data.keyword.messagehub}} produzir e consumir mensagens.
O aplicativo também serve um frontend da web que você pode usar para administração.

É possível localizar o código de amostra no [projeto do GitHub event-streams-samples ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/ibm-messaging/event-streams-samples/tree/master/kafka-java-liberty-sample){:new_window}.

<!--
17/10/17 - Karen: following info duplicated at messagehub063 
-->

## Usando a propriedade sasl.jaas.config
{: #sasl_prop notoc}
Se estiver usando um cliente Kafka em 0.10.2.1 ou mais recente, será possível usar a
propriedade <code>sasl.jaas.config</code> para a configuração do cliente em vez de um arquivo do
JAAS. Para conectar-se ao {{site.data.keyword.messagehub}}, configure <code>sasl.jaas.config</code>
como segue:
<pre>
<code>    sasl.jaas.config=org.apache.kafka.common.security.plain.PlainLoginModule required \
    username="USERNAME" \
    password="PASSWORD";</code>
</pre>
{:codeblock}

em que USERNAME e PASSWORD são os valores do {{site.data.keyword.messagehub}} na guia
**Credenciais de serviço** no {{site.data.keyword.Bluemix_notm}}.

Se usar <code>sasl.jaas.config</code>, os clientes em execução na mesma JVM poderão usar credenciais
diferentes. Para obter mais informações, consulte
[Configurando clientes Kafka ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://kafka.apache.org/documentation/#security_sasl_plain_clientconfig){:new_window}.

Para um cliente Kafka anterior, deve-se usar um arquivo de configuração do JAAS para especificar as credenciais. Esse mecanismo é menos conveniente, portanto, recomendamos o uso da propriedade <code>sasl.jaas.config</code> como alternativa.

<!--
23/04/18 - Karen: following migration info on production in messagehub084 
-->

## Migrando um cliente Kafka da 0.9.X ou da 0.10.X para versões do cliente mais recentes
{: #kafka_migrate}


Se você estiver usando os clientes Java, será possível usar os clientes Kafka publicamente disponíveis na 0.10 ou
mais recente. 

É altamente recomendado mudar da 0.9.X para a versão mais recente. É possível fazer download de um cliente Kafka em
[https://kafka.apache.org/downloads
![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://kafka.apache.org/downloads){:new_window}.

<!--
For information about the implications of using a 0.9.X client, see 
[Backward compatibility](/docs/services/EventStreams?topic=eventstreams-kafka_clients#compatibility).
-->



### Migrando um cliente Kafka para a 0.10.2.X ou versões mais recentes

A partir da 0.10.2, é possível configurar a autenticação SASL diretamente nas propriedades do cliente em vez de usar um
arquivo JAAS. Essa simplificação permite executar múltiplos clientes na mesma JVM usando diferentes conjuntos de credenciais, o que
não é possível com um arquivo JAAS.

Execute as seguintes etapas:

1. Exclua o arquivo JAAS. Observe que a propriedade JVM java.security.auth.login.config=<PATH TO JAAS> também não é
mais necessária.
2. Inclua o seguinte nas propriedades do cliente:
    ```
	sasl.mechanism=PLAIN
    sasl.jaas.config=org.apache.kafka.common.security.plain.PlainLoginModule required username="USERNAME" password="PASSWORD";
	```

	em que USERNAME e PASSWORD são os valores do {{site.data.keyword.messagehub}} na guia
**Credenciais de serviço** no {{site.data.keyword.Bluemix_notm}}.



