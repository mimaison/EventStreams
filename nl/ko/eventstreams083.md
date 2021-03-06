---

copyright:
  years: 2015, 2019
lastupdated: "2018-05-30"

keywords: IBM Event Streams, Kafka as a service, managed Apache Kafka

subcollection: eventstreams

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

<!-- 15/11/18: info moved to eventstreams075.md, moved because of doc app changes -->
# 최대 한계
{: #maximum_limits}

** MQ Light API는 표준 플랜의 일부로만 사용 가능합니다.**
<br/>

{{site.data.keyword.mql}} API에 대해 다음과 같은 한계가 적용됩니다.
{:shortdesc}

* 저장될 수 있는 최대 데이터 양은 사용자의 결제 플랜에 대한 단일 Kafka 파티션과 일치합니다(일반적으로 1GB). 이 데이터 한계를 초과하는 경우, 새 메시지가 전송되면 파티션에서 가장 오래된 메시지가 제거됩니다.
* 메시지가 저장되는 최대 시간은 사용자의 결제 플랜에 대한 단일 Kafka 파티션과 일치합니다(일반적으로 24시간). 이 기간보다 더 이전의 메시지는 검색할 수 없습니다.
* 메시지의 최대 크기(헤더 제외)는 1MB입니다.
* 한 번에 연결할 수 있는 클라이언트의 최대수는 25입니다.
* 한 번에 활성 상태일 수 있는 대상의 최대수는 25입니다. 활성 대상은 다음과 같이 정의됩니다.
  - 클라이언트가 현재 연결되어 있거나 연결되지 않은 TimeToLive > 0인 대상입니다.
  - 클라이언트가 연결되는 TimeToLive = 0(기본값)인 대상입니다. 
  <p>클라이언트 간에 공유되는 대상은 하나의 대상으로 간주합니다.</p>
