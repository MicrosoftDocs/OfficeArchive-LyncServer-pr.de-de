---
title: 'Lync Server 2013: Übersicht über den Sicherungs-und Wiederherstellungsprozess'
description: 'Lync Server 2013: Übersicht über den Sicherungs-und Wiederherstellungsprozess.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77b833a05021d3a848e9de1ee8768f7daa194c6a
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437994"
---
# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="6c73b-103">Übersicht über den Sicherungs-und Wiederherstellungsprozess für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c73b-103">Backup and restoration process overview for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="6c73b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="6c73b-104">

<span> </span></span></span>

<span data-ttu-id="6c73b-105">_**Letztes Änderungsdatum des Themas:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="6c73b-105">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="6c73b-106">Dieser Abschnitt enthält eine Übersicht über die Funktionsweise des Sicherungs-und Wiederherstellungsprozesses für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c73b-106">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="6c73b-107">Sie verwenden das gleiche Verfahren für alle Standard Edition-Server und Enterprise Edition-Server unabhängig von deren Standort.</span><span class="sxs-lookup"><span data-stu-id="6c73b-107">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="6c73b-108">Im Allgemeinen funktioniert der Sicherungsvorgang wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6c73b-108">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="6c73b-109">Sie erstellen einen Sicherungsspeicherort als freigegebenen Ordner auf einem eigenständigen Computer, der nicht zu einem Pool gehört.</span><span class="sxs-lookup"><span data-stu-id="6c73b-109">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="6c73b-110">Auf den Speicherort der Sicherung wird in **$Backup** verwiesen.</span><span class="sxs-lookup"><span data-stu-id="6c73b-110">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="6c73b-111">In regelmäßigen Abständen sichern Sie alle lync Server-Datenbanken und alle Dateispeicher, die unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013 beschrieben werden: Daten](lync-server-2013-backup-and-restoration-requirements-data.md) , indem Sie die unter [Sichern von lync Server 2013](lync-server-2013-backing-up-lync-server.md) beschriebenen Verfahren ausführen, in dem der zentrale Verwaltungsspeicher alle Server Einstellungen und-Konfigurationen umfasst.</span><span class="sxs-lookup"><span data-stu-id="6c73b-111">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="6c73b-112">Jedes Mal, wenn Sie eine nachfolgende Sicherung ausführen, erstellen Sie einen neuen freigegebenen Ordner und ändern den Pfad, in dem Verweise **$Backup** .</span><span class="sxs-lookup"><span data-stu-id="6c73b-112">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="6c73b-113">Im Allgemeinen funktioniert der Wiederherstellungsprozess wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6c73b-113">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="6c73b-114">Wenn ein Fehler oder Ausfall auftritt, stellen Sie die Daten an dem Speicherort wieder her, auf den **$Backup** auf neue oder bereinigte Computer verweisen.</span><span class="sxs-lookup"><span data-stu-id="6c73b-114">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6c73b-115">Durch diesen Wiederherstellungsprozess werden keine Daten auf einem vorhandenen Serverzustand wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="6c73b-115">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="6c73b-116">Dieser Vorgang erfordert also, dass der Server sauber oder neu ist.</span><span class="sxs-lookup"><span data-stu-id="6c73b-116">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="6c73b-117">Damit Ihre Benutzer-und Konferenz Informationen bis zum Zeitpunkt des Fehlers wiederherstellbar sind, können Sie eine Disaster Recovery-Topologie mit gekoppelten Front-End-Pools implementieren, wie in [Planen für Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c73b-117">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="6c73b-118">Alle DNS-Konfigurationen (Domain Name System), DHCP-Konfiguration (Dynamic Host Configuration Protocol), Domänennamen, vollqualifizierte Computer Domänennamen (FQDNs), Dateispeicher Pfade usw. müssen zum Zeitpunkt der Wiederherstellung identisch sein, die Sie zum Zeitpunkt der Wiederherstellung hatten.</span><span class="sxs-lookup"><span data-stu-id="6c73b-118">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="6c73b-119">Wenn ein Server mit lync Server ausfällt, umfasst die Wiederherstellung die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="6c73b-119">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="6c73b-120">Installieren Sie das Betriebssystem auf einem neuen oder sauberen Computer mit demselben FQDN wie der fehlerhafte Computer.</span><span class="sxs-lookup"><span data-stu-id="6c73b-120">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="6c73b-121">Installieren Sie Zertifikate erneut.</span><span class="sxs-lookup"><span data-stu-id="6c73b-121">Reinstall certificates.</span></span>

  - <span data-ttu-id="6c73b-122">Wenn der Server eine Datenbank gehostet hat, installieren Sie Microsoft SQL Server 2012 oder Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="6c73b-122">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="6c73b-123">Wenn der Server eine Datenbank gehostet hat, führen Sie im Allgemeinen den Topologie-Generator aus, um die Datenbank zu erstellen und zu installieren sowie Zugriffssteuerungslisten (ACLs) einzurichten.</span><span class="sxs-lookup"><span data-stu-id="6c73b-123">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="6c73b-124">Wenn der Server eine Serverrolle gehostet hat, führen Sie im allgemeinen Schritt 1 bis Schritt 4 des lync Server-Bereitstellungs-Assistenten aus, um die lokalen Konfigurationsdateien zu installieren, die Serverrollenkomponenten zu installieren, Zertifikate zuzuweisen und die Dienste zu starten.</span><span class="sxs-lookup"><span data-stu-id="6c73b-124">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c73b-125">Wenn der Server eine Datenbank mit der Serverrolle gehostet hat, wird mit Schritt 2 des lync Server-Bereitstellungs-Assistenten die Datenbank neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="6c73b-125">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="6c73b-126">Wenn der Server eine Datenbank gehostet hat, stellen Sie die gesicherten Daten wieder her.</span><span class="sxs-lookup"><span data-stu-id="6c73b-126">If the server hosted a database, restore the backed up data.</span></span>

<span data-ttu-id="6c73b-127"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="6c73b-127"></div>

<span> </span>

</div>

</div>

</span></span></div>

