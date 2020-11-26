---
title: 'Lync Server 2013: Backup-Voraussetzungen für ABC-Pool-Failover'
description: 'Lync Server 2013: Backup-Voraussetzungen für ABC-Pool-Failover.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05eb0d2ad50f1ed4f04964158fb5d22d079f3b50
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437910"
---
# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="66820-103">Backup-Voraussetzungen für ABC-Pool-Failover in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66820-103">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="66820-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="66820-104">

<span> </span></span></span>

<span data-ttu-id="66820-105">_**Letztes Änderungsdatum des Themas:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="66820-105">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="66820-106">Um den größtmöglichen Nutzen aus der Verwendung des ABC-Pool-Failover-Verfahrens zu ziehen, müssen Sie bestimmte Sicherungen durchführen, bevor ein Notfall und ein Failover stattfinden:</span><span class="sxs-lookup"><span data-stu-id="66820-106">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="66820-107">Sie müssen die Konfigurationsdaten des Standort Informationsdiensts (Location Information Service, LIS) regelmäßig aus Pool A mithilfe des Cmdlets **Export-CsLISConfiguration** sichern.</span><span class="sxs-lookup"><span data-stu-id="66820-107">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="66820-108">Sie müssen die Konfigurationsdaten der Reaktionsgruppe in Pool A regelmäßig mithilfe des Cmdlets **Export-CsRgsConfiguration** sichern.</span><span class="sxs-lookup"><span data-stu-id="66820-108">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="66820-109">Im Allgemeinen empfehlen wir, dass Sie tägliche Sicherungen durchführen, aber wenn Sie über eine große Anzahl von Änderungen verfügen, möchten Sie möglicherweise häufigere Sicherungen planen.</span><span class="sxs-lookup"><span data-stu-id="66820-109">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="66820-110">Die Menge der Informationen, die Sie bei einem Notfall verlieren können, hängt von der Häufigkeit Ihrer Sicherungen sowie von der Häufigkeit und dem Umfang der Änderungen ab.</span><span class="sxs-lookup"><span data-stu-id="66820-110">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="66820-111">Die reaktionsgruppenanwendung kann nur einen Satz von Einstellungen auf Anwendungsebene pro Pool speichern.</span><span class="sxs-lookup"><span data-stu-id="66820-111">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="66820-112">Auf diese Einstellungen kann über die Cmdlets " **Get-CsRgsConfiguration** " zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="66820-112">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="66820-113">Zu den Einstellungen gehören die standardmäßige Musik-in-situ-Konfiguration, die standardmäßige Musik-in-Halt-Audiodatei, die Kulanzzeit für den Agenten-Rückruf und die Kontextkonfiguration des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="66820-113">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="66820-114">Diese Einstellungen können über das Cmdlet " **Import-CsRgsConfiguration** " von einem Pool zu einem anderen übertragen werden, indem Sie den **ReplaceExistingSettings** -Parameter verwenden, dieser Vorgang jedoch alle Einstellungen auf Anwendungsebene im Ziel Pool außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="66820-114">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="66820-115">Bewahren Sie an einem separaten Speicherort eine Sicherungskopie aller Original Audiodateien auf, die zum Konfigurieren der Antwortgruppen Anwendung verwendet wurden (also alle Aufzeichnungen oder Musik-in-halten-Dateien).</span><span class="sxs-lookup"><span data-stu-id="66820-115">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="66820-116">Wenn Sie benutzerdefinierte Musik-in-Warte-Dateien haben, die in einem Pool für den Anruf Park hochgeladen wurden, sollten Sie eine Kopie dieser Dateien an einem anderen Speicherort speichern.</span><span class="sxs-lookup"><span data-stu-id="66820-116">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="66820-117">Diese Dateien werden nicht im Rahmen des lync Server 2013-Wiederherstellungsprozesses gesichert, und Sie gehen verloren, wenn die Dateien, die in den Pool hochgeladen wurden, beschädigt, beschädigt oder gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="66820-117">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66820-118">Die Anwendung Parken kann nur einen Satz von Einstellungen und eine angepasste Musik-auf-halten-Audiodatei pro Pool speichern.</span><span class="sxs-lookup"><span data-stu-id="66820-118">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="66820-119">Auf diese Einstellungen kann über das Cmdlet " <STRONG>Get-CsCpsConfiguration</STRONG> " zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="66820-119">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="66820-120">Da der Disaster Recovery-Mechanismus für Call Park auf der Anwendung Parken des Backup-Pools basiert, werden die Einstellungen des primären Pools nicht gesichert, wenn ein Notfall eintritt.</span><span class="sxs-lookup"><span data-stu-id="66820-120">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="66820-121">Wenn der primäre Pool verloren geht, können diese Einstellungen nicht wiederhergestellt werden, und wenn ein neuer Pool zum Ersetzen des primären Pools bereitgestellt wird, müssen die Einstellungen für den Anruf Park und alle angepassten Musik-in-halten-Audiodateien neu konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="66820-121">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="66820-122">Wenn Sie Ankündigungen als Teil des Sprachfeatures "nicht zugewiesene Rufnummern" konfigurieren, empfehlen wir, dass Sie an einem anderen Speicherort eine Kopie einer beliebigen Originalaudiodatei beibehalten, die während der Erstkonfiguration verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="66820-122">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="66820-123">Wenn Sie dies nicht tun, können Sie eine Kopie der konfigurierten Audiodateien im Dateispeicher des Servers oder Pools abrufen, in den die Audiodateien importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="66820-123">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="66820-124">Diese Dateien werden nicht im Rahmen des lync Server 2013-Wiederherstellungsprozesses gesichert, und Sie gehen verloren, wenn die Dateien, die in den Pool hochgeladen wurden, beschädigt, beschädigt oder gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="66820-124">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="66820-125">Verwenden Sie Folgendes, um alle Audiodateien zu kopieren, die zum Konfigurieren des Sprachfeatures "nicht zugewiesene Rufnummern" aus dem Dateispeicher eines Servers oder Pools verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="66820-125">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="66820-126">Wenn Sie über Überwachungs-und Archivierungsdatenbanken in einem Pool verfügen, sollten Sie die SQL Server-Verwaltungstools verwenden, um Sie zu sichern.</span><span class="sxs-lookup"><span data-stu-id="66820-126">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="66820-127">Bei der ABC-Failover-Prozedur werden Überwachungs-und Archivierungsdatenbanken nicht beibehalten, wenn Sie in Pool A zusammengefasst werden, da diese Datenbanken nicht über den lync Server-Sicherungsdienst gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="66820-127">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

<span data-ttu-id="66820-128"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="66820-128"></div>

<span> </span>

</div>

</div>

</span></span></div>

