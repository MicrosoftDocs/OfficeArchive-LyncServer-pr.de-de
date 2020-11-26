---
title: 'Lync Server 2013: Konfigurieren des mobilitätsdiensts für eine höhere Leistung'
description: 'Lync Server 2013: Konfigurieren des mobilitätsdiensts für eine höhere Leistung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4732d9f6a92c383a105a6f0d7162c9b6c798de24
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432884"
---
# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Konfigurieren des mobilitätsdiensts für die Höchstleistung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-17_

<div>


> [!IMPORTANT]  
> Dieses Thema bezieht sich nur auf den lync Server 2013 Mobility Service (MCX) und gilt nicht für Unified Communications Web API (UCWA), wie Sie in den kumulativen Updates für lync Server 2013: Februar 2013 bereitgestellt werden.



</div>

Wenn Sie den Mobilitätsdienst (MCX) auf Internet Informationsdienste (IIS) 7,5 installieren, konfiguriert das Mobilitätsdienst-Installationsprogramm einige Leistungseinstellungen auf dem Front-End-Server. Es wird empfohlen, IIS 7.5 für die Mobilität zu verwenden. Diese Einstellungen wirken sich auf die maximale Anzahl gleichzeitiger Benutzeranforderungen und die maximale Anzahl von Threads aus, die für den Mobilitätsdienst zulässig sind.

Die Leistungseinstellungen lauten wie folgt:

<div>

## <a name="settings-for-mcx-on-iis-75"></a>Einstellungen für Mcx auf IIS 7.5

1.  **maxConcurrentThreadsPerCPU** ist auf null (0) gesetzt.

2.  **maxConcurrentRequestsPerCPU** ist auf null (0) gesetzt.

3.  Das ASP.NET-Prozessmodell ist auf AutoConfig (nur für IIS 7.5) gesetzt.

4.  Das Limit für die HTTP.SYS-Warteschlange ist standardmäßig auf 1.000 gesetzt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

