---
title: 'Lync Server 2013: tblEnumValue'
description: 'Lync Server 2013: tblEnumValue.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159f90bb96c367fcb3e11725a582a9993080d3fd
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49444448"
---
# <a name="tblenumvalue-in-lync-server-2013"></a>tblEnumValue in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-28_

tblEnumValue ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltens Werte der Attribute enthält, die in der Knoten Tabelle verwendet werden.

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
<td><p>Werttyp</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>Die ID des Werts.</p></td>
</tr>
<tr class="even">
<td><p>AttributeID</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>Die ID des Attributs.</p></td>
</tr>
<tr class="odd">
<td><p>AttributeValue</p></td>
<td><p>nvarchar (256); nicht NULL</p></td>
<td><p>Der Name des Werts.</p></td>
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
<td><p>Werttyp</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>AttributeID</p></td>
<td><p>Fremdschlüssel mit Lookup in der tblEnumAttribute. AttributeCollection-Tabelle.</p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a>Tabellenwerte

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Werttyp</th>
<th>AttributeID</th>
<th>AttributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
<td><p>privat</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>1</p></td>
<td><p>Bereich</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>2</p></td>
<td><p>normal</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>2</p></td>
<td><p>Auditorium</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>1</p></td>
<td><p>Öffnen</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Siehe auch


[tblNode in Lync Server 2013](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

