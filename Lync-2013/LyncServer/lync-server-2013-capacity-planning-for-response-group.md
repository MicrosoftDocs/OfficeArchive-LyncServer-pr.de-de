---
title: 'Lync Server 2013: Kapazitätsplanung für Reaktionsgruppen'
description: 'Lync Server 2013: Kapazitätsplanung für Reaktionsgruppe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78c543f558f67deaaeb781b308aa5f68d39cd785
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49435530"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>Kapazitätsplanung für Reaktionsgruppen in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

<div id="sectionSection0" class="section">

In der folgenden Tabelle wird das Benutzermodell der Reaktionsgruppe beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.

<div>


> [!NOTE]  
> Bei den Zahlen in der folgenden Tabelle wird davon ausgegangen, dass Sie 16-kHz-, Mono-, 16-Bit-WAV-Dateien für alle Audiodateien für Reaktionsgruppen verwenden. Wenn Sie andere Dateiformate, z. B. Windows Media Audio (WMA), einsetzen, können die Zahlen abweichen.



</div>

<div>


> [!IMPORTANT]  
> Bedenken Sie bei der Kapazitätsplanung für die Notfallwiederherstellung, dass jeder Pool eines Poolpaars in der Lage sein sollte, die Arbeitslasten für alle Reaktionsgruppen in beiden Pools zu verarbeiten.



</div>

### <a name="response-group-user-model"></a>Benutzermodell für Reaktionsgruppen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metrik</th>
<th>Pro Enterprise Edition-Pool (mit 8 Front-End-Servern)</th>
<th>Pro Standard Edition-Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Eingehende Anrufe pro Sekunde</p></td>
<td><p>16</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Gleichzeitige mit interaktiver Sprachantwort (IVR) oder Wartemusik (MoH) verbundene Anrufe</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Gleichzeitige anonyme Sitzungen (ohne Chat)</p></td>
<td><p>224</p></td>
<td><p>28</p></td>
</tr>
<tr class="even">
<td><p>Gleichzeitige anonyme Sitzungen (mit Chat)</p></td>
<td><p>64</p></td>
<td><p>8</p></td>
</tr>
<tr class="odd">
<td><p>Aktive Agents (formell und informell)</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der Sammelanschlüsse</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl der IVR-Gruppen (Verwendung der Spracherkennung)</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

