---
title: 'Lync Server 2013: Importieren der lync Server 2013-Verwaltungspakete'
description: 'Lync Server 2013: Importieren der lync Server 2013-Verwaltungspakete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9615e559baf2f1c8b99015f1e407230559ff770
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427327"
---
# <a name="importing-the-lync-server-2013-management-packs"></a>Importieren der lync Server 2013-Verwaltungspakete

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Sie können die Funktionen von System Center Operations Manager erweitern, indem Sie Management Packs installieren – Software, die festlegt, welche Elemente System Center Operations Manager überwachen kann, und wie diese Elemente überwacht werden sollen und wie Benachrichtigungen ausgelöst und gemeldet werden sollen. Lync Server 2013 umfasst zwei System Center Operations Manager-Verwaltungspakete, die die folgenden Funktionen bieten:

  - Das Komponenten-und Benutzer Verwaltungspaket (Microsoft.ls.2013.Monitoring.ComponentAndUser.MP) verfolgt lync-Server Probleme, die in Ereignisprotokollen aufgezeichnet, von Leistungsindikatoren registriert oder in den Anruf Detaildatensätzen (CDR) oder den QoE-Datenbanken (Quality of Experience) protokolliert wurden. Bei kritischen Problemen kann System Center Operations Manager so konfiguriert werden, dass Administratoren sofort per e-Mail, Sofortnachricht oder SMS-Messaging benachrichtigt werden. SMS ist die Technologie, die verwendet wird, um Textnachrichten von einem mobilen Gerät an einen anderen zu senden.)
    
    <div>
    

    > [!NOTE]  
    > Details zum Konfigurieren der Operations Manager-Benachrichtigung finden Sie unter Konfigurieren der Benachrichtigung in der TechNet-Bibliothek unter <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A> .

    
    </div>

  - Das Active Monitoring Management Pack (Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP) testet proaktiv wichtige lync Server-Komponenten wie das Anmelden beim System, den Austausch von Sofortnachrichten oder das tätigen von Anrufen an ein Telefon, das sich im öffentlichen Telefonnetz (PSTN) befindet. Diese Tests werden mithilfe der Cmdlets für synthetische lync Server-Transaktionen durchgeführt. So können Sie beispielsweise das Cmdlet **Test-CsIM** verwenden, um eine Chat Unterhaltung zwischen zwei Testbenutzern zu simulieren. Wenn diese simulierte Nachrichten Unterhaltung fehlschlägt, wird eine Benachrichtigung generiert.

Sie müssen die Management Packs importieren. Wenn Sie die Management Packs nicht importieren, können Sie Operations Manager nicht verwenden, um lync Server-Ereignisse zu überwachen oder synthetische lync Server-Transaktionen auszuführen.

Das Komponenten-und Benutzer Verwaltungspaket wird nur zum Überwachen von lync Server 2013 verwendet. Wenn Sie sich in einem Koexistenz-Szenario befinden, in dem sowohl lync Server 2013 als auch lync Server 2010 installiert sind, sollten Sie weiterhin die lync Server 2010-Verwaltungspakete für Ihre lync Server 2010-Computer verwenden.

<div>


> [!NOTE]  
> Zu den Management Packs für lync Server 2010 gehören das lync Server 2010-Überwachungs Management Pack und das lync Server 2010-Überwachungs Management Pack für Gruppenchats.



</div>

Zum Importieren der Management Packs können folgende Tools verwendet werden:

  - **System Center Operations Manager**   Mit dieser Methode verwenden Sie den Operations Manager, um die Überwachung für lync Server hinzuzufügen.

  - **Operations Manager-Shell**   Sie können die Operations Manager-Shell verwenden, um direkt zu importieren oder Probleme zu beheben, die beim Importieren von Management Packs mithilfe der System Center Operations Manager-Konsole auftreten.

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importieren der Management Packs mit System Center Operations Manager

1.  Laden Sie die Dateien Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP und Microsoft.ls.2013.Monitoring.ComponentAndUser.MP.

