---
title: 'Lync Server 2013: Verwalten von Watcher-Knoten'
description: 'Lync Server 2013: Verwalten von Watcher-Knoten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1795b09bbca73d8157cf796ceeaaeafb9cc2ebc5
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425829"
---
# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="9721b-103">Verwalten von Watcher-Knoten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9721b-103">Managing watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="9721b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="9721b-104">

<span> </span></span></span>

<span data-ttu-id="9721b-105">_**Letztes Änderungsdatum des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="9721b-105">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="9721b-106">Zusätzlich zum Ändern der synthetischen Transaktionen, die auf einem Watcher-Knoten ausgeführt werden, können Administratoren auch das Cmdlet " **Satz-CsWatcherNodeConfiguration** " verwenden, um zwei weitere wichtige Aufgaben auszuführen: Aktivieren und Deaktivieren des Watcher-Knotens und Konfigurieren des Watcher-Knotens zum Verwenden interner URLs oder externer URLs, wenn die Tests ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9721b-106">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="9721b-107">In der Standardeinstellung führen Watcher-Knoten in regelmäßigen Abständen alle für sie aktivierten synthetischen Transaktionen aus.</span><span class="sxs-lookup"><span data-stu-id="9721b-107">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="9721b-108">Manchmal müssen Sie diese Transaktionen aber möglicherweise anhalten.</span><span class="sxs-lookup"><span data-stu-id="9721b-108">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="9721b-109">Wenn der Watcher-Knoten zum Beispiel vorübergehend vom Netzwerk getrennt ist, liegt kein Grund vor, dass die synthetischen Transaktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9721b-109">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="9721b-110">Ohne Netzwerkkonnektivität sind diese Transaktionen garantiert fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="9721b-110">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="9721b-111">Wenn Sie einen Watcher-Knoten vorübergehend deaktivieren möchten, führen Sie in der lync Server-Verwaltungsshell einen ähnlichen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="9721b-111">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="9721b-112">Mit diesem Befehl wird die Ausführung von synthetischen Transaktionen auf dem Watcher-Knoten ATL-Watcher-001.litwareinc.com deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9721b-112">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com.</span></span> <span data-ttu-id="9721b-113">Wenn die synthetischen Transaktionen wieder aufgenommen werden sollen, setzen Sie die Eigenschaft „Enabled“ wieder zurück auf „True“ ($True):</span><span class="sxs-lookup"><span data-stu-id="9721b-113">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="9721b-p103">Mithilfe der Eigenschaft „Enabled“ können Watcher-Knoten ein- und ausgeschaltet werden. Wenn Sie einen Watcher-Knoten dauerhaft löschen möchten, verwenden Sie das <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>-Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="9721b-p103">The Enabled property can be used to turn watcher nodes on or off. If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="9721b-116">Remove-CsWatcherNodeConfiguration – Identität "ATL-Watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="9721b-116">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="9721b-117">Dieser Befehl entfernt alle Überwachungsknoten-Konfigurationseinstellungen vom angegebenen Computer, wodurch verhindert wird, dass der Computer synthetische Transaktionen automatisch ausführt.</span><span class="sxs-lookup"><span data-stu-id="9721b-117">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="9721b-118">Der Befehl wird jedoch nicht die System Center-Agentendateien oder die lync Server 2013-Systemdateien deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="9721b-118">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="9721b-119">Standardmäßig verwenden Watcher-Knoten die externen URLs einer Organisation, wenn Sie Ihre Tests durchführen.</span><span class="sxs-lookup"><span data-stu-id="9721b-119">By default, watcher nodes use an organization's external URLs when conducting their tests.</span></span> <span data-ttu-id="9721b-120">Watcher-Knoten können jedoch auch so konfiguriert werden, dass Sie die internen URLs der Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="9721b-120">However, watcher nodes can also be configured to use the organization's internal URLs.</span></span> <span data-ttu-id="9721b-121">Dies ermöglicht es Administratoren, den URL-Zugriff für innerhalb des Umkreisnetzwerks befindliche Benutzer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9721b-121">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="9721b-122">Wenn Sie einen Watcher-Knoten für die Verwendung interner URLs anstelle externer URLs konfigurieren möchten, legen Sie die UseInternalWebUrls-Eigenschaft auf true ($true) fest:</span><span class="sxs-lookup"><span data-stu-id="9721b-122">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="9721b-123">Wenn Sie diese Eigenschaft auf den Standardwert false ($false) zurücksetzen, verwendet der Watcher die externen URLs:</span><span class="sxs-lookup"><span data-stu-id="9721b-123">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

<span data-ttu-id="9721b-124"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="9721b-124"></div>

<span> </span>

</div>

</div>

</span></span></div>

