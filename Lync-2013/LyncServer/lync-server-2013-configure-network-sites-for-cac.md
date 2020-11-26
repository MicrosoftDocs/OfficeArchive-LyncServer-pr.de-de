---
title: 'Lync Server 2013: Konfigurieren von Netzwerk Websites für CAC'
description: 'Lync Server 2013: Konfigurieren von Netzwerk Websites für CAC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24adbbb1f5ee46618c685e072d519a338cb9b0af
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433850"
---
# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="87903-103">Konfigurieren von Netzwerk Websites für CAC in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87903-103">Configure network sites for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="87903-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="87903-104">

<span> </span></span></span>

<span data-ttu-id="87903-105">_**Letztes Änderungsdatum des Themas:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="87903-105">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="87903-106">Wenn Sie bereits Netzwerk Websites für E9-1-1 oder Media Bypass erstellt haben, können Sie die vorhandenen Netzwerk Websites so ändern, dass ein bandbreitenrichtlinienprofil mithilfe des Cmdlets " <STRONG>CsNetworkSite</STRONG> " angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="87903-106">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="87903-107">Ein Beispiel für das Ändern einer Netzwerk Website finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern einer Netzwerk Website in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="87903-107">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="87903-108">*Netzwerk Websites* sind die Büros oder Standorte innerhalb der einzelnen netzwerkregionen der Anruf Zulassungs Steuerung (CAC), E9-1-1 und Media Bypass-Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="87903-108">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="87903-109">Führen Sie die folgenden Verfahren aus, um Netzwerk Websites zu erstellen, die in der Beispiel Netzwerktopologie für CAC an Netzwerk Websites ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="87903-109">Use the following procedures to create network sites that align to network sites in the example network topology for CAC.</span></span> <span data-ttu-id="87903-110">In diesen Verfahren wird gezeigt, wie Netzwerk Websites erstellt und konfiguriert werden, die durch WAN-Bandbreite eingeschränkt sind, und daher Bandbreitenrichtlinien erforderlich sind, die den Echt Zeit Durchsatz von Audio-oder Videodaten einschränken.</span><span class="sxs-lookup"><span data-stu-id="87903-110">These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="87903-111">Im Beispiel für die CAC-Bereitstellung verfügt die Region Nordamerika über sechs Websites.</span><span class="sxs-lookup"><span data-stu-id="87903-111">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="87903-112">Drei dieser Websites sind durch die WAN-Bandbreite beschränkt: Reno, Portland und Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="87903-112">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="87903-113">Die anderen drei Websites, die *nicht* von der WAN-Bandbreite abhängig sind: New York, Chicago und Detroit.</span><span class="sxs-lookup"><span data-stu-id="87903-113">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="87903-114">Ein Beispiel zum Erstellen oder Ändern dieser anderen Netzwerk Websites finden Sie unter [erstellen oder Ändern einer Netzwerk Website in lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="87903-114">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="87903-115">Informationen zum Anzeigen der Beispiel Netzwerktopologie finden Sie unter [Beispiel: Sammeln Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="87903-115">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="87903-116">Im folgenden Verfahren wird die lync Server-Verwaltungsshell zum Erstellen einer Netzwerk Website verwendet.</span><span class="sxs-lookup"><span data-stu-id="87903-116">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="87903-117">Details zur Verwendung der lync Server-Systemsteuerung zum Erstellen einer Netzwerk Website finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern einer Netzwerk Website in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="87903-117">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="87903-118">So erstellen Sie Netzwerk Websites für die Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="87903-118">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="87903-119">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="87903-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="87903-120">Führen Sie das Cmdlet **New-CsNetworkSite** aus, um Netzwerk Websites zu erstellen und auf jede Website ein entsprechendes bandbreitenrichtlinienprofil anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="87903-120">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="87903-121">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="87903-121">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="87903-122">Um das Erstellen von Netzwerk Websites für die gesamte Beispieltopologie abzuschließen, wiederholen Sie Schritt 2 für die Netzwerk Websites mit Bandbreiteneinschränkungen in den Regionen EMEA und APAC.</span><span class="sxs-lookup"><span data-stu-id="87903-122">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

<span data-ttu-id="87903-123"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="87903-123"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

