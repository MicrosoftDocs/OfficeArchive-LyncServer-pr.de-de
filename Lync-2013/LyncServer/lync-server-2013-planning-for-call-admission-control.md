---
title: 'Lync Server 2013: Planen des Anrufsteuerungsdiensts'
description: 'Lync Server 2013: Planen der Anrufsteuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afbc3ca411fcf0a3a1c869a23cddccdb87f09ed6
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437042"
---
# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Planen des Anrufsteuerungsdiensts in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Für UC-Anwendungen (Unified Communications), die IP-basiert sind, wie Telefonie, Video und Anwendungsfreigabe, wird die verfügbare Bandbreite von Unternehmensnetzwerken im Allgemeinen nicht als limitierender Faktor in LAN-Umgebungen angesehen. Wenn Standorte jedoch über ein WAN verbunden sind, kann die Bandbreite eingeschränkt sein. Wenn ein Zustrom von Netzwerkdatenverkehr eine WAN-Verbindung überzeichnet, werden aktuelle Mechanismen wie Warteschlangen, Pufferung und Paket Abwurf verwendet, um die Überlastung zu beheben. Der zusätzliche Datenverkehr wird üblicherweise verzögert, bis die Überlastung aufgehoben ist, oder gegebenenfalls verworfen. Bei herkömmlichem Datenverkehr kann der Empfängerclient die Daten in solchen Situationen wiederherstellen. Für echtzeitdatenverkehr wie Unified Communications kann die Netzwerküberlastung auf diese Weise nicht aufgelöst werden, da der Unified Communications-Datenverkehr sowohl auf Latenz als auch auf Paketverluste reagiert. Eine Überlastung des WAN kann zu einer unzureichenden Erlebnisqualität für Benutzer führen. Für Echtzeitverkehr in überlasteten Situationen ist es besser, Anrufe zu verweigern, als Verbindungen mit schlechter Qualität bereitzustellen.

Die Anrufsteuerung (Call Admission Control, CAC) ermittelt, ob ausreichend Netzwerkbandbreite für eine Echtzeitsitzung in akzeptabler Qualität vorhanden ist. In lync Server 2013 steuert CAC den Echtzeitverkehr nur für Audio und Video, hat aber keinen Einfluss auf den Datenverkehr. Wenn der WAN-Standardpfad nicht die erforderliche Bandbreite aufweist, kann die Anrufsteuerung versuchen, den Anruf über einen Internetpfad oder das Festnetz zu leiten. CAC steht nur in lync Server zur Verfügung.

In diesem Abschnitt wird die Funktionsweise der Anrufsteuerung beschrieben und es wird erläutert, wie die Anrufsteuerung geplant werden kann.

<div>


> [!NOTE]  
> Lync Server verfügt über drei erweiterte Enterprise-VoIP-Features: Anrufannahme Steuerung (CAC), Notfalldienste (E9-1-1) und medienumgehung. Eine Übersicht über die Planungsinformationen, die für alle drei Features üblich sind, finden Sie unter <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Übersicht über die Anrufsteuerung in lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Definieren der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Beispiel: Erfassen Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Komponenten und Topologien für die Anrufsteuerung in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Bewährte Methoden für die Anrufsteuerung in Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Prüfliste für die Bereitstellung der Anrufsteuerung in Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

