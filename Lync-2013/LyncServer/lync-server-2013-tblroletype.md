---
title: 'Lync Server 2013: tblRoleType'
description: 'Lync Server 2013: tblRoleType.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f458259acaee7821d5f6a7339b993c70fe65f595
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49393911"
---
# <a name="tblroletype-in-lync-server-2013"></a>tblRoleType in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-25_

tblRoleType ist eine statische Nachschlagetabelle mit Rollentypen und zugehörigen Berechtigungssätzen.

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
<td><p>rtypeID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Rollentyps.</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256); nicht NULL</p></td>
<td><p>Beschreibung des Rollentyps. Es gibt vier verfügbare Rollen:</p>
<ul>
<li><p>Mitglied: Chatroom-Mitglied</p></li>
<li><p>Manager: Chat Room Manager</p></li>
<li><p>Geäußert: Referent für einen Chatroom für Auditorium</p></li>
<li><p>Creator: kann Chatrooms erstellen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Der Berechtigungssatz für die Rolle. Die verwendeten Bits sind:</p>
<ul>
<li><p>2: true, wenn die Rolle Knoten verwalten kann.</p></li>
<li><p>4: true, wenn die Rolle untergeordnete Knoten erstellen kann.</p></li>
<li><p>7: true, wenn die Rolle einem Chatroom (oder Chatrooms einer Kategorie) beitreten kann.</p></li>
<li><p>8: true, wenn die Rolle in einem Chatroom (oder in Chatrooms einer Kategorie) chatten kann.</p></li>
<li><p>10: true, wenn die Rolle das Chat-Protokoll lesen kann, selbst wenn Sie nicht zu einem Chatroom gehört.</p></li>
<li><p>11: true, wenn die Rolle den Chatroom sehen kann. (Dies wird durch Faktoren wie Bereich und Sichtbarkeit weiter verfeinert.)</p></li>
<li><p>12: true, wenn die Rolle in einem Auditorium-Chatroom chatten kann.</p></li>
<li><p>13: true, wenn die Rolle Sichtbarkeitsregeln beim Anzeigen von Knoten umgehen kann.</p></li>
</ul></td>
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
<td><p>rtypeID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

