---
title: 'Lync Server 2013: ErrorCategory-Tabelle'
description: 'Lync Server 2013: ErrorCategory-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8154c73f33b5dad62a338335a960553cfc06ec13
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428566"
---
# <a name="errorcategory-table-in-lync-server-2013"></a>ErrorCategory-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-08-20_

Die ErrorCategory-Tabelle enthält den Anzeigenamen für jede Microsoft lync Server 2013-Diagnose Klassifikation. Standardmäßig verwendet lync Server 2013 die folgenden Klassifizierungen:

  - 0--Erfolg

  - 1 – Erwarteter Fehler

  - 2 – unerwarteter Fehler

Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p><strong>CategoryID</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutiger Bezeichner für die Klassifizierung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Name</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Wert und Anzeigename, der der Klassifizierung zugewiesen ist. Gültige Werte sind:</p>
<ul>
<li><p>0--Erfolg</p></li>
<li><p>1 – Erwarteter Fehler</p></li>
<li><p>2 – unerwarteter Fehler</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

