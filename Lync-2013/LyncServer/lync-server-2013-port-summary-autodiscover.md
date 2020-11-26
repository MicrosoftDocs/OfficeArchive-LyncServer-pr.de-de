---
title: 'Lync Server 2013: Port Zusammenfassung – AutoErmittlung'
description: 'Lync Server 2013: Port Zusammenfassung – AutoErmittlung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49442817"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a>Port Zusammenfassung – AutoErmittlung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-05_

Der lync Server 2013-AutoErmittlungsdienst wird auf dem Director-und Front-End-Pool Server ausgeführt und kann, wenn er in DNS mithilfe der `lyncdiscover.<domain>` und `lyncdiscoverinternal.<domain>` Hosteinträge veröffentlicht wird, von Clients zum Auffinden von lync Server-Features verwendet werden. Damit Mobile Geräte mit lync Mobile die AutoErmittlung verwenden können, müssen Sie möglicherweise zuerst die Listen alternativer Zertifikats Subjekte auf jedem Director und Front-End-Server ändern, auf dem der AutoErmittlungsdienst ausgeführt wird. Darüber hinaus ist es möglicherweise erforderlich, die Listen Betreff alternativer Name auf Zertifikaten zu ändern, die für externe Webdienst Veröffentlichungsregeln für umgekehrte Proxys verwendet werden.

Die Entscheidung darüber, ob die Listen Betreff alternativer Namen in umgekehrten Proxys verwendet werden, basiert darauf, ob Sie den AutoErmittlungsdienst auf Port 80 oder auf Port 443 veröffentlichen:

  - **Veröffentlicht auf Port 80**   Bei mobilen Geräten sind keine Zertifikat Änderungen erforderlich, wenn die ursprüngliche Abfrage des AutoErmittlungsdiensts über Port 80 erfolgt. Dies liegt daran, dass Mobile Geräte, auf denen lync ausgeführt wird, auf den Reverse-Proxy auf Port 80 extern zugreifen und dann intern auf Port 8080 an einen Director oder Front-End-Server umgeleitet werden.

  - **Veröffentlicht auf Port 443**   Die Liste Subject Alternative Name für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, muss einen `lyncdiscover.<sipdomain>` Eintrag für jede SIP-Domäne innerhalb Ihrer Organisation enthalten.
    
    <div>
    

    > [!IMPORTANT]  
    > Für neue Installationen oder Upgrades von lync Server 2010, bei denen Sie Mobility bereitgestellt haben, haben Sie entweder Port 80 für die AutoErmittlung des mobilitätsdiensts verwendet oder Zertifikate mit dem richtigen Antragstellernamen und den alternativen Subjektnamen neu ausgestellt. Überprüfen Sie die Zertifikate auf Ihrem Director und dem Front-End-Server, um den ausgewählten Pfad zu bestätigen.

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>Firewall-Details für Reverse Proxy Server: externe Schnittstelle

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Beliebig</p></td>
<td><p>Reverse Proxy-Listener</p></td>
<td><p>Optional Umleitung zu HTTPS, wenn der Benutzer http://publishedSiteFQDN eingibt &lt; &gt; . Dies ist auch bei Verwendung von Office Web Apps für Conferencing und dem AutoErmittlungsdienst für mobile Geräte, die lync ausführen, in Situationen erforderlich, in denen die Organisation das Zertifikat des externen Webdienst-Veröffentlichungsregel nicht ändern möchte.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Reverse Proxy-Listener</p></td>
<td><p>Adressbuch Downloads, Adressbuch-Webabfrage Dienst, AutoErmittlung, Clientupdates, Besprechungsinhalte, Geräte Updates, Gruppenerweiterung, Office Web Apps für Konferenzen, Einwahlkonferenzen und Besprechungen.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>Firewall-Details für Reverse Proxy Server: interne Schnittstelle

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interne Reverse-Proxy-Schnittstelle</p></td>
<td><p>Front-End-Server, Front-End-Pool, Director, Director-Pool, Office Web Apps für Konferenzen</p></td>
<td><p>Erforderlich, wenn der AutoErmittlungsdienst für mobile Geräte mit lync in Situationen verwendet wird, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte. Datenverkehr, der an Port 80 auf der externen Schnittstelle des Reverse Proxys gesendet wird, wird von der internen Schnittstelle des Reverse-Proxys an einen Pool auf Port 8080 umgeleitet, sodass die Pool-Webdienste Sie vom internen Webverkehr unterscheiden können.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interne Reverse-Proxy-Schnittstelle</p></td>
<td><p>Front-End-Server, Front-End-Pool, Director, Director-Pool, Office Web Apps für Konferenzen</p></td>
<td><p>Datenverkehr, der an Port 443 auf der externen Schnittstelle des Reverse Proxys gesendet wird, wird von der internen Schnittstelle des Reverse-Proxys an einen Pool auf Port 4443 umgeleitet, sodass die Pool-Webdienste Sie vom internen Webverkehr unterscheiden können.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

