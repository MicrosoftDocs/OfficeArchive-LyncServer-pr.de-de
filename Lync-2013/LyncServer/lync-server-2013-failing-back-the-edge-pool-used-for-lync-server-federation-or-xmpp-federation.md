---
title: Ausführen eines Failbacks für den Edgepool, der für den Lync Server- oder XMPP-Partnerverbund verwendet wird
description: Fehler beim Zurücksetzen des Edge-Pools, der für lync Server Federation oder XMPP Federation verwendet wird.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 137910d71de1d6177356e0b7bacbd6d17022d71d
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428300"
---
# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="e2494-103">Ausführen eines Failbacks für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e2494-103">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e2494-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e2494-104">

<span> </span></span></span>

<span data-ttu-id="e2494-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e2494-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e2494-106">Nachdem ein ausgefallener Edge-Pool, der zum Hosten der Föderation verwendet wurde, wieder online geschaltet wurde, verwenden Sie dieses Verfahren zum Zurücksetzen der lync Server-Föderations Route und/oder der XMPP-Föderations Route, um diesen wiederhergestellten Edge-Pool erneut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2494-106">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="e2494-107">Fehler beim Zurücksetzen des Verbund zu einem wiederhergestellten Edge-Pool</span><span class="sxs-lookup"><span data-stu-id="e2494-107">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="e2494-108">Starten Sie in dem jetzt wieder verfügbaren Edge-Pool die Edge-Dienste.</span><span class="sxs-lookup"><span data-stu-id="e2494-108">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="e2494-109">Gehen Sie wie folgt vor, wenn Sie die lync Server-Föderations Route zur Verwendung des wiederhergestellten Edge-Servers zurücksetzen möchten:</span><span class="sxs-lookup"><span data-stu-id="e2494-109">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="e2494-110">Öffnen Sie auf einem Front-End-Server den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="e2494-110">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="e2494-111">Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder den Edgeserver-Pool, der derzeit für den Verbund konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e2494-111">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="e2494-112">Wählen Sie **Eigenschaften bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="e2494-112">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="e2494-113">Deaktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="e2494-113">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="e2494-114">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2494-114">Click **OK**.</span></span>
    
      - <span data-ttu-id="e2494-115">Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den ursprünglichen Edge-Server oder den Edgeserver-Pool, den Sie erneut für den Verbund verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e2494-115">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="e2494-116">Wählen Sie **Eigenschaften bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="e2494-116">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="e2494-117">Wählen Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)** aus.</span><span class="sxs-lookup"><span data-stu-id="e2494-117">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="e2494-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2494-118">Click **OK**.</span></span>
    
      - <span data-ttu-id="e2494-119">Klicken Sie auf **Aktion**, wählen Sie **Topologie** aus, und wählen Sie **veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="e2494-119">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="e2494-120">Wenn Sie dazu aufgefordert werden, **die Topologie zu veröffentlichen**, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="e2494-120">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="e2494-121">Wenn der Veröffentlichungsvorgang abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e2494-121">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="e2494-122">Öffnen Sie auf dem Edgeserver den lync Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="e2494-122">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="e2494-123">Klicken Sie auf **lync Server System installieren oder aktualisieren** und dann auf **lync Server-Komponenten einrichten oder entfernen**.</span><span class="sxs-lookup"><span data-stu-id="e2494-123">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="e2494-124">Klicken Sie **erneut auf Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e2494-124">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="e2494-125">Klicken Sie bei der Installation von lync Server-Komponenten auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="e2494-125">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="e2494-126">Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e2494-126">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="e2494-127">Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e2494-127">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="e2494-128">Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e2494-128">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="e2494-129">Gehen Sie wie folgt vor, wenn Sie die XMPP-Föderations Route zur Verwendung des wiederhergestellten Edge-Servers zurücksetzen möchten:</span><span class="sxs-lookup"><span data-stu-id="e2494-129">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="e2494-130">Führen Sie das folgende Cmdlet aus, um die XMPP-Föderations Route an den Edge-Pool zu verweisen, der nun XMPP-Föderation hostet (in diesem Beispiel EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="e2494-130">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="e2494-131">In diesem Beispiel ist site1 die Website, die den Edge-Pool enthält, auf dem nun die XMPP-Föderations Route gehostet wird, und EdgeServer1.contoso.com ist der FQDN eines Edgeserver in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="e2494-131">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="e2494-132">Wenn Sie noch keinen DNS-SRV-Eintrag für die XMPP-Föderation haben, der in den Edge-Pool aufgelöst wird, der nun XMPP-Föderation hostet, müssen Sie ihn wie im folgenden Beispiel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e2494-132">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="e2494-133">Dieser SRV-Eintrag muss einen Portwert von 5269 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e2494-133">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="e2494-134">Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für XMPP-Föderation, um auf EdgeServer2.contoso.com zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="e2494-134">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="e2494-135">Überprüfen Sie, ob der Edge-Pool, auf dem nun der XMPP-Verbund gehostet wird, Port 5269 extern geöffnet hat.</span><span class="sxs-lookup"><span data-stu-id="e2494-135">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="e2494-136">Wenn die Front-End-Pools weiterhin auf der Website mit dem fehlerhaften Edge-Pool ausgeführt wurden und wiederhergestellt wurden, sollten Sie den Webkonferenzdienst und den A/V-Konferenzdienst in diesen Front-End-Pools aktualisieren, um die Edge-Pools auf der lokalen Website erneut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2494-136">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="e2494-137">Weitere Informationen finden Sie unter [Ändern des Edge-Pools, der einem Front-End-Pool in lync Server 2013 zugeordnet](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)ist.</span><span class="sxs-lookup"><span data-stu-id="e2494-137">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="e2494-138">Wenn der Front-End-Pool am gleichen Standort wie der fehlerhafte Edge-Pool ebenfalls fehlgeschlagen ist, können Sie jetzt Invoke – CsPoolFailback verwenden, um den Front-End-Pool zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="e2494-138">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e2494-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2494-139">See Also</span></span>


[<span data-ttu-id="e2494-140">Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e2494-140">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="e2494-141">Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den XMPP-Partnerverbund verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e2494-141">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="e2494-142">Notfallwiederherstellung für Edgeserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2494-142">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

<span data-ttu-id="e2494-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e2494-143"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

