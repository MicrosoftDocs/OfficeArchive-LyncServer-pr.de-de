---
title: 'Lync Server 2013: Liste der CDR-Ansichten'
description: 'Lync Server 2013: Liste der CDR-Ansichten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f1c29560851c0e4466dbf4316bf0b1335906d4e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49426592"
---
# <a name="list-of-cdr-views-in-lync-server-2013"></a>Liste der CDR-Ansichten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Ansichten bieten eine einfache Möglichkeit, auf Informationen zu den am häufigsten verwendeten Szenarien zuzugreifen, die für die Rückgabe von Daten aus der CDR-Datenbank verwendet werden. Es wird empfohlen, Ansichten zum Erstellen benutzerdefinierter Berichte zu verwenden, anstatt die eigentlichen CdR-Datenbanktabellen zu verwenden. Das liegt daran, dass die Datenbankansichten eher die Abwärtskompatibilität mit zukünftigen Versionen von lync Server aufrecht erhalten.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ansichts Name</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-view.md">ClientVersions-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu den Client Software/-Geräten zurück, die in einer Kommunikationssitzung verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen über die Anzahl der Nachrichten zurück, die von Benutzern in einer Konferenz gesendet wurden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Konferenz Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Konferenz Informationen zurück, einschließlich Startzeit, Endzeit und Konferenzorganisator.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Sitzungsdetails für alle Konferenzsitzungen zurück, einschließlich Start-und Endzeit, Benutzer-IDs, Antwortcodes und Diagnose-IDs.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Konferenz-URIs zurück, die in einer Konferenz verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">ErrorReport-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Fehlern zurück, die während einer Sitzung aufgetreten sind.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Dateiübertragungen (Ansicht) in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Dateiübertragungssitzungen zurück, einschließlich des Datei namens und der Frage, ob die Übertragung angenommen, abgelehnt oder abgebrochen wurde.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Teilnahme-und Abwesenheits Aktivitäten für Konferenzen zurück.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt kombinierte Informationen zu Teilnahme-und Abwesenheits Aktivitäten für Konferenzen zurück (jeder Konferenz Beitritt wird mit dem entsprechenden Konferenz Urlaub gekoppelt).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">MCU-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Konferenzservern zurück.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Medienansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu den Medientypen zurück, die in Peer-to-Peer-Kommunikationssitzungen verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">ProgressReport-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu abgeschlossenen Sitzungen zurück.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Registrierungs Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Registrierungen mit lync Server zurück.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">SessionDetails-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Peer-to-Peer-Sitzungen zurück, darunter VoIP-VoIP Telefonanrufe, zweier-Chatsitzungen oder andere Peer-to-Peer-Kommunikationssitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Benutzeransicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu den Benutzern zurück, die an Kommunikationssitzungen teilgenommen haben.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">VoIPDetails-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Peer-to-Peer-Sitzungen zurück, die mindestens einen VoIP-Benutzer (Voice over IO) umfassen.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

