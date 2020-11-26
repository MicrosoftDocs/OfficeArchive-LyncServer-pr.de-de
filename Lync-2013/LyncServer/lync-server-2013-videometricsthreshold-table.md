---
title: 'Lync Server 2013: VideoMetricsThreshold-Tabelle'
description: 'Lync Server 2013: VideoMetricsThreshold-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93cdd6fb4c3c54ac1470499490f36fee87ba283d
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49438869"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a>VideoMetricsThreshold-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Die VideoMetricsThreshold-Tabelle enthält die optimalen und akzeptablen Werte für die Qualität der bei Videoanrufen verwendeten Metriken für die Erfahrung.


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
<td><p><strong>CallType</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Der Typ des Anrufs, der getätigt wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLROptimal</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Der Standardwert ist 0,05.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPostFECPLRAcceptable</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Der Standardwert ist 0,10.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Der Standardwert ist 5,0.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Der Standardwert ist 10,0.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverageOptimal</strong></p></td>
<td><p>Dezimal (9; 4)</p></td>
<td></td>
<td><p>Der Standardwert ist 12,0000.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvFramerateAverageAcceptable</strong></p></td>
<td><p>Dezimal (9; 4)</p></td>
<td></td>
<td><p>Der Standardwert ist 7,0000.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercentOptimal</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Der Standardwert ist 5,0.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowFrameRateCallPercentAcceptable</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Der Standardwert ist 10.0/</p></td>
</tr>
<tr class="even">
<td><p><strong>LowResolutionCallPercentOptimal</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Der Standardwert ist 5,0.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercentAcceptable</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Der Standardwert ist 10,0.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRateOptimal</strong></p></td>
<td><p>foat</p></td>
<td></td>
<td><p>Der Standardwert ist 0,05.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPacketLossRateAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Der Standardwert ist 0,10.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFrameRateAvgOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Der Standardwert ist 12.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameRateAvgAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Der Standardwert ist 7.</p></td>
</tr>
<tr class="even">
<td><p><strong>DynamicCapabilityPercentOptimal</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Der Standardwert ist 5,00.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercentAcceptable</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Der Standardwert ist 10,00.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

