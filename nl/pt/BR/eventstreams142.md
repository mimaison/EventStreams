---

copyright:
  years: 2015, 2019
lastupdated: "2018-09-11"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}



# Relatando um problema para a equipe do {{site.data.keyword.messagehub}} para o plano Clássico
{: #report_problem_classic}

Se você estiver tendo problemas com o {{site.data.keyword.messagehub}}, verifique primeiro a [página de status do {{site.data.keyword.Bluemix_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://cloud.ibm.com/status?selected=status){:new_window}. 

Se quiser ajuda da equipe do {{site.data.keyword.messagehub}}, reúna todas as informações a seguir. Quanto mais informações você puder fornecer diretamente, mais eficientemente a equipe poderá ajudar com o problema:
{:shortdesc}

1. A sua instância do {{site.data.keyword.messagehub}} está provisionada em qual localização (região) do {{site.data.keyword.Bluemix_notm}}?  Por exemplo, Dallas ou Londres. 
2. Em qual interface você está encontrando problemas? Kafka, REST, AMQP ou pontes?
3. Quando o primeiro problema ocorreu (especificamente hora, data e fuso horário)? Por quanto tempo
seu aplicativo esteve em execução antes disso?
4. O problema ainda está ocorrendo? É possível replicá-lo?
5. Qual é o ID da instância do serviço do {{site.data.keyword.messagehub}} que você está
usando? 
É possível localizar esse ID consultando o campo "instance_id" no JSON VCAP_SERVICES do serviço. Por exemplo:
 ```
 "instance_id": "e662a61b-d1ff-4cce-aab9-5eae9adb9827"
 ```
6. Que cliente Kafka ou REST seu aplicativo está usando? Quais são os detalhes da versão?
7. Quais são os detalhes de configuração do seu cliente?
8. Você possui fragmentos de log do aplicativo que exibem o problema?
9. Qual é o problema que você está vendo? Quais tópicos, IDs de cliente e IDs de grupo são afetados?
10. Que impacto o problema está causando em seu serviço?


É possível fornecer as informações reunidas para a IBM em um chamado de suporte [enviando uma solicitação
de suporte ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](/docs/get-support?topic=get-support-getting-customer-support#using-avatar){:new_window}.










