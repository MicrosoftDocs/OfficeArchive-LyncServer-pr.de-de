---
title: 'Lync Server 2013: Tenants-Tabelle'
description: 'Lync Server 2013: Tabelle "Mandanten"'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96025dfd9fb42a6083f7f3daca98e243f01a8516
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49441284"
---
# <a name="tenants-table-in-lync-server-2013"></a>Tenants-Tabelle in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Die Tabelle Mandanten ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Mandanten gespeichert ist. Jeder Datensatz in der Tabelle steht für einen Mandanten.

<div>


> [!NOTE]  
> In der lokalen Bereitstellung verwendet CdR die integrierte Mandanten-ID, um einen anderen Authentifizierungstyp anzugeben, beispielsweise öffentliche im-Konnektivität, Federated und Anonymous.



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Schlüssel/Index</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Mandanten</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Nummer, die diese Mandanten-ID kennzeichnet.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Zulässige Werte:</p>
<ul>
<li><p>00000000-0000-0000-0000-000000000000 – Enterprise</p></li>
<li><p>00000000-0000-0000-0000-000000000001 – Federated</p></li>
<li><p>00000000-0000-0000-0000-000000000002 – anonym</p></li>
<li><p>00000000-0000-0000-0000-000000000003 – Konnektivität für öffentliche Chats</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

