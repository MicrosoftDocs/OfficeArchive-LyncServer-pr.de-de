---
title: 'Lync Server 2013: Zuordnen eines überwachungsspeichers zu einem Front-End-Pool'
description: 'Lync Server 2013: Zuordnen eines überwachungsspeichers zu einem Front-End-Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81192272e487b145eb7514ee0d4be0070bd903a4
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49438273"
---
# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a>Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-04-22_

In Microsoft lync Server 2013 können Überwachungsdaten nur in Front-End-Pools gesammelt werden, die einem Überwachungsspeicher zugeordnet wurden, eine Aufgabe, die in der Regel durchgeführt wird, definieren Sie einen Front-End-Pool im Topologie-Generator. Wenn Sie einen Überwachungsspeicher einem neuen Front-End-Pool zuordnen möchten, stellen Sie sicher, dass Sie auf der Seite **"Features auswählen** " des Assistenten zum Definieren eines neuen Front-End-Pools die Option **Überwachung (Anrufdetailaufzeichnung und Protokollierung der Kriterien für die Qualität der Erfahrung)** auswählen. Beachten Sie, dass Sie, wenn Sie diese Option auswählen, auch einen SQL Store angeben müssen, um den Assistenten abzuschließen. dieser Store muss jedoch zum Zeitpunkt der Ausführung des Assistenten nicht vorhanden sein. Das bedeutet, dass Sie zunächst einen Pool mit einem Überwachungsspeicher verknüpfen und diesen dann später einrichten und konfigurieren können.

Alternativ können Sie einem vorhandenen Front-End-Pool anhand des folgenden Verfahrens einen neuen oder anderen Überwachungsspeicher zuordnen:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus vorhandener Bereitstellung herunterladen** aus und klicken Sie dann auf **OK**.

3.  Geben Sie im Dialogfeld **Speichern unter** einen Dateinamen für Ihre aktuelle Topologie ein und klicken Sie dann auf **Speichern**. Die gespeicherte Topologie kann später abgerufen und erneut veröffentlicht werden, falls es Probleme mit der neuen Topologie gibt.

4.  Erweitern Sie im Topologie-Generator **lync Server 2013**, erweitern Sie den Namen der Website, die den Front-End-Pool enthält, und klicken Sie dann auf **Enterprise Edition-Front-End-Pools** erweitern.

5.  Klicken Sie mit der rechten Maustaste auf den Namen des Pools, dem der Überwachungsspeicher zugeordnet werden soll und klicken Sie dann auf **Eigenschaften bearbeiten**.

6.  Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Option **Überwachung (CDR- und QoE-Metriken)** aus und wählen Sie dann in der Dropdownliste **SQL Server-Speicher für Überwachung** eine vorhandene SQL-Server-Datenbank aus. (Oder klicken Sie auf **Neu**, um dem Pool einen neuen Datenbankspeicher zuzuordnen.) Wenn Sie einen neuen Datenbankspeicher verwenden möchten, geben Sie im Dialogfeld **Neuen SQL-Speicher definieren** den vollqualifizierten Domänenname des SQL-Server-Computers im Feld **SQL-Server-FQDN** ein. Wenn Sie die SQL-Server-Standardinstanz für diesen Speicher verwenden möchten, wählen Sie **Standardinstanz** aus. Andernfalls wählen Sie **Benannte Instanz** aus und geben den Namen der Instanz im Feld **Benannte Instanz** ein.
    
    Im Dialogfeld **Eigenschaften bearbeiten** haben Sie auch die Möglichkeit, einen SQL-Spiegel für Ihre Überwachungsdatenbank zu erstellen (mit einem SQL-Spiegel können Sie zwei Kopien Ihrer Überwachungsdatenbank verwalten, wobei eine Kopie auf dem Überwachungsspeichercomputer und die andere Kopie auf dem SQL-Spiegelcomputer verwaltet wird). Zum Aktivieren der Spiegelung wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus und geben die Portnummer für den Spiegelserver im Feld **Spiegelportnummer** ein.

