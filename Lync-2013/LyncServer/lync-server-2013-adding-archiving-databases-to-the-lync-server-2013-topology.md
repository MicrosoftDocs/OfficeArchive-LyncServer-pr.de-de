---
title: 'Lync Server 2013: Hinzufügen von Archivierungsdatenbanken zur lync Server 2013-Topologie'
description: 'Lync Server 2013: Hinzufügen von Archivierungsdatenbanken zur lync Server 2013-Topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12387c06bc55775ef824c061228a68021046c113
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49439254"
---
# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>Hinzufügen von Archivierungsdatenbanken zur lync Server 2013-Topologie

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

Sie müssen die Archivierung in Ihre Topologie aufnehmen, bevor Sie Ihre Bereitstellung zur Unterstützung der Archivierung konfigurieren können. Die Informationen in diesem Thema erläutern, wie Sie mithilfe des Topologie-Generators Ihrer vorhandenen Topologie Archivierung hinzufügen.

<div>


> [!NOTE]  
> Wenn Sie die Microsoft Exchange-Integration zum Speichern von Archivierungsdaten und-Dateien auf Exchange 2013-Servern für alle Benutzer in Ihrer Bereitstellung verwenden möchten, geben Sie keinen <STRONG>Archivierungs-SQL Server-Speicher</STRONG> an, oder verwenden Sie die <STRONG>Spiegelungsinformationen des SQL Server-Speichers</STRONG> .



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>So fügen Sie Ihrer Topologie Unterstützung für die Archivierungsdatenbank hinzu

1.  Melden Sie sich auf einem Computer, auf dem lync Server 2013 ausgeführt wird oder auf dem die lync Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Gruppe "Benutzer" (oder einem Konto mit entsprechenden Benutzerrechten) ist.
    
    <div>
    

    > [!NOTE]  
    > Sie können eine Topologie mithilfe eines Kontos definieren, das ein Mitglied der lokalen Benutzergruppe ist, aber zum Veröffentlichen einer Topologie, die zum Hinzufügen eines Servers zur Topologie erforderlich ist, müssen Sie ein Konto verwenden, das ein Mitglied der Gruppe der <STRONG>Domänenadministratoren</STRONG> und der <STRONG>RTCUniversalServerAdmins</STRONG> -Gruppe ist. und dies verfügt über die Vollzugriffsberechtigung (also lesen, schreiben und ändern) für die Dateifreigabe, die Sie für den lync Server 2013-Dateispeicher verwenden (Dies bedeutet, dass der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control List) oder ein Konto mit entsprechenden rechten konfigurieren kann.

    
    </div>

2.  Starten Sie den Topologie-Generator.

3.  Navigieren Sie in der Konsolenstruktur zu dem Front-End-Pool, in dem die Archivierung bereitgestellt werden soll, und klicken Sie dann auf den Namen des Front-End-Pools, in dem die Archivierung bereitgestellt werden soll.

4.  Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.

5.  Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.

6.  Führen Sie einen Bildlauf nach unten zur **Archivierung** aus.

7.  Aktivieren Sie das Kontrollkästchen **Archivierung**.

8.  Führen Sie unter **SQL Server-Archivierungsspeicher** eine der folgenden Aktionen aus:
    
      - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten. Wenn sich alle Benutzer auf Microsoft Exchange Server 2013 oder höher befinden, können Sie die lync-Kommunikation für alle Benutzer in Exchange archivieren. In diesem Fall müssen Sie den SQL Server-Archivierungsspeicher nicht konfigurieren.
    
      - Wenn Sie einen neuen SQL Server-Speicher angeben möchten, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** die folgenden Aktionen aus:
        
          - Geben Sie im **SQL Server-FQDN** den FQDN des Servers an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
        
          - Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
        
          - Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in der Spiegelungs** Beziehung, und geben Sie dann in **Spiegelungs-Portnummer** die Portnummer an.

9.  Wenn Sie die SQL Server Store-Spiegelung verwenden möchten, wählen Sie **SQL Server Store-Spiegelung aktivieren** aus, und gehen Sie dann wie folgt vor:
    
      - Wenn Sie einen vorhandenen SQL Server-Speicher für die Spiegelung verwenden möchten, klicken Sie im Dropdown-Listenfeld **SQL Server Store Mirror-Archivierung** auf den Namen des SQL Server-Speichers, den Sie für die Spiegelung verwenden möchten.
    
      - Wenn Sie einen neuen SQL Server-Speicher für die Spiegelung angeben möchten, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** eine der folgenden Aktionen aus:
        
        1.  Geben Sie im **SQL Server-FQDN** den FQDN des SQL Server an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
        
        2.  Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.
        
        3.  Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in der Spiegelungs** Beziehung, und geben Sie dann in **Spiegelungs-Portnummer** die Portnummer an.
    
      - Wenn Sie die SQL Server-Spiegelung aktivieren und einen SQL Server-Spiegelungs Zeugen (eine dritte, separate SQL Server-Instanz, die den Zustand des primären SQL Server-Servers und der Spiegelungs Instanzen erkennen kann) einbeziehen möchten, aktivieren Sie das Kontrollkästchen **SQL Server-Spiegelungs Zeuge zum Aktivieren des automatischen Failovers verwenden** , und führen Sie dann eine der folgenden Aktionen aus:
        
        1.  Geben Sie im **SQL Server-FQDN** den FQDN des Servers an, auf dem Sie den neuen SQL Server-Spiegelungs Zeugen erstellen möchten.
        
        2.  Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
        
        3.  Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in der Spiegelungs** Beziehung, und geben Sie dann in **Spiegelungs-Portnummer** die Portnummer an.

10. Klicken Sie zum Speichern der Konfiguration auf **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

