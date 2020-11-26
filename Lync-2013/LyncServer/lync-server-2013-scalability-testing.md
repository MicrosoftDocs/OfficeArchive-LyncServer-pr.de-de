---
title: Testen von lync Server 2013-Skalierbarkeit
description: Testen von lync Server 2013-Skalierbarkeit
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73b4ab8726de7ea068ed60fedf104b01fe91ac1b
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49442124"
---
# <a name="scalability-testing-in-lync-server-2013"></a>Skalierbarkeitstests in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Lync Server 2013 stellt die Server Infrastruktur für alle lync Server-Echtzeitkommunikationen bereit, einschließlich Instant Messaging (im) und Anwesenheits-, Konferenz-und Enterprise-VoIP. Dazu gehören alle Features, die die Hardwareressourcen eines lync Server 2013-Pools verwenden und sich daher auf Leistung und Skalierung auswirken. Alle Organisationen verwenden nicht alle Funktionen gleichermaßen.

Beispielsweise können einige Organisationen Video in Konferenzen sehr stark verwenden, während andere wenig oder gar keine Videonutzung haben könnten. Einige Organisationen bevorzugen die PowerPoint-Folien Freigabe für die Anwendungsfreigabe, während andere das Gegenteil bevorzugen. Organisationen, die Enterprise-VoIP bereitstellen, können die reaktionsgruppenanwendung möglicherweise stark verwenden oder nicht. In den meisten Organisationen werden Überwachungsserver bereitgestellt, aber nicht viele von Ihnen stellen Archivierungsserver bereit. Darüber hinaus verfügen Organisationen nicht alle über die gleichen Infrastrukturen wie Hardwarekapazitäten, Netzwerkkapazitäten und die Anzahl der Pools und die Größe der bereitgestellten Pools. Die Vielfalt der Features und Infrastrukturen stellt eine Herausforderung für Skalierbarkeitstests dar – es ist nicht möglich, alle möglichen Kombinationen von Features und Infrastrukturen zu simulieren.

Um die Unterstützung der Skalierbarkeit für lync Server zu ermitteln, führen wir Tests mit allen lync Server-Features gleichzeitig aus, basierend auf einem durchschnittlichen Nutzungsmodell (Benutzermodell). Um ein geeignetes Benutzermodell für lync Server-Arbeitslasten zu ermitteln, analysieren wir viele Datenpunkte, einschließlich Kundenbefragungen, Feedback aus dem Microsoft-Programm zur Verbesserung der Benutzerfreundlichkeit, lync Server-Nutzungsdaten aus der internen IT-Abteilung bei Microsoft sowie Daten, die von unserem Live Meeting-Dienst abgebaut werden. In vielen Fällen weist das Benutzermodell eine Neigung zu schwereren Lasten auf, um einen bequemen Seitenrand für die Verwendung innerhalb einer Organisation bereitzustellen.

In unseren Skalierbarkeitstests richten wir lync Server 2013-Pools entsprechend den empfohlenen Hardware-und Software Spezifikationen ein, einschließlich Infrastrukturkomponenten wie Active Directory-Domänendienste, Hardwarelastenausgleichs und Firewalls. Wir haben lync Server-Umgebungen so eingerichtet, dass Sie den typischen Umgebungen in der realen Welt entsprechen. Anschließend verwenden wir das Stress-und Leistungs Tool von lync Server 2013, um lync Server 2013-Lasten zu simulieren (basierend auf unserem Benutzermodell). .

Wir führen mehrere Iterationen von Skalierbarkeitstests durch, einschließlich mehrerer dreiwöchiger Test Läufe. Wir verwenden die Ergebnisse aller Tests, um bei der Leistungsoptimierung zu helfen und die Unterstützung für die Skalierbarkeits Nummern in unserem Benutzermodell zu überprüfen.

</div>

<span> </span>

</div>

</div>

</div>

