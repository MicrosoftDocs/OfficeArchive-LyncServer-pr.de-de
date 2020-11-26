---
title: 'Lync Server 2013: Überprüfen der Normalisierung und des Routings von sprach Nummern'
description: 'Lync Server 2013: Überprüfen der Normalisierung und des Routings von sprach Nummern.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f28f679cbb991bdb90362eb61c9c7b68879791e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49438624"
---
# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a>Überprüfen der Normalisierung und des Routings von sprach Nummern in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-19_

Korrekte Zahlen Normalisierung und-Routing ist für die funktionelle Enterprise-VoIP-Umgebung sehr wichtig. Besonders bei Migrationen von der privaten Branch Exchange (PBX) zur eigenständigen lync Server-Umgebung besteht einer der Schlüssel für eine erfolgreiche Migration darin, alle vorhandenen Wählregeln anzuzeigen und zu dokumentieren und geeignete Normalisierungsregeln, VoIP-Richtlinien, Telefonverwendungen und-Routen zu erstellen.

Das Überprüfen der Normalisierung und des Routings von Zahlen ist nicht nur bei Migrationen wichtig, sondern auch im normalen, stabilen Betrieb des Systems.

Wir empfehlen, diese Überprüfung täglich mithilfe der lync Server-Systemsteuerung durchzuführen, beginnend mit der Entwicklung einer robusten Reihe von Testfällen für den aktuellen Satz von Normalisierungsregeln, die in den globalen lync Server-Einstellungen veröffentlicht wurden. Diese Testfälle sollten täglich ausgeführt werden, um alle unerwünschten Änderungen hervorzuheben, die an den Wähleinstellungen vorgenommen und zugesichert wurden.

Die lync Server-Systemsteuerung unterstützt Sie auch beim visualisieren, testen, ändern, archivieren und Freigeben von Konfigurationsinformationen zum VoIP-Routing sowie zum Ändern von Regeln für die Normalisierung von Unternehmens-und sprach Nummern, Wählpläne, VoIP-Richtlinien und Routen. Es bietet zusätzliche Funktionen für folgende Aktionen:

  - Exportieren und importieren oder Sichern von VoIP-Routingdaten zwischen Systemen.

  - Testen Sie Konfigurationsänderungen, bevor Sie Sie in ein Live System hochladen.

  - Erstellen und Ausführen von Konfigurations Testfälle, um die Nutzbarkeit von Routingdaten nach dem vornehmen von Änderungen zu gewährleisten, aber bevor Sie die Änderungen an einem bereitgestellten System durchführen.

  - Erstellen und Ändern von Nummern Normalisierungsregeln, Standortprofilen, VoIP-Richtlinien und Routingdaten, ohne die erforderlichen regulären Ausdrücke zu schreiben.

  - Analysieren eines Standortprofils zur Kompatibilität mit der lync Server Phone Edition

  - Weitere Informationen zu VoIP-Routing Tests finden Sie unter [Testen des VoIP-Routings in lync Server 2013](lync-server-2013-test-voice-routing.md)

<div>

## <a name="see-also"></a>Siehe auch


[Testen des VoIP-Routings in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

