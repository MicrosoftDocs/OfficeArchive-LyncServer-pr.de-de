---
title: 'Lync Server 2013: tblConfig'
description: 'Lync Server 2013: tblConfig.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48184515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8990e0b2c8724a5e90c36e706b92f9985f288772
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49444462"
---
# <a name="tblconfig-in-lync-server-2013"></a>tblConfig in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-12_

tblConfig enthält eine nicht unterstützte Konfiguration für beständigen Chat Server in einer Zeile.

### <a name="columns"></a>Spalten

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Typ</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>configLabel</p></td>
<td><p>nvarchar (255); nicht NULL</p></td>
<td><p>Enthält &quot; Pool.&quot;</p></td>
</tr>
<tr class="even">
<td><p>configContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Konfigurationsinhalt.</p></td>
</tr>
<tr class="odd">
<td><p>configPoolID</p></td>
<td><p>GUID, nicht NULL</p></td>
<td><p>Eindeutige ID der Datenbankinstanz.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Key

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>configLabel</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

