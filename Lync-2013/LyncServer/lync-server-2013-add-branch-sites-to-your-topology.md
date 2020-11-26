---
title: 'Lync Server 2013: Hinzufügen von Zweigstellenstandorten zur Topologie'
description: 'Lync Server 2013: Fügen Sie Ihrer Topologie Verzweigungs Websites hinzu.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c7a12373c6a60a2902ee451d39c99f756e2b2f5
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49439366"
---
# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="6282b-103">Hinzufügen von Zweigstellenstandorten zur Topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6282b-103">Add branch sites to your topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="6282b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="6282b-104">

<span> </span></span></span>

<span data-ttu-id="6282b-105">_**Letztes Änderungsdatum des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6282b-105">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6282b-106">Verzweigungs Websites stellen physische Zweigstellen dar, die über eine WAN-Verbindung mit ihren Hauptniederlassungen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="6282b-106">Branch sites represent physical branch offices that are connected to your main offices over a WAN link.</span></span> <span data-ttu-id="6282b-107">Wenn Sie Ihrer lync-Topologie eine Verzweigungs Website hinzufügen möchten, führen Sie diese Schritte am zentralen Standort aus.</span><span class="sxs-lookup"><span data-stu-id="6282b-107">To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="6282b-108">So fügen Sie Ihrer Topologie Verzweigungs Websites hinzu</span><span class="sxs-lookup"><span data-stu-id="6282b-108">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="6282b-109">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="6282b-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="6282b-110">Erweitern Sie in der Konsolenstruktur die zentrale Website, klicken Sie mit der rechten Maustaste auf **Verzweigungs Websites**, und klicken Sie dann auf **neue Verzweigungs Website**.</span><span class="sxs-lookup"><span data-stu-id="6282b-110">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="6282b-111">Klicken Sie im Dialogfeld **neue Verzweigungs Website definieren** auf **Name**, und geben Sie dann den Namen der Verzweigungs Website ein.</span><span class="sxs-lookup"><span data-stu-id="6282b-111">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="6282b-112">Optional Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für die Verzweigungs Website ein.</span><span class="sxs-lookup"><span data-stu-id="6282b-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="6282b-113">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6282b-113">Click **Next**.</span></span>

6.  <span data-ttu-id="6282b-114">Optional Führen Sie im nächsten Dialogfeld **neue Verzweigungs Website definieren** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6282b-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="6282b-115">Klicken Sie auf **Stadt**, und geben Sie dann den Namen des Orts ein, in dem sich die Zweigstelle befindet.</span><span class="sxs-lookup"><span data-stu-id="6282b-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="6282b-116">Klicken Sie auf **Bundesland/Region**, und geben Sie dann den Namen des Bundeslands oder der Region ein, in dem sich die Verzweigungs Website befindet.</span><span class="sxs-lookup"><span data-stu-id="6282b-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="6282b-117">Klicken Sie auf **Landesvorwahl**, und geben Sie dann den zweistelligen anrufcode für das Land/die Region ein, in dem sich die Zweigstelle befindet.</span><span class="sxs-lookup"><span data-stu-id="6282b-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="6282b-118">Klicken Sie auf **weiter**, und führen Sie dann eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6282b-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="6282b-119">Wenn Sie eine Survivable Branch-Appliance oder einen Server an dieser Website verwenden, stellen Sie sicher, dass das Kontrollkästchen **den neuen Überlebenden Assistenten beim Schließen des Assistenten öffnen** aktiviert ist, klicken Sie auf **Fertig stellen**, und folgen Sie dann den Anweisungen des Assistenten, der geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="6282b-119">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="6282b-120">Informationen zu Assistenten Elementen finden Sie unter Definieren einer überlebensfähigen [Verzweigungs Einheit oder eines Servers in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="6282b-120">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="6282b-121">Wenn Sie keine Survivable Branch-Appliance oder einen Server an dieser Website verwenden, deaktivieren Sie das Kontrollkästchen **neuen Überlebenden Assistenten öffnen, wenn dieser Assistent geschlossen** wird, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="6282b-121">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="6282b-122">Wiederholen Sie die vorherigen Schritte für jede Verzweigungs Website, die Sie zur Topologie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="6282b-122">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="6282b-123">**Nächster Schritt:**</span><span class="sxs-lookup"><span data-stu-id="6282b-123">**Next step:**</span></span>

<span data-ttu-id="6282b-124">Für Survivable Branch-Appliances oder-Server: Definieren einer überlebensfähigen [Branch-Appliance oder eines Survivable-Servers in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="6282b-124">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="6282b-125">Für nicht belastbare PSTN-Konnektivität: [Definieren eines PSTN-Gateways für eine Zweigstelle in lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)oder [Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="6282b-125">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

<span data-ttu-id="6282b-126"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="6282b-126"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

