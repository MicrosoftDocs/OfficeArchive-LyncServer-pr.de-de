---
title: 'Lync Server 2013: Wiederherstellen eines Enterprise Edition-Back-End-Servers'
description: 'Lync Server 2013: Wiederherstellen eines Enterprise Edition-Back-End-Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2147aec00714704195399449e5d5e4d6ce609fd
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49442579"
---
# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="7e4d2-103">Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e4d2-103">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="7e4d2-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="7e4d2-104">

<span> </span></span></span>

<span data-ttu-id="7e4d2-105">_**Letztes Änderungsdatum des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="7e4d2-105">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="7e4d2-106">Verwenden Sie das in diesem Thema beschriebene Verfahren in den beiden folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="7e4d2-106">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="7e4d2-107">Sowohl die primäre als auch die Spiegeldatenbank eines gespiegelten Enterprise Edition-Back-End-Servers schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-107">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="7e4d2-108">Ein Enterprise Edition-Back-End-Server, der nicht gespiegelt wird, schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-108">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="7e4d2-109">Wenn Sie über ein Back-End für die Spiegelungs-Enterprise-Edition verfügen und nur die Spiegelungs-oder primäre Datenbank fehlschlägt, finden Sie Informationen unter [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013 – primär](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) zum Wiederherstellen der primären Datenbank und [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers 2013 in](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)</span><span class="sxs-lookup"><span data-stu-id="7e4d2-109">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="7e4d2-110">Wenn der zentrale Verwaltungsspeicher fehlschlägt, lesen Sie [Wiederherstellen des Servers, auf dem der zentrale Verwaltungsspeicher in lync Server 2013 gehostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)wird.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-110">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="7e4d2-111">Wenn ein Enterprise Edition-Mitgliedsserver, der nicht der Back-End-Server ist, fehlschlägt, lesen Sie [Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md)</span><span class="sxs-lookup"><span data-stu-id="7e4d2-111">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7e4d2-112">Wir empfehlen, dass Sie eine Image-Kopie des Systems erstellen, bevor Sie mit der Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-112">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="7e4d2-113">Sie können dieses Bild als Rollback-Punkt verwenden, falls während der Wiederherstellung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-113">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="7e4d2-114">Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem und SQL Server installiert haben, und die Zertifikate wiederherstellen oder erneut registrieren.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-114">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="7e4d2-115">Wiederherstellen eines Enterprise Edition-Back-End-Servers</span><span class="sxs-lookup"><span data-stu-id="7e4d2-115">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="7e4d2-116">Beginnen Sie mit einem sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-116">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e4d2-117">Befolgen Sie die Server Bereitstellungsverfahren Ihrer Organisation, um diesen Schritt ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-117">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="7e4d2-118">Melden Sie sich von einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, bei dem Server an, den Sie wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-118">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="7e4d2-119">Installieren Sie SQL Server 2012 oder SQL Server 2008 R2, und halten Sie die Namen der Instanz wie vor dem Fehler.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-119">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e4d2-120">Je nach Bereitstellung umfasst der Back-End-Server möglicherweise mehrere zusammengefasste oder getrennte Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-120">Depending on your deployment, the Back End Server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="7e4d2-121">Führen Sie die gleichen Schritte aus, um SQL Server zu installieren, den Sie ursprünglich für die Bereitstellung des Servers verwendet haben, einschließlich SQL Server-Berechtigungen und-Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-121">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="7e4d2-122">Nachdem Sie SQL Server installiert haben, führen Sie die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="7e4d2-122">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="7e4d2-123">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="7e4d2-124">Klicken Sie auf **Topologie aus vorhandener Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-124">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="7e4d2-125">Wählen Sie die Topologie aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-125">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="7e4d2-126">Klicken Sie auf **Ja** , um die Auswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-126">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="7e4d2-127">Klicken Sie mit der rechten Maustaste auf den **lync Server 2013** -Knoten, und klicken Sie dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-127">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="7e4d2-128">Folgen Sie dem Assistenten zum **Veröffentlichen der Topologie** .</span><span class="sxs-lookup"><span data-stu-id="7e4d2-128">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="7e4d2-129">Wählen Sie auf der Seite **create databases** die Datenbanken aus, die Sie neu erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-129">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7e4d2-130">Auf der Seite " <STRONG>Datenbankenerstellen</STRONG> " werden nur eigenständige Datenbanken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-130">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="7e4d2-131">Wenn Sie ein zurück gespiegeltes Back-End wiederherstellen, folgen Sie weiterhin dem restlichen Assistenten, bis die Aufforderung zum **Erstellen einer Spiegeldatenbank** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-131">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="7e4d2-132">Wählen Sie die Datenbank aus, die Sie installieren möchten, und schließen Sie den Vorgang ab.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-132">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="7e4d2-133">Führen Sie den restlichen Assistenten aus, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-133">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="7e4d2-134">Anstelle des Topologie-Generators können Sie das Cmdlet " <STRONG>install-CsDatabase</STRONG> " verwenden, um jede Datenbank zu erstellen, und das Cmdlet " <STRONG>install-CsMirrorDatabase</STRONG> ", um die Spiegelung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-134">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="7e4d2-135">Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-135">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="7e4d2-136">Wiederherstellen von Benutzerdaten durch Ausführen der folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="7e4d2-136">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="7e4d2-137">Kopieren Sie ExportedUserData.zip aus $Backup \\ in ein lokales Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-137">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="7e4d2-138">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="7e4d2-139">Bevor Sie die Benutzerdaten wiederherstellen, müssen Sie lync-Dienste beenden.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-139">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="7e4d2-140">Geben Sie dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7e4d2-140">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="7e4d2-141">Geben Sie zum Wiederherstellen der Benutzerdaten in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7e4d2-141">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="7e4d2-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7e4d2-142">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="7e4d2-143">Starten Sie lync Services neu, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="7e4d2-143">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="7e4d2-144">Wenn Sie die Reaktionsgruppe in diesem Pool bereitgestellt haben, stellen Sie die Konfigurationsdaten der Reaktionsgruppe wieder her.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-144">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="7e4d2-145">Ausführliche Informationen finden Sie unter [Wiederherstellen von Einstellungen für die Reaktionsgruppe in lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7e4d2-145">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="7e4d2-146">Wenn Sie einen Back-End-Server wiederherstellen, der Archivierungs-oder Überwachungsdatenbanken enthielt, stellen Sie die Archivierungs-oder Überwachungsdaten mithilfe eines SQL Server-Tools wie SQL Server Management Studio wieder her.</span><span class="sxs-lookup"><span data-stu-id="7e4d2-146">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="7e4d2-147">Ausführliche Informationen finden Sie unter [Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="7e4d2-147">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

<span data-ttu-id="7e4d2-148"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="7e4d2-148"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

