---
title: 'Lync Server 2013: Anzeigen von Netzwerk Regionsinformationen'
description: 'Lync Server 2013: Anzeigen von Netzwerk Regionsinformationen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 225cafc392b9b9d0c23f3882d530ad6d2b59f165
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49446276"
---
# <a name="viewing-network-region-information-in-lync-server-2013"></a><span data-ttu-id="ce40b-103">Anzeigen von Netzwerk Regionsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce40b-103">Viewing network region information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="ce40b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="ce40b-104">

<span> </span></span></span>

<span data-ttu-id="ce40b-105">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ce40b-105">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ce40b-106">Ein Netzwerkbereich verbindet verschiedene Teile eines Netzwerks über mehrere geographische Bereiche hinweg.</span><span class="sxs-lookup"><span data-stu-id="ce40b-106">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ce40b-107">Jeder Netzwerkbereich muss einem zentralen Standort zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="ce40b-107">Every network region must be associated with a central site.</span></span> <span data-ttu-id="ce40b-108">Der zentrale Standort ist die Datencenter-Website, auf der der bandbreitenrichtliniendienst für die Anrufannahme Steuerung (CAC) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ce40b-108">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="ce40b-109">Sie können die lync Server-Systemsteuerung verwenden, um netzwerkregionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce40b-109">You can use Lync Server Control Panel to view network regions.</span></span> <span data-ttu-id="ce40b-110">Zu den netzwerkregionen gehören Einstellungen, die bestimmen, ob für Audio-und Videoverbindungen alternative Pfade über das Internet zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="ce40b-110">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="ce40b-111">Verwenden Sie dieses Thema, um vorhandene netzwerkregionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce40b-111">Use this topic to view existing network regions.</span></span> <span data-ttu-id="ce40b-112">Details zum Erstellen oder Ändern vorhandener netzwerkregionen finden Sie unter [erstellen oder Ändern von netzwerkregionen in lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="ce40b-112">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a><span data-ttu-id="ce40b-113">So zeigen Sie Informationen zu einem Netzwerkbereich mit der lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="ce40b-113">To view information about a network region with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ce40b-114">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ce40b-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ce40b-115">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ce40b-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ce40b-116">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ce40b-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ce40b-117">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="ce40b-117">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="ce40b-118">Klicken Sie auf der Seite **Region** auf den Bereich, den Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="ce40b-118">On the **Region** page, click the region you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ce40b-119">Sie können nur jeweils einen Bereich anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce40b-119">You can only view one region at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="ce40b-120">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ce40b-120">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ce40b-121">Anzeigen von Netzwerk Regionsinformationen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ce40b-121">Viewing Network Region Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ce40b-122">Sie können Netzwerk Regionsinformationen mithilfe von Windows PowerShell und dem Cmdlet **Get-CsNetworkRegion** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce40b-122">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="ce40b-123">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="ce40b-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ce40b-124">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="ce40b-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-information"></a><span data-ttu-id="ce40b-125">So zeigen Sie Netzwerkbereichs Informationen an</span><span class="sxs-lookup"><span data-stu-id="ce40b-125">To view network region information</span></span>

  - <span data-ttu-id="ce40b-126">Wenn Sie Informationen zu allen ihren netzwerkregionen anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="ce40b-126">To view information about all your network regions, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="ce40b-127">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="ce40b-127">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

<span data-ttu-id="ce40b-128">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="ce40b-128">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce40b-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce40b-129">See Also</span></span>


[<span data-ttu-id="ce40b-130">Erstellen oder Ändern von netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce40b-130">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
[<span data-ttu-id="ce40b-131">Löschen vorhandener netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce40b-131">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
  

<span data-ttu-id="ce40b-132"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="ce40b-132"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

