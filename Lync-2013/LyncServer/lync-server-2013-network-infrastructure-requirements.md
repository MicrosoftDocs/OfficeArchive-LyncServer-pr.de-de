---
title: Anforderungen für die Netzwerkinfrastruktur in lync Server 2013
description: Anforderungen für die Netzwerkinfrastruktur in lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f7ff21c2f936ef8e048f6831d55408994055400
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425192"
---
# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="1960e-103">Anforderungen an die Netzwerkinfrastruktur für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1960e-103">Network infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="1960e-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="1960e-104">

<span> </span></span></span>

<span data-ttu-id="1960e-105">_**Letztes Änderungsdatum des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="1960e-105">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="1960e-106">Die Netzwerkadapterkarte jedes Servers in der lync Server 2013-Topologie muss mindestens 1 Gigabit pro Sekunde (Gbit/s) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1960e-106">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="1960e-107">Im Allgemeinen sollten Sie alle Serverrollen innerhalb der lync Server-Topologie mit einem lokalen Netzwerk (LAN) mit geringer Latenz und großer Bandbreite verbinden.</span><span class="sxs-lookup"><span data-stu-id="1960e-107">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="1960e-108">Die Größe des LANs hängt von der Größe der Topologie ab:</span><span class="sxs-lookup"><span data-stu-id="1960e-108">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="1960e-109">In Standard Edition-Topologien sollten sich die Server in einem Netzwerk befinden, das 1 Gbit/s Ethernet oder eine Entsprechung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1960e-109">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="1960e-110">In Front-End-Pool Topologien sollten sich die meisten Server in einem Netzwerk befinden, das mehr als 1 Gbit/s unterstützt, insbesondere bei der Unterstützung von Audio/Video-Konferenzen (a/V) und Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="1960e-110">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="1960e-111">Zur Integration in das Telefonfestnetz (Public Switched Telephone Network, PSTN) können Sie entweder T1/E1-Leitungen oder das SIP-Trunking verwenden.</span><span class="sxs-lookup"><span data-stu-id="1960e-111">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="1960e-112">Audio/Video-Netzwerkanforderungen</span><span class="sxs-lookup"><span data-stu-id="1960e-112">Audio/Video Network Requirements</span></span>

