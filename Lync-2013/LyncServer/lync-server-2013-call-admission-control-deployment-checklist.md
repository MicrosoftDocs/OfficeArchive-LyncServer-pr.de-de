---
title: 'Lync Server 2013: Bereitstellungscheckliste für die Anruf Zulassungs Steuerung'
description: 'Lync Server 2013: Bereitstellungscheckliste für Anruf Zulassungs Steuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db7a69bda3048f93089a47b43a0b433946b783f1
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49435915"
---
# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="5f45b-103">Checkliste für die Bereitstellung der Anrufsteuerung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f45b-103">Call admission control deployment checklist for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="5f45b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="5f45b-104">

<span> </span></span></span>

<span data-ttu-id="5f45b-105">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="5f45b-105">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="5f45b-106">Verwenden Sie die folgende Checkliste, um sicherzustellen, dass Sie alle erforderlichen Konfigurationsaufgaben zum Bereitstellen der Anrufannahme Steuerung (CAC) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="5f45b-106">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="5f45b-107">Wenn ein oder mehrere Edgeserver bereitgestellt werden, muss jede externe Schnittstellen-IP-Adresse der Subnetliste in den Netzwerkkonfigurationseinstellungen mit einer Bitmaske von 32 hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5f45b-107">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="5f45b-108">Sie sollten dieses Subnetz (IP-Adresse) außerdem der Netzwerkstandort-ID für den geografischen Standort zuordnen, an dem der A/V-Edgedienst bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5f45b-108">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5f45b-109">Edgeserver müssen keine CAC-Implementierung implementieren.</span><span class="sxs-lookup"><span data-stu-id="5f45b-109">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="5f45b-110">Stellen Sie sicher, dass CAC aktiviert ist, entweder über die lync Server-Systemsteuerung oder durch Ausführen des Cmdlets gemäß den Angaben unter [Aktivieren der Anrufsteuerung in lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="5f45b-110">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="5f45b-111">Stellen Sie sicher, dass die Anrufsteuerung an allen zentralen Standorten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5f45b-111">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="5f45b-112">Dies kann über den Topologie-Generator erfolgen.</span><span class="sxs-lookup"><span data-stu-id="5f45b-112">This can be done through the Topology Builder.</span></span> <span data-ttu-id="5f45b-113">Wenn beim Veröffentlichen eine Warnung generiert wird, ignorieren Sie diese *nicht*.</span><span class="sxs-lookup"><span data-stu-id="5f45b-113">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="5f45b-114">Stellen Sie sicher, dass alle im Unternehmensnetzwerk verwalteten Subnetze in den Netzwerkkonfigurationseinstellungen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="5f45b-114">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="5f45b-115">Darüber hinaus ist es wichtig, dass jedes Subnetz einer Netzwerk Website zugeordnet ist, wie unter Zuordnen eines Subnetzes zu [einer Netzwerk Website in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="5f45b-115">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="5f45b-116">Stellen Sie sicher, dass die Subnetz- oder IP-Adressen aller Front-End-Server, Survivable Branch Appliances (SBAs), A/V-Konferenzserver (sofern in einem separaten Pool bereitgestellt) und Vermittlungsserver in den Netzwerkkonfigurationseinstellungen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="5f45b-116">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

<span data-ttu-id="5f45b-117"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="5f45b-117"></div>

<span> </span>

</div>

</div>

</span></span></div>

