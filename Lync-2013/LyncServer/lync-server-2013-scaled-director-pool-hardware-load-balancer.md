---
title: 'Lync Server 2013: Skalierter Directorpool (Hardwarelastenausgleich)'
description: 'Lync Server 2013: skalierten Director-Pool – Hardware-Lastenausgleichsmodul.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 022c5afb67687149f8ba24655be2a1461d4371f2
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49393951"
---
# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="99731-103">Skalierter Directorpool (Hardwarelastenausgleich) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99731-103">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="99731-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="99731-104">

<span> </span></span></span>

<span data-ttu-id="99731-105">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="99731-105">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="99731-106">Ein skalierten Director-Pool, in dem mehr als ein Director bereitgestellt wird, um zusätzliche Kapazität zu verarbeiten und hohe Verfügbarkeit bereitzustellen, erfordert Lastenausgleich, um die Client-und Server Kommunikation an alle Mitglieder des Pools zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="99731-106">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="99731-107">Ein Director hostet Webdienste ähnlich wie ein Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="99731-107">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="99731-108">Für die Webdienste ist ein Hardware Lastenausgleich erforderlich.</span><span class="sxs-lookup"><span data-stu-id="99731-108">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="99731-109">In den folgenden Themen werden die Planungsüberlegungen zum Bereitstellen eines Director-Pools mithilfe des Hardwarelastenausgleichs beschrieben.</span><span class="sxs-lookup"><span data-stu-id="99731-109">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="99731-110">Wenn Sie beabsichtigen, den Hardwarelastenausgleich und den DNS-Lastenausgleich für den Director-Pool zu verwenden, lesen Sie das Thema [skalierten Director-Pool – DNS-Lastenausgleich und Hardwarelastenausgleich in lync Server 2013, in](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) dem die Planungsanforderungen für diese Topologie beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="99731-110">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="99731-111">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="99731-111">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="99731-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="99731-112">In This Section</span></span>

  - [<span data-ttu-id="99731-113">Zertifikatzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99731-113">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="99731-114">Portzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99731-114">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="99731-115">DNS-Übersicht für skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99731-115">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

<span data-ttu-id="99731-116"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="99731-116"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

