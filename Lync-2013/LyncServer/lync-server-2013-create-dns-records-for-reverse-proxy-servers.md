---
title: 'Lync Server 2013: Erstellen von DNS-Einträgen für Reverseproxyserver'
description: 'Lync Server 2013: Erstellen von DNS-Einträgen für Reverse-Proxy Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef785ebbd7160274b631a2d2b6b1f1dcc866e5fc
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431946"
---
# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>Erstellen von DNS-Einträgen für Reverseproxyserver in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-29_

Erstellen Sie externe DNS-A-Einträge, die auf die öffentliche externe Schnittstelle Ihres Microsoft Internet Security and Acceleration (ISA)-Servers 2006 SP1, Forefront Threat Management Gateway 2010 Server oder Internet Information Server-Anwendungs Anforderungs Routing verweisen, wie unter [Konfigurieren von DNS für Edge-Unterstützung in lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md)beschrieben. Sie benötigen DNS-Einträge für die FQDNs des externen Webdiensts für jeden Pool, den Director-(oder Director-Pool) und jede einfache URL.

Die Mindest-DNS-Einträge für die Clientauflösung des Reverse-Proxys müssen die folgenden Einträge erstellt werden:

  - Host (A)-Datensätze, die die veröffentlichten externen Webdienste für Directors-und Director-Pools definieren (beispielsweise **webdirext.contoso.com**)

  - Host (A)-Datensätze, die die veröffentlichten externen Webdienste für externe Webdienste definieren, die auf allen Front-End-Pools und Standard Edition-Serverrollen gehostet werden (beispielsweise **Webext.contoso.com**)

  - Host (A)-Einträge für die einfachen URLs (beispielsweise **dialin.contoso.com** und **Meet.contoso.com**)

  - Host (A)-Eintrag für den lync-Ermittlungs externen Eintrag und bietet auch einen Zeiger auf die AutoErmittlung für alle Web-Apps, einschließlich lync Web App, Scheduler und Mobilität (beispielsweise **lyncdiscover.contoso.com**).

  - Host (A)-Einträge für die Office Web Apps-Server-URL (beispielsweise **officewebapp01.contoso.com**)

Ausführliche Informationen finden Sie unter [DNS Summary – Reverse Proxy in lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

</div>

<span> </span>

</div>

</div>

</div>

