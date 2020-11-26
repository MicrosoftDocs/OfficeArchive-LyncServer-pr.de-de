---
title: 'Lync Server 2013: Einrichten von Netzwerkschnittstellen für Edgeserver'
description: 'Lync Server 2013: Einrichten von Netzwerkschnittstellen für Edgeserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 576ca8670a34be022e3df0a699edaf0df10f5b70
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49441739"
---
# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="823a2-103">Einrichten von Netzwerkschnittstellen für Edgeserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="823a2-103">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="823a2-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="823a2-104">

<span> </span></span></span>

<span data-ttu-id="823a2-105">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="823a2-105">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="823a2-106">Bei jedem Edgeserver handelt es sich um einen mehr vernetzten Computer mit externen und internen Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="823a2-106">Each Edge Server is a multihomed computer with external and internal facing interfaces.</span></span> <span data-ttu-id="823a2-107">Die DNS-Einstellungen (Domain Name System) des Adapters hängen davon ab, ob im Umkreisnetzwerk DNS-Server vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="823a2-107">The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network.</span></span> <span data-ttu-id="823a2-108">Wenn DNS-Server im Umkreis vorhanden sind, müssen Sie über eine Zone verfügen, die mindestens einen DNS-a-Eintrag für den Server oder Pool des nächsten Hop enthält (also entweder einen Director oder einen benannten Front-End-Pool), und für externe Abfragen, die Sie auf andere öffentliche DNS-Server verweisen.</span><span class="sxs-lookup"><span data-stu-id="823a2-108">If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers.</span></span> <span data-ttu-id="823a2-109">Wenn keine DNS-Server im Umkreis vorhanden sind, verwenden die Edgeserver externe DNS-Server zum Auflösen von Internet Namen suchen, und jeder Edgeserver verwendet einen Host, um die Servernamen für den nächsten Hop in IP-Adressen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="823a2-109">If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" /><span data-ttu-id="823a2-111">Sicherheitshinweis:</span><span class="sxs-lookup"><span data-stu-id="823a2-111">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="823a2-112">Aus Sicherheitsgründen empfehlen wir, dass Ihre Edgeserver nicht auf einen DNS-Server zugreifen, der sich im internen Netzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="823a2-112">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="823a2-113">So konfigurieren Sie Schnittstellen mit DNS-Servern im Umkreisnetzwerk</span><span class="sxs-lookup"><span data-stu-id="823a2-113">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="823a2-114">Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne Schnittstelle und einen für die extern anliegende Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="823a2-114">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="823a2-115">Ein Routing vom internen Subnetz zum externen Subnetz (und umgekehrt) darf nicht möglich sein.</span><span class="sxs-lookup"><span data-stu-id="823a2-115">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="823a2-116">Konfigurieren Sie auf der externen Schnittstelle drei statische IP-Adressen im Subnetz des externen Umkreisnetzwerks (auch bekannt als DMZ, demilitarisierte Zone und geschirmtes Subnetz), und zeigen Sie das Standardgateway auf die interne Schnittstelle der externen Firewall.</span><span class="sxs-lookup"><span data-stu-id="823a2-116">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="823a2-117">Konfigurieren Sie die Adapter-DNS-Einstellungen so, dass Sie auf ein paar von Umkreis-DNS-Servern verweisen.</span><span class="sxs-lookup"><span data-stu-id="823a2-117">Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="823a2-118">Es ist möglich, nur eine IP-Adresse für diese Schnittstelle zu verwenden, aber dazu müssen Sie die Portzuweisungen auf nicht Standardwerte ändern.</span><span class="sxs-lookup"><span data-stu-id="823a2-118">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="823a2-119">Sie bestimmen dies, wenn Sie die Topologie im Topologie-Generator erstellen.</span><span class="sxs-lookup"><span data-stu-id="823a2-119">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="823a2-120">Konfigurieren Sie auf der internen Schnittstelleeine statische IP-Adresse im Subnetz des internen Umkreisnetzwerks, und legen Sie kein Standardgateway an.</span><span class="sxs-lookup"><span data-stu-id="823a2-120">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="823a2-121">Konfigurieren Sie die Adapter-DNS-Einstellungen so, dass Sie auf mindestens einen DNS-Server verweisen, vorzugsweise auf ein paar von Umkreis-DNS-Servern.</span><span class="sxs-lookup"><span data-stu-id="823a2-121">Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="823a2-122">Erstellen Sie persistente statische Routen auf der internen Schnittstelle für alle internen Netzwerke, auf denen sich Clients, lync Server 2013 und Exchange Unified Messaging-Server befinden.</span><span class="sxs-lookup"><span data-stu-id="823a2-122">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="823a2-123">So konfigurieren Sie Schnittstellen ohne DNS-Server im Umkreisnetzwerk</span><span class="sxs-lookup"><span data-stu-id="823a2-123">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="823a2-124">Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne Schnittstelle und einen für die extern anliegende Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="823a2-124">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="823a2-125">Ein Routing vom internen Subnetz zum externen Subnetz (und umgekehrt) darf nicht möglich sein.</span><span class="sxs-lookup"><span data-stu-id="823a2-125">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="823a2-126">Konfigurieren Sie auf der externen Schnittstelle drei statische IP-Adressen im Subnetz des externen Umkreisnetzwerks.</span><span class="sxs-lookup"><span data-stu-id="823a2-126">On the external interface, configure three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="823a2-127">Darüber hinaus konfigurieren Sie das Standardgateway auf der externen Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="823a2-127">You also configure the default gateway on the external interface.</span></span> <span data-ttu-id="823a2-128">Definieren Sie beispielsweise den mit dem Internet versehenen Router oder die externe Firewall als Standardgateway.</span><span class="sxs-lookup"><span data-stu-id="823a2-128">For example, define the Internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="823a2-129">Konfigurieren Sie die DNS-Einstellungen so, dass Sie auf einen DNS-Server verweisen, vorzugsweise auf ein paar externer DNS-Server.</span><span class="sxs-lookup"><span data-stu-id="823a2-129">Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="823a2-130">Es ist möglich, aber nicht empfehlenswert, nur eine IP-Adresse für die externe Schnittstelle zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="823a2-130">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="823a2-131">Damit dies funktioniert, müssen Sie die Portzuweisungen auf nicht standardmäßige Werte und außerhalb des standardmäßigen Port 443 ändern, der in der Regel für die Clientkommunikation "Firewall-freundlich" ist.</span><span class="sxs-lookup"><span data-stu-id="823a2-131">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="823a2-132">Sie bestimmen die IP-Adresseneinstellung und die Porteinstellungen, wenn Sie die Topologie im Topologie-Generator erstellen.</span><span class="sxs-lookup"><span data-stu-id="823a2-132">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="823a2-133">Konfigurieren Sie auf der internen Schnittstelleeine statische IP-Adresse im Subnetz des internen Umkreisnetzwerks, und legen Sie kein Standardgateway an.</span><span class="sxs-lookup"><span data-stu-id="823a2-133">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="823a2-134">Lassen Sie die Adapter-DNS-Einstellungen leer.</span><span class="sxs-lookup"><span data-stu-id="823a2-134">Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="823a2-135">Erstellen Sie persistente statische Routen auf der internen Schnittstelle für alle internen Netzwerke, in denen lync-Clients oder-Server mit lync Server 2013 befinden.</span><span class="sxs-lookup"><span data-stu-id="823a2-135">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="823a2-136">Bearbeiten Sie die Hostdatei auf jedem Edgeserver, um einen Eintrag für den nächsten Hop-Server oder die virtuelle IP (VIP) zu enthalten (der Datensatz ist der Director, Standard Edition-Server oder ein Front-End-Pool, der im Topologie-Generator als Adresse des Edge-Servers für den nächsten Hop konfiguriert wurde).</span><span class="sxs-lookup"><span data-stu-id="823a2-136">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="823a2-137">Wenn Sie den DNS-Lastenausgleich verwenden, schließen Sie eine Zeile für jedes Mitglied des nächsten Hop-Pools ein.</span><span class="sxs-lookup"><span data-stu-id="823a2-137">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

<span data-ttu-id="823a2-138"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="823a2-138"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

