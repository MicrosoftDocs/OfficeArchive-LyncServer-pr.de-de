---
title: 'Lync Server 2013: Modi für die Medienumgehung'
description: 'Lync Server 2013: Medien Umgehungs Modi.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a7f1a71930df7ef92a29087f42bdb9382b3904c
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425689"
---
# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="68cad-103">Modi für die Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68cad-103">Media bypass modes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="68cad-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="68cad-104">

<span> </span></span></span>

<span data-ttu-id="68cad-105">_**Letztes Änderungsdatum des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="68cad-105">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="68cad-p101">Sie müssen die Medienumgehung sowohl global als auch für jeden einzelnen PSTN-Trunk konfigurieren. Wenn Sie die Medienumgehung global aktivieren, haben Sie die Auswahl zwischen zwei Optionen: **Immer umgehen** und **Informationen zu Standort und Region verwenden**.</span><span class="sxs-lookup"><span data-stu-id="68cad-p101">You must configure media bypass both globally and for each individual PSTN trunk. When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="68cad-p102">Wie der Name vermuten lässt, wird die Medienumgehung bei Auswahl von **Immer umgehen** auf alle PSTN-Anrufe angewendet. **Immer umgehen** wird in Bereitstellungen verwendet, in denen weder eine Anrufsteuerung noch die Bereitstellung detaillierter Konfigurationsinformationen für die Medienumgehung erforderlich ist. Darüber hinaus wird die Option **Immer umgehen** verwendet, wenn vollständige Konnektivität zwischen Clients und PSTN-Gateways gegeben ist. In dieser Konfiguration sind alle Subnetze einer einzigen ID für die Umgehung zugeordnet, die durch das System berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="68cad-p102">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls. **Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass. Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways. In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="68cad-p103">Bei Auswahl der Option **Informationen zu Standort und Region verwenden** werden Entscheidungen zur Medienumgehung anhand der ID für die Umgehung und der zugeordneten Standort- und Regionenkonfiguration getroffen. Diese Konfiguration bietet die Flexibilität, die Medienumgehung für die gängigsten Topologien zu konfigurieren, da einerseits genau gesteuert werden kann, wann eine Umgehung stattfindet, und andererseits eine Interaktion mit der Anrufsteuerung unterstützt wird. Das System versucht, diese Aufgabe zu vereinfachen, indem automatisch IDs für die Umgehung zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="68cad-p103">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision. This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC). The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="68cad-115">Das System weist jeder Region eine einzelne, eindeutige ID für die Umgehung zu.</span><span class="sxs-lookup"><span data-stu-id="68cad-115">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="68cad-116">Jeder Standort, der über eine WAN-Verbindung ohne Bandbreiteneinschränkungen mit einer Region verbunden ist, erbt dieselbe Umgehungs-ID wie die Region.</span><span class="sxs-lookup"><span data-stu-id="68cad-116">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="68cad-117">Einem Standort, der über eine WAN-Verbindung mit Bandbreiteneinschränkungen mit der Region verbunden ist, wird eine andere ID für die Umgehung zugewiesen als der Region.</span><span class="sxs-lookup"><span data-stu-id="68cad-117">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="68cad-118">Die jedem Standort zugeordneten Subnetze erben die Umgehungs-ID für diesen Standort.</span><span class="sxs-lookup"><span data-stu-id="68cad-118">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="68cad-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68cad-119">See Also</span></span>


[<span data-ttu-id="68cad-120">Übersicht über die medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68cad-120">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="68cad-121">Medienumgehung und Anrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68cad-121">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="68cad-122">Technische Anforderungen für die Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68cad-122">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

<span data-ttu-id="68cad-123"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="68cad-123"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

