---
title: 'Lync Server 2013: Sichern und Schützen der Datenbanken'
description: 'Lync Server 2013: Härten und schützen von Datenbanken.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af1ed8f54384e8ecac3b1e4ce6a4253a10bcc2c6
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427761"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="e95f6-103">Sichern und Schützen der Datenbanken von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e95f6-103">Hardening and protecting the databases of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e95f6-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e95f6-104">

<span> </span></span></span>

<span data-ttu-id="e95f6-105">_**Letztes Änderungsdatum des Themas:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="e95f6-105">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="e95f6-106">Microsoft lync Server 2013 hängt auch von SQL Server-Datenbanken zum Speichern von Benutzerinformationen, Konferenzstatus, Archivierungsdaten und Anruf Detail Datensätzen (CDRs) ab.</span><span class="sxs-lookup"><span data-stu-id="e95f6-106">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="e95f6-107">Sie können die Verfügbarkeit von lync Server 2013-Daten in lync Server-Back-End-Datenbanken maximieren, indem Sie die Anwendungsdaten auf eine Weise partitionieren, die die Fehlertoleranz verbessert und die Problembehandlung vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="e95f6-107">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="e95f6-108">Um diese Ziele zu erreichen, partitionieren Sie die Anwendungsdaten nach folgendem:</span><span class="sxs-lookup"><span data-stu-id="e95f6-108">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="e95f6-109">**Verwenden von bewährten Methoden für die Server Partitionierung**   Trennen Sie das Betriebssystem, die Anwendung und die Programmdateien von den Datendateien.</span><span class="sxs-lookup"><span data-stu-id="e95f6-109">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="e95f6-110">**Speichern von Transaktionsprotokolldateien und Datenbankdateien**   Speichern Sie diese Dateien separat, um die Fehlertoleranz zu erhöhen und die Wiederherstellung zu optimieren, und speichern Sie Sie auf einem verschlüsselten Datenträger oder Volume.</span><span class="sxs-lookup"><span data-stu-id="e95f6-110">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="e95f6-111">**Verwenden von Serverclustern**   Clustern Sie die Back-End-Server, um die Systemverfügbarkeit von lync Server 2013 zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="e95f6-111">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="e95f6-112">**Sicherstellen, dass alle Datensicherungen verschlüsselt und ordnungsgemäß verarbeitet werden**   Verloren gegangene, verworfene oder verlegte Sicherungsmedien können eine erhebliche Gefährdung der Datensicherheit für lync Server 2013-Bereitstellungen darstellen.</span><span class="sxs-lookup"><span data-stu-id="e95f6-112">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="e95f6-113">Auf einem lync Server 2013-Server mit Ausnahme des Standard Edition-Servers ist die SQL Server Express-Instanz (RTCLOCAL-Instanz) nicht Remote verfügbar, und es werden keine lokalen Firewall-Ausnahmen erstellt, mit Ausnahme von SQL Server Express auf einem Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="e95f6-113">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="e95f6-114">Auf einem Standard Edition-Server sind sowohl die Back-End-Datenbank als auch der zentrale Verwaltungsspeicher (CMS) so eingerichtet, dass ein Remotezugriff möglich ist.</span><span class="sxs-lookup"><span data-stu-id="e95f6-114">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="e95f6-115">Zum Härten von SQL Server-Datenbankenkönnen Sie die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="e95f6-115">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="e95f6-116">Passen Sie die SQL Server Express-Firewall auf Standard Edition-Servern an, um den Umfang der Server zu begrenzen, die Remote auf die Datenbank zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="e95f6-116">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database.</span></span> <span data-ttu-id="e95f6-117">Standardmäßig kann eine beliebige IP-Adresse Remote auf die Datenbank zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e95f6-117">By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="e95f6-118">Verwenden Sie den SQL Server-Konfigurations-Manager, um die Protokolle, IP-Adressen und Ports für den SQL Server-Remotezugriff anzugeben:</span><span class="sxs-lookup"><span data-stu-id="e95f6-118">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="e95f6-119">Lync Server 2013 verwendet das TCP/IP-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="e95f6-119">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="e95f6-120">Sie unterstützt IP Version 4 (IPv4), aber nicht IP Version 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="e95f6-120">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e95f6-121">Lync Server 2013 kann in einem Netzwerk mit aktiviertem Dual IP Stack funktionieren.</span><span class="sxs-lookup"><span data-stu-id="e95f6-121">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="e95f6-122">Lync Server 2013 unterstützt mehrere IP-Adressen (mehrfach vernetzte Netzwerk Adresskarten).</span><span class="sxs-lookup"><span data-stu-id="e95f6-122">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="e95f6-123">Sie können angeben, dass SQL Server nur bestimmte IP-Adressen (einzelne Adresse oder Subnetz) abhören und nur bestimmte Protokolle verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="e95f6-123">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="e95f6-124">Lync Server 2013 unterstützt statische und dynamische SQL Server-Ports.</span><span class="sxs-lookup"><span data-stu-id="e95f6-124">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="e95f6-125">Führen Sie SQL Server auf einem statischen (nicht standardmäßigen) Port aus, und führen Sie keinen SQL Server-Browser aus (damit der Abhör-Port nicht an den Client gemeldet werden kann).</span><span class="sxs-lookup"><span data-stu-id="e95f6-125">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="e95f6-126">Dies erfordert eine benutzerdefinierte Konfiguration für jeden SQL Server-Client, einschließlich Front-End-Server, Überwachungsserver, Archivierungsserver und Verwaltungskonsolen (mit lync Server-Verwaltungsshell, lync Server Control Panel oder Topology Builder) und allen anderen Servern, auf denen lync Server-Datenbanken ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="e95f6-126">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e95f6-127">Der Zugriff auf Datenbanken muss auf vertrauenswürdige Datenbankadministratoren limitiert sein.</span><span class="sxs-lookup"><span data-stu-id="e95f6-127">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="e95f6-128">Ein böswilliger Datenbankadministrator kann Daten in die Datenbanken einfügen oder ändern, um Berechtigungen über die lync Server 2013-Server zu erwerben oder vertrauliche Informationen von den Diensten abzurufen, auch wenn dem Datenbankadministrator kein direkter Zugriff oder keine Kontrolle über die lync Server 2013-Server gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="e95f6-128">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="e95f6-129">Details zu benutzerdefinierten Konfigurationen und zum Härten von SQL Server-Datenbanken finden Sie im NextHop-Blog Artikel "Verwenden von lync Server 2010 mit einer benutzerdefinierten SQL Server-Netzwerkkonfiguration" unter [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) .</span><span class="sxs-lookup"><span data-stu-id="e95f6-129">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e95f6-130">Sie können auch Betriebssysteme und Anwendungsserver verhärten, und Sie können mithilfe von Gruppenrichtlinien Sicherheits Sperrungen in ihrer lync Server-Bereitstellung implementieren.</span><span class="sxs-lookup"><span data-stu-id="e95f6-130">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="e95f6-131">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Härten und schützen von Servern und Anwendungen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e95f6-131">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



<span data-ttu-id="e95f6-132"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e95f6-132"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

