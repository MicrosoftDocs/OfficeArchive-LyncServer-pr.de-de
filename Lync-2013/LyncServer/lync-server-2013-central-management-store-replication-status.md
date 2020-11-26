---
title: 'Lync Server 2013: Replikationsstatus des zentralen Verwaltungsspeichers'
description: 'Lync Server 2013: Replikationsstatus des zentralen Verwaltungsspeichers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f1f9008a966040cf34ac0499c023f9dbe53a541
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49435460"
---
# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="d06a1-103">Replikationsstatus des zentralen Verwaltungsspeichers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d06a1-103">Central management store replication status in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="d06a1-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="d06a1-104">

<span> </span></span></span>

<span data-ttu-id="d06a1-105">_**Letztes Änderungsdatum des Themas:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="d06a1-105">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="d06a1-106">Wenn ein Administrator eine Art Änderung an lync Server vornimmt (Wenn beispielsweise ein Administrator eine neue VoIP-Richtlinie erstellt oder die Konfigurationseinstellungen des Adressbuchservers ändert), wird diese Änderung im zentralen Verwaltungsspeicher aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d06a1-106">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="d06a1-107">Die Änderung muss dann wiederum auf alle Computer repliziert werden, auf denen lync Server-Dienste oder Serverrollen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d06a1-107">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="d06a1-108">Zum Replizieren der Daten erstellt der Master-Replikationsdienst (der auf dem zentralen Verwaltungsserver ausgeführt wird) eine Momentaufnahme der geänderten Konfigurationsdaten.</span><span class="sxs-lookup"><span data-stu-id="d06a1-108">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="d06a1-109">Anschließend wird eine Kopie dieses Snapshots an jeden Computer gesendet, auf dem lync Server-Dienste oder Serverrollen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d06a1-109">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="d06a1-110">Auf diesen Computern erhält ein lokaler Replikations-Agent die Momentaufnahme und lädt die geänderten Daten hoch.</span><span class="sxs-lookup"><span data-stu-id="d06a1-110">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="d06a1-111">Der Agent sendet dann dem Master-Replikationsdienst eine Nachricht mit dem aktuellen Replikationsstatus.</span><span class="sxs-lookup"><span data-stu-id="d06a1-111">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="d06a1-112">Mit dem Get-CsManagementStoreReplicationStatus-Cmdlet können Sie den Replikationsstatus für alle (oder alle) lync Server-Computer in Ihrer Organisation überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d06a1-112">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="d06a1-113">Wer kann dieses Cmdlet ausführen?</span><span class="sxs-lookup"><span data-stu-id="d06a1-113">Who can run this cmdlet?</span></span> <span data-ttu-id="d06a1-114">Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Get-CsManagementStoreReplicationStatus-Cmdlet lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d06a1-114">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="d06a1-115">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="d06a1-115">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="d06a1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d06a1-116">See Also</span></span>


[<span data-ttu-id="d06a1-117">Get-CsManagementStoreReplicationStatus</span><span class="sxs-lookup"><span data-stu-id="d06a1-117">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

<span data-ttu-id="d06a1-118"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="d06a1-118"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

