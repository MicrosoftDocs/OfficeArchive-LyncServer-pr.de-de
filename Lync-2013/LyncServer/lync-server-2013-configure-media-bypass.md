---
title: 'Lync Server 2013: Konfigurieren der Medienumgehung'
description: 'Lync Server 2013: Konfigurieren der medienumgehung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eefe960b9811f16544b7dabdd6aa07960e273806
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433906"
---
# <a name="configure-media-bypass-in-lync-server-2013"></a>Konfigurieren der Medienumgehung in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

In diesem Abschnitt wird davon ausgegangen, dass Sie bereits mindestens einen Vermittlungsserver veröffentlicht und konfiguriert haben (wie unter [Definieren eines Vermittlungsservers im Topologie-Generator in lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) und [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md)oder in [definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) und [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md), jeweils in der Bereitstellungsdokumentation

In diesem Abschnitt wird auch davon ausgegangen, dass Sie mindestens einen Gateway-Peer für die Bereitstellung von PSTN-Konnektivität definiert haben, wie unter [Definieren eines Gateways im Topologie-Generator in lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)beschrieben. Wenn es sich bei dem Peer, mit dem Sie sich verbinden, um den SBC eines SIP-Trunkinganbieters handelt, sollten Sie sich vergewissern, dass dieser ein qualifizierter Anbieter ist und die Medienumgehung unterstützt. Viele SIP-Trunkinganbieter lassen für den SBC nur den Empfang von Datenverkehr vom Vermittlungsserver zu. In diesem Fall darf die Medienumgehung für den betreffenden Trunk nicht aktiviert werden. Darüber hinaus können Sie die Medienumgehung nur aktivieren, wenn Ihre Organisation dem SIP-Trunkinganbieter ihre internen Netzwerk-IP-Adressen offenlegt.

<div>


> [!NOTE]  
> Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program – lync Server unter aufgeführt sind <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .



</div>

In diesem Abschnitt wird beschrieben, wie Sie die medienumgehung aktivieren, um die für den Vermittlungs Server erforderliche Verarbeitung zu verringern. Bevor Sie die medienumgehung aktivieren, müssen Sie sicherstellen, dass Ihre Umgebung die für die Unterstützung der medienumgehung erforderlichen Bedingungen erfüllt, wie unter [Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in der Planning-Dokumentation beschrieben ist. Stellen Sie außerdem sicher, dass Sie die Informationen unter [Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) verwendet haben, um zu entscheiden, ob die globalen Einstellungen für die medienumgehung aktiviert werden sollen, um den Vermittlungsserver immer zu umgehen oder Informationen zu Websites und Regionen zu verwenden, um zu ermitteln, ob der Vermittlungsserver umgangen werden soll.

Wenn Sie die Anrufsteuerung (Call Admission Control, CAC) – eine andere erweiterte Enterprise-VoIP-Funktion – bereits optional konfiguriert haben, beachten Sie, dass die Bandbreitenreservierung der Anrufsteuerung nicht für Anrufe gilt, für welche die Medienumgehung aktiviert ist. Bei einem Anruf wird zuerst überprüft, ob die Medienumgehung angewendet werden soll. Wenn dies der Fall ist, wird die Anrufsteuerung nicht angewendet. Nur wenn die Medienumgehung nicht aktiviert ist, wird geprüft, ob die Anrufsteuerung angewendet werden soll. Diese beiden Funktionen schließen sich für alle Anrufe, die an das PSTN weitergeleitet werden, gegenseitig aus. Dies ist ein logisches Verhalten, denn die Medienumgehung setzt voraus, dass bei einem Anruf keine Bandbreitenbeschränkungen zwischen den Medienendpunkten vorhanden sind. In Verbindungen mit eingeschränkter Bandbreite kann keine Medienumgehung stattfinden. Demzufolge trifft auf einen PSTN-Anruf nur eine der beiden folgenden Verhaltensweisen zu: a) die Medien umgehen den Vermittlungsserver und die Anrufsteuerung reserviert keine Bandbreite für den Anruf oder b) die Anrufsteuerung reserviert Bandbreite für den Anruf und die Medien werden vom betroffenen Vermittlungsserver verarbeitet.

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>Nächste Schritte: Aktivieren der medienumgehung für die trunk-Verbindung

Nachdem Sie die anfänglichen Einstellungen für PSTN-Konnektivität (Wählpläne, VoIP-Richtlinien, PSTN-Verwendungsdaten Sätze, ausgehende Anrufrouten und Übersetzungsregeln) konfiguriert haben, beginnen Sie mit der Aktivierung der medienumgehung, indem Sie die Schritte unter [Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)verwenden.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Globale Medien Umgehungs Optionen in lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