7.  Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **OK**.

Nachdem Sie den Überwachungsspeicher einem Front-End-Pool zugeordnet haben, müssen Sie die neue Topologie veröffentlichen, damit die Änderungen wirksam werden. Führen Sie die folgenden Schritte im Topologie-Generator aus, um Ihre neue Topologie zu veröffentlichen:

1.  Klicken Sie auf **Aktion**, zeigen Sie auf **Topologie** und klicken Sie dann auf **Veröffentlichen**.

2.  Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.

3.  Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertigstellen**.

Nachdem die Topologie veröffentlicht wurde, können Sie die Überwachungsdatenbank auf dem Computer installieren, auf dem der Überwachungsspeicher gehostet wird. Die Überwachungsdatenbank kann mithilfe der lync Server-Verwaltungsshell und Windows PowerShell installiert werden. Wenn Sie die Datenbank lokal installieren möchten (wenn Sie die Datenbank auf demselben Computer installieren möchten, auf dem Sie die lync Server-Verwaltungsshell ausführen), starten Sie die Verwaltungsshell auf dem entsprechenden Computer, und geben Sie dann den folgenden Befehl ein, und drücken Sie die EINGABETASTE:

    Install-CsDatabase -LocalDatabases

Wenn Sie den vorhergehenden Befehl ausführen, liest Install-CsDatabase die aktuelle lync Server-Topologie, ermittelt, welche Datenbanken auf dem lokalen Computer installiert werden müssen, und installiert und konfiguriert dann jede dieser Datenbankenautomatisch.

Zum Installieren der Datenbank auf einem Remotecomputer (also einem anderen Computer als dem Computer, auf dem die Verwaltungsshell ausgeführt wird) müssen Sie mindestens zwei Parameter einbeziehen: den ConfiguredDatabases-Parameter und den SqlServerFqdn-Parameter. Diese Parameter weisen das Install-CsDatabase-Cmdlet an, die lync Server-Topologie abzurufen und dann die erforderlichen Datenbanken auf dem durch den SqlServerFqdn-Parameter angegebenen Computer zu installieren und zu konfigurieren. Der SqlServerFqdn-Parameter muss einen Parameterwert verwenden, der den vollqualifizierten Domänennamen des Computers darstellt, auf dem die Datenbanken installiert werden sollen.

Beispielsweise wird mit dem folgenden Befehl die Überwachungsdatenbank auf dem Computer atl-sql-001.litwareinc.com installiert:

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

Alternativ können Sie die Überwachungsdatenbank installieren, indem Sie den lync Server-Bereitstellungs-Assistenten auf dem Computer ausführen, auf dem der Überwachungsspeicher gehostet wird. Dazu melden Sie sich am entsprechenden Computer an und führen das folgende Verfahren aus:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Bereitstellungs-Assistent**.

2.  Klicken Sie im Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren**.

3.  Klicken Sie auf der Seite **Deploy** unter **Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten** erneut auf **Ausführen**.

4.  Klicken Sie im Assistenten zum Einrichten von lync Server-Komponenten auf der Seite **Setup lync Server Components** auf **weiter**.

5.  Geben Sie auf der Seite **Pfad zur MSIs angeben** den Pfad zu der Datei Ocscore.msi (eine Datei, die im Lieferumfang Ihrer lync Server-Installationsmedien enthalten ist) ein, und klicken Sie dann auf **weiter**.

6.  Klicken Sie auf der Seite **Befehle ausführen** auf **Fertigstellen**.

Wenn Sie sicherstellen möchten, dass alle erforderlichen lync Server-Dienste gestartet wurden, klicken Sie unter der Überschrift **Schritt 4: Starten von Diensten** auf der Seite **Bereitstellen** auf **Ausführen** .

</div>

<span> </span>

</div>

</div>

</div>

