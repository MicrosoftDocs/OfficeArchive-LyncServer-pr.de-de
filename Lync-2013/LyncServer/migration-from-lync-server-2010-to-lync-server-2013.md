---
title: Migration von Lync Server 2010 zu Lync Server 2013
description: Migration von lync Server 2010 zu lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe1bc1b7745c5ddc89a7f8fb64295a82f52c9bd
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49438596"
---
# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Migration von Lync Server 2010 zu Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Die Themen in diesem Abschnitt führen Sie durch den Vorgang der Migration von lync Server 2010 zu lync Server 2013.

<div>


> [!IMPORTANT]  
> In diesem Dokument werden die Schritte beschrieben, die in der Regel für die einzelnen Migrationsphasen erforderlich sind. Sie bezieht sich nicht auf jede mögliche Legacy Bereitstellungstopologie oder alle möglichen Migrationsszenarien. Daher müssen Sie möglicherweise nicht alle beschriebenen Schritte ausführen, oder Sie müssen abhängig von Ihrer Bereitstellung möglicherweise zusätzliche Schritte ausführen. Dieses Dokument enthält auch Beispiele für Überprüfungsschritte. Diese Überprüfungsschritte werden bereitgestellt, um Ihnen zu verdeutlichen, was Sie suchen müssen, um sicherzustellen, dass jede Phase erfolgreich abgeschlossen wird, während Sie Ihre Migration fortführen. Passen Sie diese Überprüfungsschritte an den jeweiligen Migrationsprozess an.



</div>

Dieses Handbuch enthält Informationen, die speziell für das Upgrade Ihrer vorhandenen Bereitstellung gelten. Es wird nicht erläutert, wie Sie Ihre vorhandene Topologie ändern. In diesem Leitfaden wird die Implementierung neuer Features nicht behandelt. Wenn eine detaillierte Prozedur an anderer Stelle dokumentiert wird, werden Sie in diesem Leitfaden zu dem entsprechenden Dokument-oder Dokumentabschnitt weitergeleitet.

In diesem Dokument werden die in der folgenden Liste angegebenen Ausdrücke definiert.

  - *Migrations*  
    Verschieben der Produktionsbereitstellung aus einer früheren Version von lync Server 2010 auf lync Server 2013

<!-- end list -->

  - *Upgrade*  
    Installieren einer neueren Software Version auf einem Server oder Clientcomputer

<!-- end list -->

  - *Koexistenz*  
    Die temporäre Umgebung, die während der Migration vorhanden ist, wenn einige Funktionen zu lync Server 2013 migriert wurden und andere Funktionen weiterhin in einer früheren Version von lync Server 2010 verbleiben.

<!-- end list -->

  - *Interoperabilität*  
    Die Möglichkeit, dass Ihre Bereitstellung während des Zeitraums der Koexistenz erfolgreich ausgeführt werden kann.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Vorbereiten der Migration](before-you-begin-the-migration.md)

  - [Phase 1: Planen der Migration von lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Phase 2: Vorbereitung der Migration](phase-2-prepare-for-migration.md)

  - [Phase 3: Bereitstellen des lync Server 2013-pilotpools](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Phase 4: Verschieben von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Phase 5: Hinzufügen von lync Server 2013 Edge-Server zu Pilot Pool](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung](phase-6-move-from-pilot-deployment-into-production.md)

  - [Phase 7: Aufgaben nach der Migration abschließen](phase-7-complete-post-migration-tasks.md)

  - [Phase 8: Außerbetriebsetzen der Legacypools](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

