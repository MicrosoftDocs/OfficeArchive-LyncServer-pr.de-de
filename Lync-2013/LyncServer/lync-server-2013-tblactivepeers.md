---
title: 'Lync Server 2013: tblActivePeers'
description: 'Lync Server 2013: tblActivePeers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48185176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f274f82a280883e38e8e02409305982b64c18e4a
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394343"
---
# <a name="tblactivepeers-in-lync-server-2013"></a>tblActivePeers in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-29_

tblActivePeers enthält die aktuellen Peer-to-Peer-Verbindungen zwischen Chat Diensten.

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
<td><p>aplServerID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Die ID des Servers, der den Eintrag gepostet hat.</p></td>
</tr>
<tr class="even">
<td><p>aplPeerID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Die ID des Peers, mit dem der Buchungsserver verbunden ist.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Schlüssel

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
<td><p>&lt;aplServerID, aplPeerID&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>aplServerID</p></td>
<td><p>Fremdschlüssel mit Lookup in der tblServerIdentity. Server-Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p>aplPeerID</p></td>
<td><p>Fremdschlüssel mit Lookup in der tblServerIdentity. Server-Tabelle.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

