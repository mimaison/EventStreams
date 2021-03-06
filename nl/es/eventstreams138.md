---

copyright:
  years: 2015, 2019
lastupdated: "2018-07-05"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Utilización de la API REST de Administración en el plan Clásico
{: #admin_api_standard}

{{site.data.keyword.messagehub}} proporciona una API RESTful de administración que puede utilizar para crear, suprimir y listar temas.
{: shortdesc}

Para descubrir el punto final de la API REST de Administración, su aplicación {{site.data.keyword.Bluemix_short}} puede utilizar la
propiedad `kafka_admin_url` en la variable de entorno VCAP_SERVICES de su aplicación.

Puede descargar la especificación completa de la API desde [admin-rest-api.yaml ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/ibm-messaging/event-streams-docs/blob/master/admin-rest-api/admin-rest-api.yaml){:new_window}.
Para ver el archivo swagger, utilice las herramientas de Swagger, por ejemplo el [Editor de Swagger ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://editor.swagger.io/#/){:new_window}.

El directorio [{{site.data.keyword.messagehub}} admin-rest-api ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/ibm-messaging/event-streams-docs/tree/master/admin-rest-api){:new_window} también contiene varios ejemplos útiles de cómo llamar a la API RESTful de administración.


