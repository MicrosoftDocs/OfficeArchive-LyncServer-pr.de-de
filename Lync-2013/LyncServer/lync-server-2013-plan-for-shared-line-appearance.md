---
title: 'Lync Server 2013: Planen der Darstellung der freigegebenen Zeile'
description: 'Lync Server 2013: Planen der Darstellung der freigegebenen Zeile'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c34a4792d6df9b37b138c08881699dfcdf684d
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49443069"
---
# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>Planen der Darstellung der freigegebenen Zeile in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-03-21_

Lesen Sie dieses Thema, um zu erfahren, wie Sie in lync Server 2013, Kumulatives Update April 2016, die Darstellung der freigegebenen Leitung planen.

Die Darstellung der freigegebenen Zeile ist ein Feature in lync Server 2013, Kumulatives Update April 2016 für die Behandlung mehrerer Anrufe an eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird. SLA kann alle Enterprise-VoIP-aktivierten lync-Benutzer als freigegebene Nummer mit mehreren Zeilen konfigurieren, um auf mehrere Anrufe zu reagieren. Die Anrufe werden für die freigegebene Nummer nicht tatsächlich empfangen, sondern an Benutzer weitergeleitet, die als Stellvertretungen für die freigegebene Nummer fungieren. Jeder Delegierte kann den Anruf annehmen, während die restlichen Teilnehmer eine Benachrichtigung auf dem Telefon erhalten, wer den Anruf aufgenommen hat und welche Zeile damit ausgelastet ist. Die Anzahl der Zeilen und die Stellvertretungen können für eine freigegebene Nummer in SLA konfiguriert werden. Darüber hinaus können erweiterte Optionen wie BusyOption (was in einer Situation geschieht, wenn alle Zeilen ausgelastet sind) und MissedCallOption (der Fall, in dem keiner der Stellvertretungen einen Anruf annimmt) auch für eine freigegebene Nummer konfiguriert werden.

SLA wird nur auf den folgenden Telefongeräten unterstützt (es wird für lync-Clients auf Computern, Mobiltelefonen oder anderen Geräten nicht unterstützt):

  - Polycom VVX300 mit Firmwareupdate 5.4.1

  - Polycom VVX400 mit Firmwareupdate 5.4.1

  - Polycom VVX500 mit Firmwareupdate 5.4.1

  - Polycom VVX600 mit Firmwareupdate 5.4.1

SLA ist ein neues Feature in lync Server 2013, Kumulatives Update April 2016.

Informationen zum Bereitstellen von SLA finden Sie unter [Bereitstellen der freigegebenen Leitungsdarstellung in lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).

<div>

## <a name="feature-list"></a>Liste der Funktionen

Das Einrichten einer SLA-Gruppe macht Folgendes möglich:

  - Alle Stellvertretungen in der Gruppe können eingehende Anrufe für dieselbe gemeinsam genutzte Nummer annehmen. Diese Anrufe können Festnetz- oder SIP-Anrufe sein.

  - Stellvertretungen können Anrufe halten und annehmen.

  - Stellvertretungen können Anrufe an eine Nummer außerhalb der SLA-Gruppe weiterleiten.

  - Stellvertretungen bekommen angezeigt, wie viele Anrufe es aktuell für die gemeinsam genutzte Nummer gibt, und sie können den Status jedes einzelnen Anrufs einsehen.

  - Sie können eine maximale Anzahl gleichzeitiger Anrufe für die gemeinsam genutzte Nummer konfigurieren. Sie können auch einstellen, wie zusätzliche Anrufe behandelt werden sollen, wenn die maximale Anzahl erreicht worden ist. Zusätzliche Anrufe können mit einem Besetztzeichen abgewiesen, an eine alternative Nummer oder an Voicemail weitergeleitet werden.

  - Sie können konfigurieren, wie entgangene Anrufe (solche, die nach einer festgelegten Zeit nicht angenommen worden sind) behandelt werden sollen. Wenn Sie Voicemail für die Gruppenidentität aktivieren, gehen entgangene Anrufe automatisch an die Voicemail. Wenn Voicemail für die Gruppenidentität (gemeinsam genutzte Nummer) nicht aktiviert ist, können Sie wählen, ob entgangene Anrufe mit einem Besetztzeichen abgewiesen, an eine alternative Nummer weitergeleitet oder getrennt werden sollen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

