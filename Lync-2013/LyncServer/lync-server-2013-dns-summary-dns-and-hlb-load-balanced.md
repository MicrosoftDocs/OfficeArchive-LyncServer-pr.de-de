---
title: 'Lync Server 2013: DNS-Zusammenfassung für DNS- und Hardwarelastenausgleich'
description: 'Lync Server 2013: DNS Summary – DNS und HLB Load Balanced.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81c191d653ce4025618e135b4c69bc673f79a6d9
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437742"
---
# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>DNS-Zusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die erforderlich sind, um den Director für DNS-Lastenausgleich und Hardwarelastenausgleich zu unterstützen. Die Rolle des Directors erfordert ähnliche DNS-Einträge wie der Front-End-Server. Die Anzahl der benötigten Datensätze wird in den für das Director-Zertifikat erforderlichen Alternativen Betreff-Namen widergespiegelt. Anders als der Front-End-Server hostet der Director-Pool keine Benutzerkonten oder hostet die Mobilitätsdienste.

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a>Für den Director-Pool erforderliche DNS-Einträge mithilfe des DNS-Lastenausgleichs und des Hardware Lastenausgleichs

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ort/Typ/Port</th>
<th>FQDN/DNS-Eintrag</th>
<th>IP-Adresse/FQDN</th>
<th>Karten/Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>Director-Hosteintrag für Replikation und Server-zu-Server</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Directorpool</p></td>
<td><p>Host-Eintrag für den DNS Load Balancing Director-Pool für Server-zu-Server</p></td>
</tr>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Directorpool</p></td>
<td><p>SIP (Inbound Session Initiation Protocol) von der internen Schnittstelle des Edge-Servers</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Director Pool HLB VIP</p></td>
<td><p>Hardware Load Balanced veröffentlichte Dialin-Webdienste vom Reverse-Proxy</p></td>
</tr>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Director Pool HLB VIP</p></td>
<td><p>Hardware Load Balanced veröffentlicht Meet Web Services from Reverse Proxy</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Director Pool HLB VIP</p></td>
<td><p>Vom Reverse Proxy Web-Ticket externe Webdienste für den Director-Pool veröffentlichte und definierte Hardware Lastenausgleich</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

