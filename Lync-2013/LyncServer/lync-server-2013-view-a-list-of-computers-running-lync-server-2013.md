---
title: 'Lync Server 2013: Anzeigen einer Liste der Computer mit lync Server 2013'
description: 'Lync Server 2013: Anzeigen einer Liste mit Computern, auf denen lync Server 2013 ausgeführt wird.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of computers running Lync Server 2013
ms:assetid: 44eeec27-8b99-44f0-b0bd-622c12393d34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520987(v=OCS.15)
ms:contentKeyID: 48184030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baeb2d8e926b1597c463259378332e0c9f50268f
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49440423"
---
# <a name="view-a-list-of-computers-running-lync-server-2013"></a><span data-ttu-id="d1c38-103">Anzeigen einer Liste der Computer mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c38-103">View a list of computers running Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="d1c38-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="d1c38-104">

<span> </span></span></span>

<span data-ttu-id="d1c38-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d1c38-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d1c38-106">Sie können die lync Server 2013-Systemsteuerung verwenden, um eine Liste aller Computer anzuzeigen, auf denen lync Server 2013 in Ihrer Topologie ausgeführt wird, und den jeweiligen Dienststatus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d1c38-106">You can use Lync Server 2013 Control Panel to view a list of all the computers that are running Lync Server 2013 in your topology and see the service status of each.</span></span> <span data-ttu-id="d1c38-107">Sie können die Liste nach Computer, Pool oder Website sortieren.</span><span class="sxs-lookup"><span data-stu-id="d1c38-107">You can sort the list by computer, pool, or site.</span></span>

<div>

## <a name="to-view-a-list-of-computers-running-lync-server"></a><span data-ttu-id="d1c38-108">So zeigen Sie eine Liste der Computer mit lync Server an</span><span class="sxs-lookup"><span data-stu-id="d1c38-108">To view a list of computers running Lync Server</span></span>

1.  <span data-ttu-id="d1c38-109">Melden Sie sich bei einem Benutzerkonto, das einer der vordefinierten Administratorrollen für lync Server 2013 zugewiesen ist, bei jedem Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d1c38-109">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="d1c38-110">Details zu den vordefinierten Administratorrollen, die in lync Server 2013 zur Verfügung stehen, finden Sie unter [Planen der rollenbasierten Zugriffssteuerung in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="d1c38-110">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="d1c38-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d1c38-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d1c38-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d1c38-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d1c38-113">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="d1c38-113">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="d1c38-114">Führen Sie auf der **Status** Seite nach Bedarf eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="d1c38-114">On the **Status** page, do any of the following as needed:</span></span>
    
      - <span data-ttu-id="d1c38-115">Sortieren Sie die Liste, indem Sie auf die Überschrift **Computer**, **Pool** oder **Website** Spalte und dann auf den nach oben oder den nach unten weisenden Pfeil klicken.</span><span class="sxs-lookup"><span data-stu-id="d1c38-115">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    
      - <span data-ttu-id="d1c38-116">Klicken Sie auf **Aktualisieren** , um die aktuelle Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d1c38-116">Click **Refresh** to view the most up-to-date list.</span></span>
    
      - <span data-ttu-id="d1c38-117">Suchen Sie nach einem bestimmten Computer, indem Sie den Computernamen in das Suchfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="d1c38-117">Search for a specific computer by typing the computer name in the search field.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1c38-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1c38-118">See Also</span></span>


[<span data-ttu-id="d1c38-119">Verwalten der Lync Server 2013-Topologie</span><span class="sxs-lookup"><span data-stu-id="d1c38-119">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

<span data-ttu-id="d1c38-120"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="d1c38-120"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

