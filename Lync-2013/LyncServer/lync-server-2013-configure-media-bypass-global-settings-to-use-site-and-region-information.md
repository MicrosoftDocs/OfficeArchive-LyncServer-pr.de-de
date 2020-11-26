---
title: Konfigurieren der globalen Einstellungen für die Medienumgehung zur Verwendung von Standort- und Regionsinformationen
description: Konfigurieren Sie die globalen Einstellungen für medienumgehung, um Website-und Regionsinformationen zu verwenden.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a65dcec966030262d6d0fb5530b94f2411003c7a
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433962"
---
# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="7709b-103">Configure media bypass global settings in Lync Server 2013 to use site and region information</span><span class="sxs-lookup"><span data-stu-id="7709b-103">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="7709b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="7709b-104">

<span> </span></span></span>

<span data-ttu-id="7709b-105">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7709b-105">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7709b-106">In diesem Thema wird davon ausgegangen, dass Sie die medienumgehung für alle trunk Verbindungen vom Vermittlungs Server zu einem Peer (einem PSTN-Gateway (Public Switched Telephone Network), einer IP-PBX-Anlage oder einem Session Border Controller (SBC) bei einem Internet-Telefoniedienstanbieter (ITSP) für eine bestimmte Website oder einen bestimmten Dienst, für den Medien den Vermittlungs Server umgehen sollen,</span><span class="sxs-lookup"><span data-stu-id="7709b-106">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="7709b-107">In diesem Thema wird auch davon ausgegangen, dass Sie alle zentralen Websites und Zweigstellen im Topologie-Generator auf eine Weise definiert haben, die dem Netzwerkbereich, der Netzwerk Website und der Subnet-Konfiguration entspricht, die Sie gemäß den Schritten unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern eines Netzwerkbereichs in lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern einer Netzwerk Website in lync Server 2013</A>und Verknüpfen eines Subnetzes <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">mit einer Netzwerk 2013 Website</A></span><span class="sxs-lookup"><span data-stu-id="7709b-107">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="7709b-108">Wenn Sie nicht übereinstimmen, ist die medienumgehung nicht erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="7709b-108">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="7709b-109">Zusätzlich zum Aktivieren der medienumgehung für einzelne trunk-Verbindungen, die einem Peer zugeordnet sind, müssen Sie auch die globalen Einstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7709b-109">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings.</span></span> <span data-ttu-id="7709b-110">Wenn Sie die Schritte in diesem Thema zum Konfigurieren globaler Einstellungen für die medienumgehung verwenden, wird davon ausgegangen, dass eine oder beide der folgenden Situationen Ihre Konfiguration beeinflussen:</span><span class="sxs-lookup"><span data-stu-id="7709b-110">If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="7709b-111">Sie verfügen *nicht* über eine gute Verbindung zwischen lync Server-Endpunkten und allen Peers, für die Sie die medienumgehung für die trunk-Verbindung konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="7709b-111">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="7709b-112">Die Anrufannahme Steuerung (CAC) für die Bandbreitenverwaltung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7709b-112">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7709b-113">Details zu den Überlegungen für die Anrufsteuerung und die medienumgehung finden Sie im Abschnitt "Anrufsteuerung für PSTN-Verbindungen" im Abschnitt " <A href="lync-server-2013-media-bypass-and-mediation-server.md">medienumgehung und Vermittlungsserver" in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7709b-113">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="7709b-p103">Die Informationen zu Netzwerkregionen und Netzwerkstandorten werden sowohl für die Anrufsteuerung als auch für die Medienumgehung verwendet, wenn beide der erweiterten Enterprise-VoIP-Funktionen aktiviert sind. Wenn Sie daher die Anrufsteuerung bereits konfiguriert haben, müssen Sie das folgende Verfahren zum Bearbeiten von Standort- und Regioneninformationen nicht speziell für die Medienumgehung ausführen. Führen Sie die Schritte des folgenden Verfahrens aus, wenn Sie noch keine Netzwerkregionen und Standorte für die Anrufsteuerung konfiguriert haben und die Einstellungen für die Medienumgehung ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="7709b-p103">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="7709b-117">Oder führen Sie die folgenden Schritte aus, wenn Sie Website-und Regionsinformationen verwenden möchten, um die Umgehungs Entscheidung zu treffen, aber nicht die Möglichkeit haben, die Anrufsteuerung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7709b-117">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="7709b-118">In diesem Fall müssen die Links zur Bandbreitenbeschränkung weiterhin über Netzwerk-standortübergreifende Richtlinien dargestellt werden, wie unter Erstellen von Netzwerk-standortübergreifenden [Richtlinien in lync Server 2013](lync-server-2013-create-network-intersite-policies.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7709b-118">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="7709b-119">In diesem Fall sind die tatsächlichen Bandbreiteneinschränkungen nicht so wichtig, da die Anrufsteuerung nicht aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="7709b-119">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="7709b-120">Stattdessen werden diese Links zum Partitionieren von Subnetzen verwendet, um diejenigen anzugeben, die keine Bandbreitenbeschränkungen aufweisen und daher die medienumgehung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7709b-120">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="7709b-121">Beachten Sie, dass dies auch der Fall ist, wenn die Anrufsteuerung und die medienumgehung aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7709b-121">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="7709b-122">Damit die Umgehungsfunktion ordnungsgemäß funktioniert, muss die Konsistenz zwischen einer Website, wie Sie im Topologie-Generator definiert ist, und der Definition beim Konfigurieren von netzwerkregionen und Netzwerk Websites bestehen.</span><span class="sxs-lookup"><span data-stu-id="7709b-122">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="7709b-123">Wenn Sie beispielsweise über eine Verzweigungs Website verfügen, die Sie im Topologie-Generator als nur ein PSTN-Gateway bereitgestellt definiert haben, muss diese Verzweigungs Website mit einer Enterprise-VoIP-Richtlinie konfiguriert werden, die es den Benutzern der Zweigstelle ermöglicht, ihre PSTN-Anrufe über das PSTN-Gateway an der Zweigstelle zu leiten.</span><span class="sxs-lookup"><span data-stu-id="7709b-123">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="7709b-124">So konfigurieren Sie Informationen zu Standorten und Regionen für die Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="7709b-124">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="7709b-125">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7709b-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7709b-126">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7709b-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="7709b-127">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="7709b-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="7709b-128">Doppelklicken Sie in der Tabelle auf die Konfiguration **Global**.</span><span class="sxs-lookup"><span data-stu-id="7709b-128">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="7709b-129">Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="7709b-129">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="7709b-130">Klicken Sie auf **Standort- und Regionskonfiguration verwenden**.</span><span class="sxs-lookup"><span data-stu-id="7709b-130">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="7709b-131">Falls erforderlich, aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="7709b-131">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7709b-p107">Aktivieren Sie dieses Kontrollkästchen nur, wenn Sie über einen oder mehrere große Standorte ohne Bandbreiteneinschränkungen verfügen (z. B. ein großer Hauptstandort), die einer bestimmten Region zugeordnet sind, und Sie außerdem über einige Zweigniederlassungen mit Bandbreiteneinschränkungen verfügen, die derselben Region zugeordnet sind. Wenn Sie die Umgehung für nicht zugeordnete Standorte aktivieren, wird die Konfiguration optimiert, da Sie nur die den Zweigniederlassungen zugeordneten Subnetze angeben, statt sämtliche, allen Standorten zugeordnete Subnetze angeben zu müssen. Es wird empfohlen, dieses Kontrollkästchen nicht zu aktivieren, wenn die Anrufsteuerung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="7709b-p107">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="7709b-135">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7709b-135">Click **Commit**.</span></span>

<span data-ttu-id="7709b-136">Fügen Sie als nächstes Subnetze zur Netzwerk Website hinzu, wie in [Zuordnen von Subnetzen mit Netzwerk Websites für die medienumgehung in lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7709b-136">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="7709b-137">(Die eigentlichen Verfahren zum Verknüpfen von Subnetzen mit Netzwerkstandorten werden unter [Zuordnen eines Subnetzes zu einer Netzwerk Website in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)beschrieben.) Nachdem Sie alle Subnetze mit Netzwerk Websites verknüpft haben, ist die Medien Umgehungs Bereitstellung abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7709b-137">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="7709b-138">Wenn Sie noch keine Netzwerkregionen und Netzwerkstandorte erstellt haben, müssen Sie dies nachholen, bevor Sie mit der Bereitstellung der Medienumgehung fortfahren können.</span><span class="sxs-lookup"><span data-stu-id="7709b-138">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="7709b-139">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern eines Netzwerkbereichs in lync Server 2013</A> und <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern einer Netzwerk Website in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7709b-139">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7709b-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7709b-140">See Also</span></span>


[<span data-ttu-id="7709b-141">Zuordnen von Subnetzen zu Netzwerk Websites zur medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7709b-141">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

<span data-ttu-id="7709b-142"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="7709b-142"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

