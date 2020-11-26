---
title: 'Lync Server 2013: Unterstützte Clients aus vorherigen Bereitstellungen'
description: 'Lync Server 2013: Unterstützte Clients aus vorherigen Bereitstellungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported clients from previous deployments
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48184390
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f83723a571bb63cb012d6ef8a8b502af2717213
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49423652"
---
# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Unterstützte Clients aus vorherigen Bereitstellungen in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-12-14_

In einem Koexistenz-Szenario können lync Server 2013-Clients mit Clients aus früheren Versionen von lync Server und Office Communications Server interagieren. Im Gegensatz zu früheren Versionen unterstützt lync Server 2010 die neuen lync 2013-Clients. Dadurch können Organisationen, die von lync Server 2010 upgraden, neue Clients unabhängig von lync Server-Upgrades bereitstellen.

<div>

## <a name="supported-server-and-client-combinations"></a>Unterstützte Server-und Client Kombinationen

In der folgenden Tabelle sind die unterstützten Kombinationen von Clientversionen und Server Versionen aufgeführt. Lync Server 2013 unterstützt zwei vorherige Clientversionen, und lync Server 2010 unterstützt den neuen lync 2013-Client.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010-Gruppenchat</p></td>
<td><p>Nicht zutreffend</p></td>
<td><p>Supported1</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010-Teilnehmer</p></td>
<td><p>Nicht Supported2</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2-Vermittlung</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
</tr>
</tbody>
</table>


1In Microsoft lync Server 2010, die Gruppen-Chatfunktionalität war mit dem Gruppen-Chat Server, einer vertrauenswürdigen Drittanbieteranwendung für lync Server 2010, verfügbar. Lync 2013-Clients sind nicht mit lync Server 2010, Gruppen-Chat, kompatibel.

2Lync Web App 2013 bietet nun eine vollständige Besprechungs Erfahrung, einschließlich Computer Audio und-Video, und gilt als Ersatz für lync 2010 Attendee.

3Die-Anwesenheits-und Chat Features in Office Communicator 2007 R2 sind mit lync Server 2013 kompatibel, die Konferenzfeatures jedoch nicht. Während der Migration von Office Communications Server 2007 R2 eignet sich Office Communicator 2007 R2 für Anwesenheits-und Chat Interoperabilität, doch Benutzer sollten lync Web App 2013 verwenden, um an lync Server 2013-Besprechungen teilzunehmen.

<div>


> [!NOTE]  
> Details zur Möglichkeit, dass lync Server 2013-Clients mit Clients aus früheren Versionen von lync Server und Office Communications Server koexistieren und mit ihnen interagieren können, finden Sie unter <A href="lync-server-2013-client-interoperability-in-lync-2013.md">Client Interoperabilität in lync 2013</A> in der Planungsdokumentation.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

