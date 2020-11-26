---
title: 'Lync Server 2013: SIPResponseMetaData-Tabelle'
description: 'Lync Server 2013: SIPResponseMetaData-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 402cff331f81a9b46028d76de69deeaace8d5ae1
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49444623"
---
# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>SIPResponseMetaData-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Das SIPResponseMetaDataTable enthält eine Liste der SIP-Antwortcodes sowie die Klassifizierung und Definition der einzelnen Codes. Diese Codes werden als Reaktion auf Ereignisse generiert, die sich auf SIP-Geräte und SIP-Kommunikationssitzungen auswirken. So wird beispielsweise der Antwortcode 403 generiert, wenn ein SIP-Gerät eine Anforderung stellt, aber der Server lehnt die Anerkennung dieser Anforderung ab.

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
<td><p><strong>Response Code</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Numerischer Wert, der den SIP-Antwortcode darstellt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Klasse</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Allgemeine Klassifizierung für den Antwortcode. Zu den Klassifizierungen gehören:</p>
<ul>
<li><p>1 – Informations Antworten</p></li>
<li><p>2 – erfolgreiche Antworten</p></li>
<li><p>3 – Umleitungsantworten</p></li>
<li><p>4 – Antworten auf Client Fehler</p></li>
<li><p>5 – Server Fehlerantworten</p></li>
<li><p>6 – globale Fehlerantwort</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Beschreibung</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Beschreibung des SIP-Antwortcodes. Antwortcode 181 weist beispielsweise die folgende Beschreibung auf:</p>
<p>Anruf wird weitergeleitet</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

