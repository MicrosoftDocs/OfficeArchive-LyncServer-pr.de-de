---
title: 'Lync Server 2013: Bearbeiten des Netzwerk Konfigurations Diagramms'
description: 'Lync Server 2013: Bearbeiten des Netzwerk Konfigurations Diagramms'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead2b0b47ec0cb0a98c33d7fff0a644f05f92c71
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437626"
---
# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a><span data-ttu-id="dfba4-103">Bearbeiten des Netzwerk Konfigurations Diagramms in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfba4-103">Editing the network configuration diagram in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="dfba4-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="dfba4-104">

<span> </span></span></span>

<span data-ttu-id="dfba4-105">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="dfba4-105">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="dfba4-106">Der größte Teil der Arbeit, die ein Designer im lync Server 2013, Planungs Tool, besteht darin, die Einträge für die IP-Adressen und vollqualifizierten Domänennamen (FQDNs) für die Einträge im Netzplandiagramm zu definieren.</span><span class="sxs-lookup"><span data-stu-id="dfba4-106">Most of the work that a designer does in the Lync Server 2013, Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="dfba4-107">Die Informationen, die auf dieser Seite eingegeben werden, werden in die Berichte und andere Informationen übernommen, die im Planungs Tool enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dfba4-107">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

<span data-ttu-id="dfba4-108">![Planungs Tool-Netzwerkdiagramm](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planungs Tool-Netzwerkdiagramm")</span><span class="sxs-lookup"><span data-stu-id="dfba4-108">![Planning Tool Network diagram](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planning Tool Network diagram")</span></span>

<span data-ttu-id="dfba4-109">Das Planungs Tool erstellt ein Netzwerkdiagramm mit Standardtext für IP-Adressen und FQDNs.</span><span class="sxs-lookup"><span data-stu-id="dfba4-109">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="dfba4-110">So bearbeiten Sie das Netzwerkdiagramm und geben Werte ein</span><span class="sxs-lookup"><span data-stu-id="dfba4-110">To edit the network diagram and input values:</span></span>

1.  <span data-ttu-id="dfba4-p102">Wählen Sie einen Abschnitt des Netzwerks aus, den Sie zuerst bearbeiten möchten. Machen Sie z. B. einen Doppelklick auf den Text **access1.contoso.net**. Geben Sie im nun geöffneten Dialogfeld den tatsächlichen FQDN für den Server „access1.contoso.net“ ein und ersetzen Sie die IP-Adresse 131.107.155.3 durch die tatsächliche IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="dfba4-p102">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2.  <span data-ttu-id="dfba4-114">Klicken Sie auf **OK**, um die Einträge zu speichern.</span><span class="sxs-lookup"><span data-stu-id="dfba4-114">Click **OK** to save the entries.</span></span>

3.  <span data-ttu-id="dfba4-115">Fahren Sie mit der Bearbeitung von IP-Adressen und FQDNs fort, und geben Sie virtuelle IP-Adressen für Hardwaregeräte zum Lastenausgleich oder Servereinträge für einen DNS-Lastenausgleich (Domain Name System) für Server in Pools an.</span><span class="sxs-lookup"><span data-stu-id="dfba4-115">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="dfba4-p103">Eine nützliche Funktion des Planungstools ist die, dass ein Bereich von IP-Adressen und Serverhostnamen inkrementell zugewiesen werden kann. Auf diese Weise muss der für den Entwurf verantwortliche Benutzer die Server in einem Pool nicht einzeln bearbeiten. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dfba4-p103">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1.  <span data-ttu-id="dfba4-p104">Machen Sie einen Doppelklick auf die Front-End-Server im Pool. Wählen Sie im nun geöffneten Dialogfeld die Option **Möchten Sie IP-Adressen und FQDN als Startpunkte für alle äquivalenten Server im Cluster verwenden?**.</span><span class="sxs-lookup"><span data-stu-id="dfba4-p104">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2.  <span data-ttu-id="dfba4-120">Beispielsweise lautet der Startwert für den ersten Server "fe0101.contoso.net", und die IP-Adresse ist auf "192.168.21.222" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dfba4-120">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3.  <span data-ttu-id="dfba4-121">Geben Sie in **FQDN des Front-End-Servers** den Wert **fe0.contoso.com** und in **IP-Adresse des Front-End-Servers** die Adresse **192.168.21.131** ein und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dfba4-121">Type **fe0.contoso.com** in **Front End Server FQDN**, type **192.168.21.131** in **Front End Server IP address**, and then click **OK**.</span></span>

4.  <span data-ttu-id="dfba4-122">Die Funktion zur automatischen inkrementellen Erhöhung aktualisiert alle Server im Pool von "fe01" bis "fe06" und alle IP-Adressen von 192.168.21.131 bis 136.</span><span class="sxs-lookup"><span data-stu-id="dfba4-122">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="dfba4-123">Nachdem Sie die Bearbeitung abgeschlossen haben, speichern Sie die Topologie, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="dfba4-123">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="dfba4-124">Wenn Sie das Planungs Tool Design speichern möchten, klicken Sie auf **Datei**, und klicken Sie dann auf **Topologie speichern** oder **Topologie speichern** unter.</span><span class="sxs-lookup"><span data-stu-id="dfba4-124">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="dfba4-125">Falls ein Dialogfeld **Planungstool speichern unter** angezeigt wird, geben Sie in **Dateiname** einen Namen für die Datei ein und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dfba4-125">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="dfba4-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfba4-126">See Also</span></span>


[<span data-ttu-id="dfba4-127">Bearbeiten des Entwurfs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfba4-127">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

<span data-ttu-id="dfba4-128"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="dfba4-128"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

