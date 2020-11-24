---
title: Konfigurieren der SCOM-Überwachung
description: Konfigurieren der SCOM-Überwachung
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c93e10c705a1a1e08972d7534e00a33c472d23a3
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394107"
---
# <a name="configure-scom-monitoring"></a>Konfigurieren der SCOM-Überwachung

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Nach der Migration zu Microsoft lync Server 2013 müssen Sie einige Aufgaben ausführen, um lync Server 2013 für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren.

  - Wenden Sie lync Server 2010-Updates auf einen Server an, der zum Verwalten der zentralen Ermittlungslogik gewählt wurde.

  - Aktualisieren Sie den Registrierungsschlüssel des zentralen Discovery Candidate-Servers.

  - Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass er den Kandidaten für die zentrale Ermittlung außer Kraft setzt.

Nachfolgend finden Sie Anweisungen zur Durchführung der einzelnen Aufgaben.

**Wenden Sie lync Server 2010-Updates auf einen Server an, der zum Verwalten der zentralen Ermittlungslogik gewählt wurde.**

1.  Wählen Sie einen Server aus, auf dem die System Center Operations Manager-Agentdateien installiert sind und als Knoten für die Kandidaten Ermittlung konfiguriert sind.

2.  Wenden Sie lync Server 2010-Updates auf diesen Server an. Lesen Sie das Thema [Anwenden von lync Server 2010-Updates](apply-lync-server-2010-updates.md).

**Aktualisieren Sie den Registrierungsschlüssel des zentralen Discovery Candidate-Servers.**

1.  Öffnen Sie auf dem Server, der zum Verwalten der zentralen Ermittlungslogik gewählt wurde, ein Windows PowerShell-Befehlsfenster.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Wenn Sie die Registrierung bearbeiten, tritt möglicherweise ein Fehler auf, dass der Befehl fehlgeschlagen ist, wenn der Registrierungsschlüssel bereits vorhanden ist. Wenn Sie dies erleben, können Sie den Fehler bedenkenlos ignorieren.

    
    </div>

**Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass er den Kandidaten für den Central Discovery Watcher-Knoten außer Kraft setzt.**

1.  Erweitern Sie auf einem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, **Management Pack-Objekte** , und wählen Sie dann **Objektermittlungen** aus.

2.  Klicken Sie auf **Bereich ändern...**

3.  Wählen Sie auf der Seite **Objekte des Bereichs Management Packs** die Option **ls Discovery Candidate** aus.

4.  Überschreiben Sie den Wert für den **effektiven ls-Ermittlungs Kandidaten** auf den Namen des Kandidaten Servers, der im vorherigen Verfahren gewählt wurde.

Um Ihre Änderungen abzuschließen, starten Sie den Integritätsdienst auf dem System Center Operations Manager-Stamm Verwaltungs Server erneut.

</div>

<span> </span>

</div>

</div>

</div>

