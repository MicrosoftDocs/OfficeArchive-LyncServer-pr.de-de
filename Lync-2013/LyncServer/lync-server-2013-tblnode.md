---
title: 'Lync Server 2013: tblNode'
description: 'Lync Server 2013: tblNode.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a5d630621c32cbc54501249c7a679bf4023c60
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49423519"
---
# <a name="tblnode-in-lync-server-2013"></a>tblNode in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-12_

tblNode enthält die Objektstruktur (mit Kategorien-oder Chatroom-Knoten), wie Sie in der lync Server 2013-Systemsteuerung und den administrativen Cmdlets verwaltet werden.

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
<td><p>nodeID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Knoten-ID (eindeutige Nummer).</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID, nicht NULL</p></td>
<td><p>Knoten-GUID.</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>Knoten-ID des übergeordneten Elements. Der Stammknoten (mit ID 1) schließt sich ebenfalls als übergeordnetes Element ein.</p></td>
</tr>
<tr class="even">
<td><p>NodeType</p></td>
<td><p>Bit, nicht NULL</p></td>
<td><p>"True", wenn der Knoten eine Kategorie ist.</p>
<p>False, wenn es sich bei dem Knoten um einen Chatroom handelt.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256); nicht NULL</p></td>
<td><p>Knotenname</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256); nicht NULL</p></td>
<td><p>Knotenbeschreibung.</p></td>
</tr>
<tr class="odd">
<td><p>einladen</p></td>
<td><p>bit</p></td>
<td><p>Für Kategorien:</p>
<ul>
<li><p>True, wenn Einladungen aktiviert sind.</p></li>
<li><p>False, wenn Einladungen deaktiviert sind.</p></li>
</ul>
<p>Für Räume:</p>
<ul>
<li><p>False, wenn Einladungen deaktiviert sind (überschreibt die übergeordnete Kategorie).</p></li>
<li><p>NULL, wenn die invites-Einstellung von der übergeordneten Kategorie geerbt wird.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>angemeldet</p></td>
<td><p>bit</p></td>
<td><p>Für Kategorien:</p>
<ul>
<li><p>"True", wenn das Chat-Protokoll aktiviert ist.</p></li>
<li><p>Falsch, wenn das Chat-Protokoll deaktiviert ist.</p></li>
</ul>
<p>Für Räume:</p>
<ul>
<li><p>NULL.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>bit</p></td>
<td><p>Für Kategorien:</p>
<ul>
<li><p>"True", wenn Dateiuploads zulässig sind.</p></li>
<li><p>False, wenn Dateiuploads nicht zulässig sind.</p></li>
</ul>
<p>Für Räume:</p>
<ul>
<li><p>NULL.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>deaktiviert</p></td>
<td><p>Bit, nicht NULL</p></td>
<td><p>"True", wenn der Chatroom deaktiviert ist. Gilt nur für Chatrooms. (Falsch für Kategorien.)</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Verhalten</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>Verhalten (in der EnumValue-Tabelle nachgeschlagen):</p>
<ul>
<li><p>4: Normal (normale Chatrooms).</p></li>
<li><p>5: Auditorium (Auditorium-Chatrooms, nur Referenten können dazu beitragen).</p></li>
</ul>
<p>Gilt nur für Chatrooms.</p></td>
</tr>
<tr class="odd">
<td><p>Sichtbarkeit</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>Sichtbarkeit (in der EnumValue-Tabelle nachgeschlagen):</p>
<ul>
<li><p>2: privat</p></li>
<li><p>3: Gültigkeitsbereich</p></li>
<li><p>6: Öffnen</p></li>
</ul>
<p>Gilt nur für Chatrooms.</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>Add-In GUID, wenn diesem Chatroom ein Add-in zugeordnet ist. (Kategorien verfügen nicht über Add-Ins.)</p>
<p>Die Add-in-Informationen werden in der SiopWhiteList-Tabelle nachgeschlagen.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Die ID des Prinzipals, der diesen Knoten erstellt hat.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Zeitstempel der Knotenerstellung.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Die ID des Prinzipals, der das neueste Update dieses Knotens durchführte.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Zeitstempel der letzten Aktualisierung dieses Knotens.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt des letzten Aufräumvorgangs (Entfernen von Bereichen aus tblScopedPrincipal-Tabelle und Rollen aus der tblPrincipalRole-Tabelle), die diesen Knoten betroffen haben. Dieser wird vom internen Cache Aktualisierungsmechanismus des Chat Diensts verwendet.</p></td>
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
<td><p>nodeID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>Verhalten</p></td>
<td><p>Fremdschlüssel mit Lookup in der Tabelle "tblEnumValue. Wert".</p></td>
</tr>
<tr class="odd">
<td><p>Sichtbarkeit</p></td>
<td><p>Fremdschlüssel mit Lookup in der Tabelle "tblEnumValue. Wert".</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Fremdschlüssel mit Lookup in der tblSiopWhiteList. siopId-Tabelle.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