2.  Klicken Sie in System Center Operations Manager auf **Verwaltung**.

3.  Klicken Sie im **Verwaltungs** Bereich mit der rechten Maustaste auf **Management Packs**, und klicken Sie dann auf **Management Packs importieren**.

4.  Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Hinzufügen** und anschließend auf **Von Datenträger hinzufügen**.

5.  Klicken Sie im Dialogfeld **Online Katalogverbindung** auf **Abbrechen** , um zu verhindern, dass Operations Manager Online geht, um festzustellen, ob für die lync Server-Management Packs Abhängigkeiten vorhanden sind. Wenn Sie System Center Operations Manager 2012 verwenden, klicken Sie auf **Nein**.

6.  Suchen Sie im Dialogfeld **zu importierende Management Packs auswählen nach** den Dateien **Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP** und **Microsoft.ls.2013.Monitoring.ComponentAndUser.MP** , und klicken Sie dann auf **Öffnen**. Wenn Sie mehrere Dateien im Dialogfeld auswählen möchten, klicken Sie auf die erste Datei, halten Sie die STRG-Taste gedrückt, und klicken Sie dann auf die zweite Datei.

7.  Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Installieren**. Wenn eine Fehlermeldung angezeigt wird und bei der Installation ein Fehler auftritt, bedeutet das normalerweise, dass sich die Management Pack-Dateien in einem Ordner befinden, der durch die Windows-Benutzerkontensteuerung geschützt ist. Wenn dies der Fall ist, kopieren Sie die Dateien in einen anderen Ordner, und starten Sie den Import-und Installationsvorgang erneut.

8.  Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Schließen**. Beachten Sie, dass für den Import-und Installationsvorgang möglicherweise mehrere Minuten erforderlich sind.

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Importieren von Management Packs mithilfe der Operations Manager-Shell

Im Allgemeinen ist es einfacher, die Management Packs mithilfe von Operations Manager zu importieren. Wenn jedoch ein Fehler auftritt und der Import fehlschlägt, bietet die Konsole nicht immer angemessene Fehlerberichte. Im Vergleich dazu bietet die Operations Manager-Shell detaillierte Informationen. Wenn Sie Operations Manager verwenden und beim Importieren eines Management Packs Probleme auftreten, importieren Sie das Pack mithilfe der Operations Manager-Shell. Die Operations Manager-Shell bietet weitere Informationen, die Ihnen bei der Entscheidung helfen können, warum der Import fehlgeschlagen ist.

Wenn Sie System Center Operations Manager 2007 R2 verwenden, führen Sie die folgenden Schritte aus:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **System Center Operations Manager 2007 R2**, und klicken Sie dann auf **Operations Manager-Shell**.

2.  Geben Sie in der Operations Manager-Shell an der Eingabeaufforderung den folgenden Befehl unter Verwendung des tatsächlichen Pfads zu Ihrer Kopie der Datei Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP ein, und drücken Sie dann die EINGABETASTE:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  Nachdem Sie das erste Management Pack importiert haben, wiederholen Sie den Vorgang mit dem Pfad zu Ihrer Kopie der Datei Microsoft.ls.2013.Monitoring.ComponentAndUser.MP:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Schließen Sie die Operations Manager-Shell.

Wenn Sie System Center Operations Manager 2012 verwenden, führen Sie stattdessen dieses Verfahren aus:

1.  Klicken Sie auf **Start**, klicken Sie dann auf **Alle Programme**, anschließend auf **Microsoft System Center 2012**, dann auf **Operations Manager** und anschließend auf **Operations Manager-Shell**.

2.  Geben Sie in der Operations Manager-Shell an der Eingabeaufforderung den folgenden Befehl unter Verwendung des tatsächlichen Pfads zu Ihrer Kopie der Datei Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP ein, und drücken Sie dann die EINGABETASTE:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  Nachdem Sie das erste Management Pack importiert haben, wiederholen Sie den Vorgang mit dem Pfad zu Ihrer Kopie der Datei Microsoft.ls.2013.Monitoring.ComponentAndUser.MP:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

