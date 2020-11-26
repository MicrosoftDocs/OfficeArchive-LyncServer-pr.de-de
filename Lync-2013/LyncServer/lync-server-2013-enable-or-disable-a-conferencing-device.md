---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren eines Konferenz Geräts'
description: 'Lync Server 2013: Aktivieren oder Deaktivieren eines Konferenz Geräts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 761bc19536c889cced68ff586753f6800df0da59
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437574"
---
# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a><span data-ttu-id="e2762-103">Aktivieren oder Deaktivieren eines Konferenz Geräts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2762-103">Enable or disable a conferencing device in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e2762-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e2762-104">

<span> </span></span></span>

<span data-ttu-id="e2762-105">_**Letztes Änderungsdatum des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e2762-105">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e2762-106">Aktivieren und deaktivieren Sie ein Konferenzgerät mithilfe des Cmdlets **enable-CsMeetingRoom** und des Cmdlets **Disable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="e2762-106">Enable and disable a conferencing device by using the **Enable-CsMeetingRoom** cmdlet and the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="e2762-107">Diese Cmdlets können entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e2762-107">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2762-108">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="e2762-108">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a><span data-ttu-id="e2762-109">Aktivieren eines Konferenz Geräts</span><span class="sxs-lookup"><span data-stu-id="e2762-109">Enabling a Conferencing Device</span></span>

  - <span data-ttu-id="e2762-110">Verwenden Sie zum Aktivieren eines Konferenz Geräts das Cmdlet **enable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="e2762-110">To enable a conferencing device, use the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="e2762-111">Wenn Sie ein Konferenzgerät aktivieren, müssen Sie ein) die Konferenzgeräte Identität, b) den Registrierungspool, in dem sich das Raum Konto befindet, und c) die SIP-Adresse einbeziehen, die diesem Konto zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2762-111">When enabling a conferencing device, you must include a) the conferencing device identity, b) the Registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a><span data-ttu-id="e2762-112">Deaktivieren eines Konferenz Geräts</span><span class="sxs-lookup"><span data-stu-id="e2762-112">Disabling a Conferencing Device</span></span>

  - <span data-ttu-id="e2762-113">Verwenden Sie zum Deaktivieren eines Konferenz Geräts das Cmdlet **Disable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="e2762-113">To disable a conferencing device, use the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="e2762-114">Stellen Sie sicher, dass Sie die Identität des Konferenz Geräts angeben, das deaktiviert werden soll:</span><span class="sxs-lookup"><span data-stu-id="e2762-114">Make sure that you specify the identity of the conferencing device to be disabled:</span></span>
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<span data-ttu-id="e2762-115">Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) und dem Cmdlet [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="e2762-115">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) cmdlet.</span></span>

<span data-ttu-id="e2762-116"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e2762-116"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

