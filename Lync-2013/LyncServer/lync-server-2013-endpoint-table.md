---
title: 'Lync Server 2013: Endpoint-Tabelle'
description: 'Lync Server 2013: Endpunkt Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614872eee41b5d8e56da4b96cf5bbe3a4a1cf4d2
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428678"
---
# <a name="endpoint-table-in-lync-server-2013"></a>Endpoint-Tabelle in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Die Endpunkt Tabelle ist eine unterstützende Tabelle, in der Informationen zu den Endpunkten gespeichert werden, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Endpunkt.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Spalte</strong></th>
<th><strong>Datentyp</strong></th>
<th><strong>Schlüssel/Index</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>EndpointKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Endpunkt kennzeichnet.</p></td>
</tr>
<tr class="even">
<td><p><strong>Name</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Eindeutigen</p></td>
<td><p>Endpunktname</p></td>
</tr>
<tr class="odd">
<td><p><strong>OS</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p> </p></td>
<td><p>Betriebssystem (OS) des Endpunkts.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUName</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td></td>
<td><p>Der CPU-Name des Endpunkts.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUNumberOfCores</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Die Anzahl von CPU-Kernen des Endpunkts.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUProcessorSpeed</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>CPU-Prozessorgeschwindigkeit des Endpunkts.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VirtualizationFlag</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Bit-Flag, das angibt, ob das System in einer virtualisierten Umgebung ausgeführt wird:</p>
<ul>
<li><p>0x0000 – keine</p></li>
<li><p>0x0001 – HyperV</p></li>
<li><p>0x0002 – VMware</p></li>
<li><p>0x0004 – virtueller PC</p></li>
<li><p>0x0008 – xen-PC</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

