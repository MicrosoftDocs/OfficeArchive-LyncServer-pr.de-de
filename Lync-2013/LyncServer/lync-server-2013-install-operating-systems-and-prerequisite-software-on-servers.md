---
title: Installieren von Betriebssystemen und erforderlicher Software auf Servern
description: Installieren Sie Betriebssysteme und die erforderliche Software auf Servern.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bae9e57db9c2f1d3f3bde7ce9cc7071b73aa01d
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427173"
---
# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="a04e3-103">Installieren von Betriebssystemen und erforderlicher Software auf Servern für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a04e3-103">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="a04e3-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="a04e3-104">

<span> </span></span></span>

<span data-ttu-id="a04e3-105">_**Letztes Änderungsdatum des Themas:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="a04e3-105">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="a04e3-106">Nachdem Sie die Hardware-und Systeminfrastruktur eingerichtet haben, müssen Sie die entsprechenden Windows-Betriebssysteme und-Updates sowie alle anderen erforderlichen Software auf jedem Server installieren, den Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a04e3-106">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="a04e3-107">Dazu gehören jede lync Server 2013-Serverrolle sowie alle zusätzlichen Infrastrukturserver oder-Server, auf denen SQL Server ausgeführt wird, die für die Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a04e3-107">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a04e3-108">In diesem Abschnitt werden die Installation von Betriebssystemen und die erforderliche Software für interne Server beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a04e3-108">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="a04e3-109">Wenn Sie Edgeserver zur Unterstützung des Zugriffs externer Benutzer bereitstellen, müssen Sie auch Betriebssysteme und die erforderliche Software für diese Server installieren, einschließlich Edgeserver und Reverse Proxy Server.</span><span class="sxs-lookup"><span data-stu-id="a04e3-109">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="a04e3-110">Details zum Vorbereiten von Servern zur Unterstützung des Zugriffs externer Benutzer finden Sie unter <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Vorbereiten der Installation von Servern im Umkreisnetzwerk für lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a04e3-110">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="a04e3-111">Installieren von Windows-Betriebssystemen auf Servern</span><span class="sxs-lookup"><span data-stu-id="a04e3-111">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="a04e3-112">Installieren Sie auf jedem Server, den Sie bereitstellen, das entsprechende Windows-Betriebssystem wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a04e3-112">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="a04e3-113">**Server mit lync Server 2013**   Ausführliche Informationen zu den Betriebssystemanforderungen für Server mit lync Server 2013 finden Sie unter Unterstützung von [Server-und Tools-Betriebssystem in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="a04e3-113">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="a04e3-114">**Datenbankserver**   Ausführliche Informationen zu den Betriebssystemanforderungen für Datenbankserver, einschließlich der Back-End-Datenbank, der Archivierungsdatenbank und der Überwachungsdatenbank, finden Sie in der SQL Server-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a04e3-114">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="a04e3-115">Informationen zu SQL Server 2012 finden Sie in der SQL Server 2012-Online Dokumentation unter [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="a04e3-115">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a04e3-116">Wenn Sie lync Server 2013 unter Windows Server &nbsp; 2008 &nbsp; R2 mit SP1 installieren, müssen Sie zuerst das im Microsoft Knowledge-Artikel 2646886 beschriebene Update installieren, "Fix: Heap Beschädigung tritt auf, wenn ein Modul die InsertEntityBody-Methode in IIS 7,5 aufruft", at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 2646886</A>.</span><span class="sxs-lookup"><span data-stu-id="a04e3-116">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="a04e3-117">Sie müssen auch die Registrierung ändern, wie im KB-Artikel <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Ereignis-IDs 32402, 61045 in lync Server 2013-Front-End-Servern protokolliert werden, die in Windows Server 2012 R2 installiert sind</A>.</span><span class="sxs-lookup"><span data-stu-id="a04e3-117">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="a04e3-118">Installieren von Windows Update auf Servern</span><span class="sxs-lookup"><span data-stu-id="a04e3-118">Install Windows Update on Servers</span></span>

<span data-ttu-id="a04e3-119">Installieren Sie die folgenden Updates von Windows Update auf jedem Server:</span><span class="sxs-lookup"><span data-stu-id="a04e3-119">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="a04e3-120">**Windows Update für Server mit lync Server 2013**   Details zu den Updates von Windows Update, die für Server mit lync Server 2013 erforderlich sind, finden Sie unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a04e3-120">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="a04e3-121">**Datenbankserver**   Details zu den Updates von Windows Update, die für Datenbankserver erforderlich sind, einschließlich der Back-End-Datenbank, der Archivierungsdatenbank und der Überwachungsdatenbank, finden Sie in der SQL Server 2012-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a04e3-121">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="a04e3-122">Informationen zu SQL Server 2012 finden Sie in der SQL Server 2012-Online Dokumentation unter [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="a04e3-122">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="a04e3-123">Installieren anderer erforderlicher Software auf Servern</span><span class="sxs-lookup"><span data-stu-id="a04e3-123">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="a04e3-124">Lync Server 2013 erfordert die Installation der folgenden zusätzlichen Software auf Servern:</span><span class="sxs-lookup"><span data-stu-id="a04e3-124">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="a04e3-125">**Erforderliche Software für Server mit lync Server 2013**   Die zusätzlichen Softwarevoraussetzungen für Server mit lync Server 2013 hängen davon ab, welche Serverrolle bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a04e3-125">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="a04e3-126">Details zu den spezifischen Softwareanforderungen für jeden Server finden Sie unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a04e3-126">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="a04e3-127">**Windows Identity Foundation**   Lync Server 2013 erfordert die Installation von Windows Identity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a04e3-127">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="a04e3-128">Um zu überprüfen, ob Sie bereits auf Ihrem Computer installiert ist, wechseln Sie zur Systemsteuerung, klicken Sie auf **Programme und Funktionen**, **zeigen Sie installierte Updates** an, und schauen Sie unter **Microsoft Windows** nach.</span><span class="sxs-lookup"><span data-stu-id="a04e3-128">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="a04e3-129">Informationen zum Installieren von Windows Identity Foundation finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="a04e3-129">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="a04e3-130">**Microsoft .NET Framework 4,5**   Die 64-Bit-Version von Microsoft .NET Framework 4,5 ist für lync Server 2013 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a04e3-130">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="a04e3-131">**Erforderliche Software für Datenbankserver**   Details zum Windows-Update, das für Datenbankserver erforderlich ist, einschließlich der Back-End-Datenbank, der Archivierungsdatenbank und der Überwachungsdatenbank, finden Sie in der SQL Server 2012-Dokumentation unter [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="a04e3-131">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a04e3-132">Lync Server 2013 installiert Microsoft SQL Server 2012 Express automatisch auf jedem Standard Edition-Server und auf jedem Server mit lync Server 2013, auf dem sich der lokale Konfigurationsspeicher befindet.</span><span class="sxs-lookup"><span data-stu-id="a04e3-132">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="a04e3-133">**Windows Media-Format Laufzeit**   Auf allen Front-End-Servern und Standard Edition-Servern, auf denen Konferenzen bereitgestellt werden, muss die Windows Media-Format Laufzeit installiert sein.</span><span class="sxs-lookup"><span data-stu-id="a04e3-133">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="a04e3-134">Die Windows Media-Format Laufzeit ist erforderlich, um die Windows Media-Audio-Dateien (WMA) auszuführen, die von den Anwendungen für die Anruf Park-, Ankündigungs-und Reaktionsgruppen für Ankündigungen und Musik abgespielt werden.</span><span class="sxs-lookup"><span data-stu-id="a04e3-134">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a04e3-135">Für Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media-Format Laufzeit mit Microsoft Media Foundation installiert.</span><span class="sxs-lookup"><span data-stu-id="a04e3-135">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a04e3-136">Für Windows Server &nbsp; 2008 und Windows Server &nbsp; 2008 &nbsp; R2 wird die Windows Media-Format Laufzeit als Teil der Windows-Desktop Oberfläche installiert.</span><span class="sxs-lookup"><span data-stu-id="a04e3-136">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="a04e3-137">Es wird empfohlen, dass Sie die Windows-Desktop Umgebung installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="a04e3-137">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="a04e3-138">Wenn lync Server 2013 diese Software auf dem Server nicht findet, werden Sie aufgefordert, Sie zu installieren, und dann müssen Sie den Server neu starten, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a04e3-138">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    <span data-ttu-id="a04e3-139"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="a04e3-139"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

