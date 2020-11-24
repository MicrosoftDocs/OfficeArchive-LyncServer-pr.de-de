---
title: 'Lync Server 2013: Übersicht über Location-Based Routing für Konferenzen'
description: 'Lync Server 2013: Übersicht über Location-Based Routing für Konferenzen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a8fe9cdf4a797243c3ec04b3466011f374fb0d0
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394982"
---
# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Übersicht über Location-Based Routing für Konferenzen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-19_

Die Location-Based Routing Konferenz Anwendung bietet lync-Konferenzen einen Mechanismus zur Verhinderung der PSTN-Maut Umgehung. Die Anwendung überwacht aktive Konferenzen und erzwingt Location-Based Routing Einschränkungen basierend auf dem Standort der teilnehmenden lync-Benutzer.

Die Location-Based Routing Konferenz Anwendung bestimmt, ob Location-Based Routing für eine lync-Besprechung erzwungen werden soll, wenn die folgenden Kriterien erfüllt sind:

  - Der Besprechungsorganisator ist für Location-Based Routing aktiviert. Location-Based Routing Einschränkungen werden nur auf Konferenzen angewendet, die von Benutzern organisiert werden, die für Location-Based Routing aktiviert sind.

  - Mindestens ein Besprechungsteilnehmer befindet sich an einem Endpunkt im öffentlichen Telefonnetz (PSTN). Location-Based Routing Einschränkungen gelten nur für Konferenzen, die PSTN-Endpunkte umfassen.

  - Der Netzwerkstandort, an dem sich das PSTN-Gateway zum Überbrücken der Konferenz in das PSTN befindet, wird ebenso lokalisiert wie die Netzwerkstandorte, von denen aus die Organisatoren und Teilnehmer die Verbindung herstellen.

Die Location-Based Routing Konferenz Anwendung verhindert die Teilnahme von lync-Benutzern und PSTN-Endpunkten von verschiedenen Netzwerkstandorten an derselben Konferenz. Wenn der Organisator einer Besprechung für Location-Based Routing aktiviert ist, erzwingt die Konferenz Anwendung die folgenden Einschränkungen:

  - Die Endpunkte, die an einer lync-Besprechung teilnehmen können, hängen von den Endpunkten ab, die bereits der Konferenz beigetreten sind, und diese Einschränkung passt sich an, wenn verknüpfte Endpunkte verlassen und neue Endpunkte der Konferenz Wenn Organisatoren und Teilnehmer einer lync-Besprechung von derselben Netzwerk Website aus beitreten, kann ein PSTN-Endpunkt, ein anderer Teilnehmer desselben Netzwerkstandorts, ein anderer Teilnehmer einer anderen Netzwerk Website oder ein Teilnehmer von einer unbekannten Netzwerk Website teilnehmen.

  - Wenn Organisatoren und Teilnehmer von unterschiedlichen oder unbekannten Netzwerkstandorten aus an der Besprechung teilnehmen, darf ein Teilnehmer an einem PSTN-Endpunkt nicht an der Besprechung teilnehmen, wenn der PSTN-Anruf von einem SIP-Trunk eingeht, der für das standortbasierte Routing aktiviert ist.

  - Wenn Organisatoren und Teilnehmer an der Besprechung von der gleichen Netzwerk Website teilnehmen und Teilnehmer derselben Besprechung über das PSTN beitreten, ist ein lync-Endpunkt von einer anderen Netzwerk Website nicht berechtigt, an der Besprechung teilzunehmen.

In der folgenden Tabelle sind die Einschränkungen für Konferenz Location-Based Routing zusammengefasst.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Benutzer in einer Konferenz an einem beliebigen Standort</p></td>
<td><p>Benutzer, die an der Konferenz teilnehmen dürfen</p></td>
<td><p>Benutzer, die nicht an der Konferenz teilnehmen dürfen</p></td>
</tr>
<tr class="even">
<td><p>Lync VoIP-Clientbenutzer (s) von einer einzelnen Netzwerk Website</p></td>
<td><p>Lync-VoIP-Clientbenutzer vom gleichen Netzwerkstandort</p>
<p>Lync-VoIP-Clientbenutzer von einer anderen Netzwerk Website</p>
<p>Lync-VoIP-Clientbenutzer von einer unbekannten Netzwerk Website</p>
<p>Verbund-lync-VoIP-Clientbenutzer</p>
<p>Benutzer, die über PSTN-Endpunkt teilnehmen</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Lync VoIP-Clientbenutzer (s) von einer unbekannten Netzwerk Website</p></td>
<td><p>Lync-VoIP-Clientbenutzer von einer beliebigen Website</p>
<p>Lync-VoIP-Clientbenutzer von einer unbekannten Website</p>
<p>Verbund-lync-VoIP-Clientbenutzer</p></td>
<td><p>Benutzer, die über einen PSTN-Endpunkt teilnehmen</p></td>
</tr>
<tr class="even">
<td><p>Lync-VoIP-Clientbenutzer von verschiedenen Netzwerkstandorten aus</p></td>
<td><p>Lync-VoIP-Clientbenutzer von einer beliebigen Netzwerk Website aus</p>
<p>Lync-VoIP-Clientbenutzer von einer unbekannten Netzwerk Website</p>
<p>Verbund-lync-VoIP-Clientbenutzer</p></td>
<td><p>Benutzer, die über einen PSTN-Endpunkt teilnehmen</p></td>
</tr>
<tr class="odd">
<td><p>Lync-VoIP-Clientbenutzer von einer einzigen Netzwerk Website und Benutzern, die von einem PSTN-Endpunkt beitreten</p></td>
<td><p>Lync-VoIP-Clientbenutzer vom gleichen Netzwerkstandort</p></td>
<td><p>Lync-VoIP-Clientbenutzer von einer anderen Netzwerk Website</p>
<p>Lync-VoIP-Clientbenutzer von einer unbekannten Netzwerk Website</p>
<p>Verbund-lync-VoIP-Clientbenutzer</p></td>
</tr>
</tbody>
</table>


Im folgenden finden Sie zusätzliche Merkmale der Location-Based Routing Konferenz Anwendung:

  - Wenn ein Benutzer nicht berechtigt ist, an einer Konferenz teilzunehmen, die Location-Based Routing Einschränkungen unterliegt, wird der Benutzer, der die Konferenz anruft, abgelehnt, und sein lync-Client meldet, dass der Anruf nicht abgeschlossen oder beendet wurde.

  - Ein PSTN-Endpunkt, der an einer Konferenz mit Location-Based-Routing-Erzwingung teilnimmt, wird unabhängig von seinem Zustand nicht auf die Teilnahme an der Konferenz beschränkt, wenn der Endpunkt über einen trunk verbunden wird, der für Location-Based Routing nicht aktiviert ist.

  - Ein PBX-System, das mit einem Vermittlungs Server über einen SIP-Stamm verbunden ist, der keine Anrufe an das PSTN abruft, hat die gleichen erzwungenen wie lync-Benutzer, die sich am gleichen Netzwerkstandort befinden, an dem der SIP-Stamm definiert ist. Beispielsweise kann ein PSTN-Endpunkt an einer Konferenz mit einem PBX-Benutzer und einem lync-Benutzer teilnehmen, wenn er sich im gleichen Netzwerkstandort befindet. Andernfalls kann der PSTN-Endpunkt nicht an der Konferenz teilnehmen, wenn sich der PBX-Benutzer an einem anderen Netzwerkstandort als der lync-Benutzer befindet.

</div>

<span> </span>

</div>

</div>

</div>

