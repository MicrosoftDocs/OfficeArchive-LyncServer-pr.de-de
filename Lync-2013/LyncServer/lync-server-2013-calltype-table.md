---
title: 'Lync Server 2013: CallType-Tabelle'
description: 'Lync Server 2013: CallType-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallType table
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412752(v=OCS.15)
ms:contentKeyID: 48185019
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af9c40396b993893f5157b89bedff0d80d87eb0
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49435621"
---
# <a name="calltype-table-in-lync-server-2013"></a>CallType-Tabelle in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Die CallType-Tabelle ist eine statische Tabelle, in der die Liste möglicher Anruftypen gespeichert ist.


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
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar</p></td>
<td></td>
<td><p>Zulässige Werte:</p>
<ul>
<li><p>0-unbekannt</p></li>
<li><p>1 – Sofortnachrichten</p></li>
<li><p>2 – Anwendungsfreigabe</p></li>
<li><p>3-Audio</p></li>
<li><p>4 – Audio und Video</p></li>
<li><p>5 – Dateiübertragung</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

