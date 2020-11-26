---
title: 'Lync Server 2013: Wiederherstellungsdauer bei einem Failover und Failback eines Pools'
description: Lync Server 2013-Wiederherstellungszeit für Pool-Failover und Pool-Failback.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bb09c32ac4d062358a511464dc21aa7346ee034
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49436678"
---
# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Wiederherstellungsdauer bei einem Failover und Failback eines Pools in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-10_

Für Pool-Failover und Pool-Failback beträgt das Entwicklungsziel für das Wiederherstellungszeitziel (RTO) 30 Minuten. Dies ist der Zeitpunkt, zu dem ein Failover erfolgen muss, nachdem Administratoren festgestellt haben, dass ein Notfall aufgetreten ist, und die Failoververfahren initiiert haben. Es umfasst nicht die Zeit, die Administratoren zur Beurteilung der Situation und zur Entscheidungsfindung haben, und auch nicht die Zeit, die Benutzer sich nach Abschluss des Failovers erneut anmelden müssen.

Für Pool-Failover und Pool-Failback beträgt das Engineering-Ziel für das Recovery Point-Ziel (RPO) 30 Minuten. Dies definiert die Zeitspanne, in der Daten aufgrund des Notfalls und aufgrund der Replikationswartezeit des Sicherungsdienstes verloren gehen können. Wenn beispielsweise ein Pool um 10:00 Uhr herunterfällt und die RPO 30 Minuten beträgt, werden die Daten in den Pool zwischen 9:30 Uhr geschrieben. und 10:00 A. M. möglicherweise nicht in den Backup-Pool repliziert und gehen verloren.

Bei allen RTO-und RPO-Nummern in diesem Dokument wird davon ausgegangen, dass sich die beiden Rechenzentren innerhalb desselben Welt Bereichs mit hoch Geschwindigkeits Transporten mit niedriger Latenz zwischen den beiden Standorten befinden. Diese Nummern werden für einen Pool mit 40.000-aktiven Benutzern und 200.000-Benutzern für lync in Bezug auf ein vordefiniertes Benutzermodell gemessen, bei dem es bei der Datenreplikation keinen Rückstand gibt. Sie unterliegen Änderungen auf der Grundlage von Leistungstests und-Validierungen.

</div>

<span> </span>

</div>

</div>

</div>

