---
title: Migrationsvorgang
description: Migrationsprozess.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f363bd79a3d3be709d731d2ca4bffb4f83fe89ea
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394655"
---
# <a name="migration-process"></a>Migrationsvorgang

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Das empfohlene und unterstützte Migrationsverfahren für lync Server 2013 ist eine parallele Migration. In diesem Thema wird beschrieben, warum Sie die parallele Migration verwenden sollten, und Sie enthält auch Informationen zum Testen der Koexistenz.

<div>

## <a name="side-by-side-migration"></a>Parallele Migration

In fast jeder Migration sollten Sie den parallelen Migrationspfad verwenden. Bei einer parallelen Migration stellen Sie einen neuen Server mit lync Server 2013 zusammen mit einem entsprechenden Server bereit, auf dem lync Server 2010 ausgeführt wird, und übertragen dann Vorgänge auf den neuen Server. Wenn ein Rollback zu lync Server 2010 erforderlich ist, müssen Sie die Vorgänge nur zurück zu den ursprünglichen Servern verschieben. Beachten Sie, dass in dieser Situation alle neuen Besprechungen, die mit aktualisierten Clients geplant sind, nicht funktionieren, und die Clients müssten ebenfalls heruntergestuft werden.

</div>

<div>

## <a name="coexistence-testing"></a>Koexistenz testen

Nachdem Sie lync Server 2013 parallel mit lync Server 2010 bereitgestellt haben, stellt die Bereitstellung einen Teststatus für die Koexistenz von lync Server 2013 und lync Server 2010 dar. In diesem Zustand ist es wichtig, zu testen und sicherzustellen, dass Dienste gestartet werden, jeder Standort verwaltet werden kann und Clients mit aktuellen und älteren Benutzern kommunizieren können. Vor der Migration aller Benutzer ist es sehr wichtig, dass Sie den Zustand jeder Bereitstellung verstehen und sicherstellen, dass jede Bereitstellung funktionsfähig ist und ordnungsgemäß funktioniert. In der Regel ist die Koexistenz Testphase während des Pilottests von lync Server 2013 vorhanden. Ältere Benutzer werden für einen bestimmten Zeitraum nach lync Server 2013 verschoben, um sicherzustellen, dass die Anwendungskompatibilität und die Features und Funktionen ordnungsgemäß funktionieren. Nach Pilottests werden Benutzer und Anwendungen in die Produktionsversion von lync Server 2013 verschoben, und die Legacy Pools und-Anwendungen von lync Server 2010 werden eingestellt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

