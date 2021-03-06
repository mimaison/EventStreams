---

copyright:
  years: 2015, 2019
lastupdated: "2018-10-29"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


# Monitoramento e criação de log no plano Clássico 
{: #monitoring_classic}

O {{site.data.keyword.messagehub}} no plano Clássico coleta automaticamente as métricas e os eventos para que seja possível monitorar seu uso do {{site.data.keyword.messagehub}}.
{:shortdesc}

**Nota:** as métricas e os eventos estão disponíveis como parte do plano Clássico do {{site.data.keyword.messagehub}} em Dallas (us-south), Londres (eu-gb) e Sydney (au-syd) apenas. 


É possível monitorar as informações de log a seguir:

<dl>
<dt>Métrica de tópico</dt>
<dd>Enviamos o número de bytes de entrada e saída para cada um de seus tópicos (um ponto de
                            verificação é obtido a cada 15 minutos). É possível acessar essas métricas
clicando no botão **Grafana** no painel do {{site.data.keyword.messagehub}}
no console do {{site.data.keyword.Bluemix_notm}}.
</dd>
<dt>Eventos do tópico</dt>
<dd>Também enviamos eventos de push toda vez que você criar ou excluir um tópico. É possível acessar esses
eventos clicando no botão **Kibana** no painel do {{site.data.keyword.messagehub}}
no console do {{site.data.keyword.Bluemix_notm}}.</dd>
</dl>


Recomendamos não editar os painéis do {{site.data.keyword.messagehub}}, já que
o {{site.data.keyword.messagehub}} faz atualizações que podem sobrescrever suas mudanças. No entanto, é possível
                incluir essas métricas e eventos em seus próprios painéis.