<span data-ttu-id="1960e-113">Zu den Netzwerkanforderungen für Audio/Video (a/V) in einer lync Server-Bereitstellung gehören die folgenden:</span><span class="sxs-lookup"><span data-stu-id="1960e-113">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="1960e-114">Wenn Sie einen einzelnen Edgeserver oder einen Edge-Pool mithilfe des DNS-Lastenausgleichs bereitstellen, können Sie die externe Firewall als NAT konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1960e-114">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="1960e-115">Sie können die interne Firewall nicht als NAT konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1960e-115">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="1960e-116">Details zu diesen Anforderungen finden Sie unter [Ermitteln der externen A/V-Firewall und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1960e-116">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1960e-117">Wenn Sie über einen Edge-Pool verfügen und ein Hardware-Lastenausgleichsmodul verwenden, müssen Sie öffentliche IP-Adressen auf jedem der Edgeserver verwenden, und Sie können NAT nicht für die Server oder den Pool auf Ihrem NAT-Gerät verwenden (beispielsweise die Firewall oder ein anderes Infrastruktur Gerät, das NAT-oder ausgehenden Datenverkehr führen würde).</span><span class="sxs-lookup"><span data-stu-id="1960e-117">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="1960e-118">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port Zusammenfassung – skalierter konsolidierter Edge mit Hardwarelastenausgleichs in lync Server 2013</A> in der Dokumentation zur Planung für den externen Benutzer Zugriff.</span><span class="sxs-lookup"><span data-stu-id="1960e-118">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="1960e-119">Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="1960e-119">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="1960e-120">Wenn Sie IPsec (Internet Protocol Security) verwenden, wird empfohlen, IPsec für die Portbereiche zu deaktivieren, die für die Übertragung von A/V-Datenverkehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1960e-120">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="1960e-121">Ausführliche Informationen finden Sie unter [IPsec-Ausnahmen in lync Server 2013](lync-server-2013-ipsec-exceptions.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1960e-121">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="1960e-122">Gehen Sie wie folgt vor, um eine optimale Medienqualität zu gewährleisten:</span><span class="sxs-lookup"><span data-stu-id="1960e-122">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="1960e-123">Stellen Sie Ihre Netzwerk Links bereit, um den Durchsatz von 65 Kbit/s pro Audio-Stream und 500 KBit/s pro Videostream zu unterstützen, sofern diese während der Spitzennutzungszeiten aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="1960e-123">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods.</span></span> <span data-ttu-id="1960e-124">Eine bidirektionale Audio-oder Videositzung besteht aus zwei Streams.</span><span class="sxs-lookup"><span data-stu-id="1960e-124">A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="1960e-125">Um unerwartete Spitzen im Datenverkehr über dieser Ebene zu bewältigen und die Nutzung im Laufe der Zeit zu vermehren, können lync Server Media-Endpunkte sich an unterschiedliche Netzwerkbedingungen anpassen und Lasten des dreifachen Durchsatzes (siehe vorheriger Absatz) für Audio und Video unterstützen, während die akzeptable Qualität weiterhin erhalten bleibt.</span><span class="sxs-lookup"><span data-stu-id="1960e-125">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="1960e-126">Gehen Sie jedoch nicht davon aus, dass diese Anpassungsfähigkeit ein unter bereitgestelltes Netzwerk unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1960e-126">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="1960e-127">In einem unter bereitgestellten Netzwerk wird die Möglichkeit, dass die lync Server-Medien Endpunkte dynamisch mit unterschiedlichen Netzwerkbedingungen (beispielsweise temporärer hoher Paketverlust) umgehen können, verringert.</span><span class="sxs-lookup"><span data-stu-id="1960e-127">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="1960e-128">Bei Netzwerk Links, bei denen die Bereitstellung extrem kostspielig und schwierig ist, müssen Sie möglicherweise die Bereitstellung für ein geringeres Datenaufkommen in Frage stellen.</span><span class="sxs-lookup"><span data-stu-id="1960e-128">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="1960e-129">Lassen Sie in diesem Szenario die Elastizität der lync Server-Medien Endpunkte den Unterschied zwischen dem Verkehrsaufkommen und dem Höchstwert für den Datenverkehr absorbieren, und zwar zu den Kosten einer gewissen Verringerung der Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="1960e-129">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="1960e-130">Darüber hinaus gibt es eine Verringerung der Kopffreiheit, die sonst zur Aufnahme von plötzlichen Peaks im Verkehr zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="1960e-130">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="1960e-131">Für Links, die kurzfristig nicht richtig bereitgestellt werden können (beispielsweise eine Website mit sehr schlechten WAN-Links), sollten Sie das Deaktivieren von Video für bestimmte Benutzer in Frage stellen.</span><span class="sxs-lookup"><span data-stu-id="1960e-131">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="1960e-132">Stellen Sie Ihr Netzwerk bereit, um eine maximale End-to-End-Verzögerung (Latenz) von 150 Millisekunden (MS) unter Spitzenlast zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="1960e-132">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="1960e-133">Latenz ist die einzige Netzwerk Beeinträchtigung, die lync Server-Medienkomponenten nicht verringern können, und es ist wichtig, die Schwachstellen zu finden und zu eliminieren.</span><span class="sxs-lookup"><span data-stu-id="1960e-133">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="1960e-134">Berücksichtigen Sie bei Servern mit Antivirensoftware alle Server, auf denen lync Server ausgeführt wird, in der Ausnahmeliste, um eine optimale Leistung und Audioqualität zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="1960e-134">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="1960e-135">Netzwerkanforderungen für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="1960e-135">Conferencing Network Requirements</span></span>

<span data-ttu-id="1960e-136">Die Bandbreite, die zum Herunterladen von Konferenz Inhalten vom IIS-Server (Internet Information Services) verwendet wird, hängt von der Größe des hochgeladenen Inhalts ab.</span><span class="sxs-lookup"><span data-stu-id="1960e-136">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

<span data-ttu-id="1960e-137"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="1960e-137"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

