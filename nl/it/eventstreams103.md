---

copyright:
  years: 2015, 2019
lastupdated: "2018-05-25"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

<!-- 14/11/18: info moved to eventstreams099.md, moved because of doc app changes -->
# Utilizzo del client Ruby MQ Light
{: #mql_how}

** L'API MQ Light è disponibile solo come parte del piano Standard.**
<br/>

Per utilizzare l'API, aggiungi un riferimento all'ultima API client {{site.data.keyword.mql}} disponibile per Ruby nel seguente modo:
{: shortdesc}

Aggiungi il seguente riferimento al <code>Gemfile</code>:

```
gem 'mqlight', '~> 1.0'
```
{: codeblock}

E aggiungi la seguente istruzione require al tuo file di origine:

```
require ‘mqlight’
```
{: codeblock}

<!-- Comment from Andrew
Instructions for getting started, with links for more info
Simple send source and receive source in-line

-->


