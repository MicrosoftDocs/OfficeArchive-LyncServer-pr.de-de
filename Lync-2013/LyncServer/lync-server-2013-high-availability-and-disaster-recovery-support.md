---
title: 'Lync Server 2013: Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung'
description: 'Lync Server 2013: Unterstützung für höhere Verfügbarkeit und Disaster Recovery.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8113c6b54cbb55e8149f8d6dd1b53ccbdc9436d
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427628"
---
# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-25_

Lync Server 2013 bietet eine höhere Verfügbarkeit durch Server Redundanz über Pooling. Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen. Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors. Details zu Serverrollen finden Sie unter [Serverrollen in lync Server 2013](lync-server-2013-server-roles.md).

Lync Server 2013 bietet auch Disaster Recovery-Maßnahmen, indem die Pool-Kopplung aktiviert wird. Wenn Sie diese Topologie bereitstellen, definieren Sie Paare von Front-End-Pools, wobei sich jeder Pool in einem Paar in einem separaten Rechenzentrum und in einem separaten geografischen Bereich befindet. Wenn ein Pool oder eine Website nicht mehr zur Verfügung steht, können Sie die Benutzer dieses Pools umleiten, um den anderen Pool des Paars mit minimaler Dienstunterbrechung zu verwenden.

Lync Server 2013 unterstützt auch die höchst Verfügbarkeit von Back-End-Servern. Hierbei handelt es sich um eine optionale Topologie, in der Sie zwei Back-End-Server für einen Front-End-Pool bereitstellen und die synchrone SQL Server-Spiegelung für alle lync-Datenbankeneinrichten, die auf den Back-End-Servern ausgeführt werden.

Details zur Pool Kopplung und zur Back-End-Server Spiegelung finden Sie unter [Planen von Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

<div>

## <a name="see-also"></a>Siehe auch


[Serverrollen in Lync Server 2013](lync-server-2013-server-roles.md)  
[Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

