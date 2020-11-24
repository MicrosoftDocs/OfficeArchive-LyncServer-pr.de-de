---
title: 'Lync Server 2013: Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken'
description: 'Lync Server 2013: Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90d1c53fb2a2dde5dde079f09b13ff4f06a659b3
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394547"
---
# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Nachdem Sie Ihre Topologie im Topologie-Generator aktualisiert haben, müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen, bevor Sie die Archivierung konfigurieren und verwenden können. Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, sodass diese Server mit der Topologie und anderen Konfigurationsänderungen synchronisiert sind.

<div>

## <a name="to-publish-your-updated-topology"></a>So veröffentlichen Sie Ihre aktualisierte Topologie

1.  Melden Sie sich auf einem Computer, auf dem lync Server 2013 ausgeführt wird oder auf dem die lync Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Gruppe "Benutzer" (oder einem Konto mit entsprechenden Benutzerrechten) ist.
    
    <div>
    

    > [!NOTE]  
    > Sie können eine Topologie mithilfe eines Kontos definieren, das ein Mitglied der lokalen Benutzergruppe ist, aber zum Veröffentlichen einer Topologie, die zum Hinzufügen eines Servers zur Topologie erforderlich ist, müssen Sie ein Konto verwenden, das ein Mitglied der Gruppe der <STRONG>Domänenadministratoren</STRONG> und der <STRONG>RTCUniversalServerAdmins</STRONG> -Gruppe ist. und dies verfügt über die Vollzugriffsberechtigung (also lesen, schreiben und ändern) für die Dateifreigabe, die Sie für den lync Server 2013-Dateispeicher verwenden (Dies bedeutet, dass der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control List) oder ein Konto mit entsprechenden rechten konfigurieren kann.

    
    </div>

2.  Öffnen Sie die im vorherigen Abschnitt erstellte Topologie mithilfe des Topologie-Generators.

3.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **Topologie veröffentlichen**.

4.  Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.

5.  Stellen Sie auf der Seite **Datenbanken erstellen** sicher, dass die Datenbank ausgewählt ist, und klicken Sie dann auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie nicht über die erforderlichen Berechtigungen zum Erstellen von Datenbanken verfügen, können Sie die Auswahl der Datenbank abbrechen, sodass ein Benutzer mit den erforderlichen Berechtigungen die Datenbankerstellung ausführen kann. Details zu den erforderlichen Administratorrechten und-Berechtigungen finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Bereitstellungsberechtigungen für SQL Server in lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Mithilfe des Topologie-Generators können nur Datenbanken auf dedizierten SQL Server-Servern installiert werden. Datenbanken auf SQL Server-Servern, die mit anderen Server Komponenten kombiniert sind, müssen durch Ausführen des lokalen Setups auf diesem Computer installiert werden.

    
    </div>

6.  Vergewissern Sie sich auf der Seite **Assistent für die Veröffentlichung abgeschlossen**, dass die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Nach Veröffentlichung der Topologie müssen Sie Optionen und Richtlinien für die Archivierung konfigurieren, bevor Inhalte archiviert werden können. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-support-for-archiving.md">Konfigurieren der Unterstützung für die Archivierung in lync Server 2013</A> in der Bereitstellungsdokumentation.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

