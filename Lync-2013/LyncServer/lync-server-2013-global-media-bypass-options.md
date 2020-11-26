---
title: 'Lync Server 2013: globale Medien Umgehungs Optionen'
description: 'Lync Server 2013: globale Medien Umgehungs Optionen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e69a776c13171d74666a202108fa4b5c72e224d0
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427908"
---
# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="a1c0c-103">Globale Medien Umgehungs Optionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1c0c-103">Global media bypass options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="a1c0c-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="a1c0c-104">

<span> </span></span></span>

<span data-ttu-id="a1c0c-105">_**Letztes Änderungsdatum des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="a1c0c-105">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a1c0c-106">In diesem Thema wird davon ausgegangen, dass Sie die medienumgehung für alle Trunks für einen Peer (ein öffentliches Switched Telephone Network (PSTN)-Gateway, eine IP-Telefonanlage oder einen Session Border Controller (SBC) bei einem Internet-Telefoniedienstanbieter) für eine bestimmte Website oder einen bestimmten Dienst konfiguriert haben, für die Medien den Vermittlungs Server umgehen sollen.</span><span class="sxs-lookup"><span data-stu-id="a1c0c-106">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="a1c0c-p101">Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zugeordnet sind, müssen Sie die Medienumgehung auch global aktivieren. Über globale Einstellungen für die Medienumgehung können Sie entweder angeben, dass die Medienumgehung auf Anrufe über das Telefonfestnetz immer angewendet wird oder dass die Medienumgehung auf der Grundlage von Zuordnungen von Subnetzen zu Netzwerkstandorten und Netzwerkregionen angewendet wird – ähnlich wie bei der Anrufsteuerung, einer anderen erweiterten VoIP-Funktion. Wenn sowohl die Medienumgehung als auch die Anrufsteuerung aktiviert wurden, werden die Informationen zu Netzwerkregionen, Netzwerkstandorten und Subnetzen, die für die Anrufsteuerung konfiguriert wurden, automatisch für Entscheidungen zur Verwendung der Medienumgehung herangezogen. Dies bedeutet, dass Sie die Medienumgehung nicht auf alle Anrufe über das Telefonfestnetz anwenden können, wenn die Anrufsteuerung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a1c0c-p101">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally. Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature. When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass. This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="a1c0c-111">In diesem Thema wird beschrieben, wie Sie die lync Server-Systemsteuerung und die lync Server-Verwaltungsshell zusammen verwenden, um globale medienumgehungseinstellungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a1c0c-111">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a1c0c-112">Wenn Sie diese Schritte zum Konfigurieren der Medienumgehung verwenden, wird von einer guten Konnektivität zwischen Clients und dem Vermittlungsserverpeer ausgegangen (z. B. einem PSTN-Gateway, einer IP-Nebenstellenanlage oder einem SBC beim SIP-Trunkinganbieter).</span><span class="sxs-lookup"><span data-stu-id="a1c0c-112">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="a1c0c-113">Wenn für die Verbindung Bandbreiteneinschränkungen gelten, kann die Medienumgehung nicht auf den Anruf angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a1c0c-113">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="a1c0c-114">Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs.</span><span class="sxs-lookup"><span data-stu-id="a1c0c-114">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="a1c0c-115">Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="a1c0c-115">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="a1c0c-116">Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program – lync Server unter aufgeführt sind <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="a1c0c-116">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="a1c0c-117">Nächste Schritte: auswählen globaler medienumgehungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="a1c0c-117">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="a1c0c-118">Nachdem Sie die medienumgehung für alle trunk-Verbindungen zu einem Peer für bestimmte Websites oder Dienste aktiviert haben, verwenden Sie den folgenden Inhalt:</span><span class="sxs-lookup"><span data-stu-id="a1c0c-118">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="a1c0c-119">Aktivieren Sie die medienumgehung immer, wie unter [Konfigurieren der medienumgehung in lync Server 2013 beschrieben, um den Vermittlungsserver immer zu umgehen](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="a1c0c-119">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="a1c0c-120">Oder konfigurieren Sie die medienumgehung für die Verwendung von Website-und Regionsinformationen, wie unter [Konfigurieren der globalen Einstellungen für medienumgehung in lync Server 2013 beschrieben, um Website-und Regionsinformationen zu verwenden](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span><span class="sxs-lookup"><span data-stu-id="a1c0c-120">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1c0c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1c0c-121">See Also</span></span>


[<span data-ttu-id="a1c0c-122">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1c0c-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="a1c0c-123">Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1c0c-123">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="a1c0c-124">Konfigurieren der Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1c0c-124">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="a1c0c-125">Medienumgehung und Vermittlungsserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1c0c-125">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

<span data-ttu-id="a1c0c-126"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="a1c0c-126"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

