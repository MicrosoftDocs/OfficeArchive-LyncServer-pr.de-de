---
title: 'Lync Server 2013: Installieren von Edgeservern'
description: 'Lync Server 2013: Installieren von Edgeserver.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e699a7f41b0ee554bc85fb2d9a72a2d9a42870cb
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427208"
---
# <a name="install-edge-servers-for-lync-server-2013"></a>Installieren von Edgeservern für Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Sie installieren lync Server 2013 auf Edge-Servern mithilfe des lync Server-Bereitstellungs-Assistenten. Wenn Sie den Bereitstellungs-Assistenten auf jedem Edgeserver ausführen, können Sie die meisten Aufgaben ausführen, die zum Einrichten des Edge-Servers erforderlich sind. Damit Sie lync Server 2013 auf einem Edgeserver bereitstellen können, müssen Sie den Topologie-Generator bereits ausgeführt haben, um die Edgeserver-Topologie zu definieren und zu veröffentlichen und Sie auf Medien zu exportieren, die vom Edgeserver zur Verfügung stehen. Ausführliche Informationen finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) , [Exportieren Ihrer lync Server 2013-Topologie und Kopieren dieser in externe Medien für die Edge-Installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

Nachdem Sie den Bereitstellungs-Assistenten verwendet haben, um jeden Edgeserver zu installieren, die erforderlichen Zertifikate zu installieren und zuzuweisen und die erforderlichen Dienste zu starten, können Sie die Einrichtung mithilfe der Informationen unter [Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) zum Aktivieren und Konfigurieren des Zugriffs auf externe Benutzer sowie der Informationen unter [Überprüfen der Edge-Bereitstellung in lync Server 2013 zum über](lync-server-2013-verifying-your-edge-deployment.md)

<div>

## <a name="to-install-an-edge-server"></a>So installieren Sie einen Edgeserver

1.  Melden Sie sich bei dem Computer an, auf dem Sie Ihren Edge-Server als Mitglied der lokalen Gruppe Administratoren installieren möchten, oder ein Konto mit entsprechenden Benutzerrechten und Berechtigungen.

2.  Stellen Sie sicher, dass die Topologie-Konfigurationsdatei, die Sie mit dem Topologie-Generator erstellt und dann auf externe Medien exportiert und kopiert haben, auf dem Edgeserver verfügbar ist (beispielsweise Zugriff auf das USB-Laufwerk, auf dem Sie die Topologie-Konfigurationsdatei kopiert haben, oder überprüfen Sie den Zugriff auf die Netzwerkfreigabe, in die Sie die Datei kopiert haben).

3.  Starten Sie den Bereitstellungs-Assistenten.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie eine Meldung erhalten, die besagt, dass Sie Microsoft Visual C++ Redistributable installieren müssen, klicken Sie auf <STRONG>Ja</STRONG>. Im nächsten Dialogfeld können Sie den Standard <STRONG>Installationsspeicherort</STRONG> übernehmen oder auf die <STRONG>Schaltfläche Durchsuchen</STRONG> klicken, um einen anderen Speicherort auszuwählen, und dann auf <STRONG>Installieren</STRONG>klicken. Aktivieren Sie im nächsten Dialogfeld das Kontrollkästchen <STRONG>Ich akzeptiere die Bedingungen im Lizenzvertrag</STRONG> , und klicken Sie dann auf <STRONG>OK</STRONG>.

    
    </div>

4.  Klicken Sie im Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren**.

5.  Nachdem der Assistent den Bereitstellungsstatus für Schritt 1 festgelegt hat **. Installieren Sie den lokalen Konfigurationsspeicher**, klicken Sie auf **Ausführen** , und gehen Sie dann folgendermaßen vor:
    
      - Klicken Sie im Dialogfeld **lokales Replikat des zentralen Verwaltungsspeichers konfigurieren** auf **aus einer Datei importieren (empfohlen für Edgeserver)**, wechseln Sie zum Speicherort der exportierten Topologie-Konfigurationsdatei, wählen Sie die ZIP-Datei aus, klicken Sie auf **Öffnen**, und klicken Sie dann auf **weiter**.
    
      - Der Bereitstellungs-Assistent liest die Konfigurationsinformationen aus der Konfigurationsdatei und schreibt die XML-Konfigurationsdatei auf den lokalen Computer.
    
      - Nachdem der Prozess **Befehle werden ausgeführt** abgeschlossen wurde, klicken Sie auf **Fertig stellen**.

6.  Klicken Sie im Bereitstellungs-Assistenten auf **Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten** , um die in der XML-Konfigurationsdatei angegebenen Edge-Komponenten von lync Server 2013 zu installieren, die auf dem lokalen Computer gespeichert sind.

7.  Nachdem Sie die Installation abgeschlossen haben, verwenden Sie die Informationen unter [Einrichten von Edge-Zertifikaten für lync Server 2013](lync-server-2013-set-up-edge-certificates.md) , um die erforderlichen Zertifikate zu installieren und zuzuweisen, bevor Sie Dienste starten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

