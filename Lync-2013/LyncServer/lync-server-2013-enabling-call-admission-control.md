---
title: 'Lync Server 2013: Aktivieren der Anrufsteuerung'
description: 'Lync Server 2013: Aktivieren der Anrufsteuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f5737f83a1965b920f2a23e1aabbbaec2af7b3
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394723"
---
# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="0157a-103">Aktivieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0157a-103">Enabling call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="0157a-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="0157a-104">

<span> </span></span></span>

<span data-ttu-id="0157a-105">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0157a-105">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0157a-106">Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können.</span><span class="sxs-lookup"><span data-stu-id="0157a-106">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="0157a-107">Nachdem Sie das CAC-Netzwerk konfiguriert haben, müssen Sie CAC aktivieren, um die Bandbreiteneinschränkungen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="0157a-107">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="0157a-108">Hierzu können Sie die lync Server-Systemsteuerung verwenden.</span><span class="sxs-lookup"><span data-stu-id="0157a-108">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="0157a-109">So aktivieren Sie CAC über die lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="0157a-109">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0157a-110">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="0157a-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0157a-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0157a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0157a-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0157a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0157a-113">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Global**.</span><span class="sxs-lookup"><span data-stu-id="0157a-113">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="0157a-114">Klicken Sie auf der Seite **Global** auf die **globale** Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="0157a-114">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0157a-115">Für jede Microsoft lync Server 2013-Bereitstellung kann nur ein Netzwerk konfiguriert werden, sodass in der Liste nie mehr als eine Netzwerkkonfiguration vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0157a-115">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="0157a-116">Sie können die globale Konfiguration nicht umbenennen.</span><span class="sxs-lookup"><span data-stu-id="0157a-116">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="0157a-117">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="0157a-117">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="0157a-118">Aktivieren Sie auf der Seite **globale Einstellungen bearbeiten** das Kontrollkästchen **Anruf Zulassungs Steuerung aktivieren** , und klicken Sie dann auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="0157a-118">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="0157a-119">Wenn Sie auf **Commit** klicken, führen Sie einen Test der Konfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="0157a-119">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="0157a-120">Das Dialogfeld **globale Einstellungen bearbeiten** wird geschlossen, und Sie kehren zur **globalen** Seite zurück.</span><span class="sxs-lookup"><span data-stu-id="0157a-120">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="0157a-121">Sie erhalten eine Warnung, wenn in Ihrer Netzwerkkonfiguration Fehler oder Inkonsistenzen festgestellt werden, die verhindern, dass Sie ordnungsgemäß funktionieren (Wenn beispielsweise alle Regionen über eine interregions Route nicht mit allen anderen Regionen verbunden sind).</span><span class="sxs-lookup"><span data-stu-id="0157a-121">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="0157a-122">Wenn Sie Änderungen an Ihrer Netzwerkkonfiguration vornehmen, können Sie die Überprüfungs Prüfung erneut ausführen, indem Sie die globale Konfiguration öffnen und auf **Commit** klicken.</span><span class="sxs-lookup"><span data-stu-id="0157a-122">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="0157a-123">Sie müssen CAC nicht zuerst deaktivieren: lassen Sie das Kontrollkästchen aktiviert, und klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="0157a-123">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="0157a-124">Sie können dies jederzeit tun, ohne Konfigurationsänderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="0157a-124">You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0157a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0157a-125">See Also</span></span>


[<span data-ttu-id="0157a-126">Übersicht über die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0157a-126">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="0157a-127">Planen des Anrufsteuerungsdiensts in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0157a-127">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="0157a-128">Konfigurieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0157a-128">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="0157a-129">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="0157a-129">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="0157a-130">Satz-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="0157a-130">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="0157a-131">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="0157a-131">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

<span data-ttu-id="0157a-132"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="0157a-132"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

