---
title: 'Lync Server 2013: tblPrincipalInvites'
description: 'Lync Server 2013: tblPrincipalInvites.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30d741864ed2a3cfbec8329215be33c21b3b262
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49423505"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a>tblPrincipalInvites in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-25_

tblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer für alle Knoten, bei denen die automatische Einladung aktiviert ist.

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
<td><p>prinID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal-ID.</p></td>
</tr>
<tr class="even">
<td><p>invID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Eindeutige sequenzielle Zahl (pro Prinzipal-ID), die aus der tblLastInviteId-Tabelle generiert wurde.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Knoten-ID (nur Chatroom).</p></td>
</tr>
<tr class="even">
<td><p>createdOn</p></td>
<td><p>DateTime, nicht NULL</p></td>
<td><p>Zeitpunkt der Erstellung.</p></td>
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
<td><p>&lt;prinID, Knoten-Nr.&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

