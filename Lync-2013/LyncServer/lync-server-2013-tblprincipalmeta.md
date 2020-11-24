---
title: 'Lync Server 2013: tblPrincipalMeta'
description: 'Lync Server 2013: tblPrincipalMeta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 899fd1e450dac52afa56c1ee1de86da82b2db309
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49393931"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a>tblPrincipalMeta in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-12_

tblPrincipalMeta enthält die Prinzipale, die aus den Active Directory-Domänendiensten aktualisiert werden müssen.

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
<td><p>prinAffiliationsDirty</p></td>
<td><p>Bit, nicht NULL</p></td>
<td><p>"True", wenn Haupt Zuordnungen aktualisiert werden müssen.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesDirty</p></td>
<td><p>Bit, nicht NULL</p></td>
<td><p>"True", wenn Prinzipal Attribute aktualisiert werden müssen.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>Bit, nicht NULL</p></td>
<td><p>"True", wenn der Prinzipal gelöscht wurde.</p></td>
</tr>
<tr class="odd">
<td><p>tryCount</p></td>
<td><p>int</p></td>
<td><p>Die Anzahl der Versuche, den Prinzipal von AD DS zu aktualisieren, die bisher geschehen sind.</p></td>
</tr>
<tr class="even">
<td><p>lastTry</p></td>
<td><p>datetime</p></td>
<td><p>Zeitstempel des letzten Versuchs, den Prinzipal zu aktualisieren. Kann NULL sein, wenn noch keine Aktualisierung versucht wurde.</p></td>
</tr>
<tr class="odd">
<td><p>nextTry</p></td>
<td><p>datetime</p></td>
<td><p>Zeitstempel für die nächste geplante Aktualisierung. Kann NULL sein, wenn keine weitere Aktualisierung geplant wurde.</p></td>
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
<td><p>prinID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

