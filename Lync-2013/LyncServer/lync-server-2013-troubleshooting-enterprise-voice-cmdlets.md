---
title: 'Lync Server 2013: Problembehandlung bei Enterprise-VoIP-Cmdlets'
description: 'Lync Server 2013: Problembehandlung bei Enterprise-VoIP-Cmdlets.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Enterprise Voice cmdlets
ms:assetid: 28ec32d2-6d1e-40e6-b2a8-065803288e8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415638(v=OCS.15)
ms:contentKeyID: 48183697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eeee9792ce635afc5c625394f6594676d0bd4f71
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49440843"
---
# <a name="troubleshooting-enterprise-voice-cmdlets-in-lync-server-2013"></a><span data-ttu-id="6c95f-103">Problembehandlung bei Enterprise-VoIP-Cmdlets in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c95f-103">Troubleshooting Enterprise Voice cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="6c95f-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="6c95f-104">

<span> </span></span></span>

<span data-ttu-id="6c95f-105">_**Letztes Änderungsdatum des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="6c95f-105">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="6c95f-106">Das Einrichten von Enterprise-VoIP im Rahmen Ihrer Microsoft lync Server 2013-Implementierung umfasst das Erstellen von Routen, Richtlinien und Regeln, die alle zusammenarbeiten müssen, um sicherzustellen, dass eingehende und ausgehende Anrufe wie erwartet abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="6c95f-106">Setting up Enterprise Voice as part of your Microsoft Lync Server 2013 implementation involves creating routes, policies and rules that must all work together to ensure incoming and outgoing calls are completed as expected.</span></span> <span data-ttu-id="6c95f-107">Die lync Server-Verwaltungsshell umfasst Cmdlets, die zum Testen von Verbindungen und Pfaden sowie zur Behandlung von Problemen, die während der Implementierung auftreten können, verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6c95f-107">Lync Server Management Shell includes cmdlets that can be used to test connections and paths and to troubleshoot issues that may arise during implementation.</span></span>

<div>

## <a name="troubleshooting-enterprise-voice-cmdlets"></a><span data-ttu-id="6c95f-108">Problembehandlung bei Enterprise-VoIP-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="6c95f-108">Troubleshooting Enterprise Voice Cmdlets</span></span>

<span data-ttu-id="6c95f-109">Die folgenden Cmdlets können verwendet werden, um Enterprise-VoIP-Verbindungen zu testen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="6c95f-109">The following cmdlets can be used to test and troubleshoot Enterprise Voice connections.</span></span>

<span data-ttu-id="6c95f-110">**Problembehandlung bei Enterprise-VoIP-Cmdlets**</span><span class="sxs-lookup"><span data-stu-id="6c95f-110">**Troubleshooting Enterprise Voice Cmdlets**</span></span>

  - <span></span>  
    <span data-ttu-id="6c95f-111">[Get-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c95f-111">[Get-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6c95f-112">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c95f-112">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6c95f-113">[Satz-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c95f-113">[Set-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6c95f-114">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c95f-114">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6c95f-115">[Neu – CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c95f-115">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6c95f-116">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c95f-116">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6c95f-117">[Satz-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c95f-117">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6c95f-118">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c95f-118">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6c95f-119">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c95f-119">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6c95f-120">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c95f-120">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6c95f-121">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c95f-121">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6c95f-122">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c95f-122">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6c95f-123">[Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6c95f-123">[Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c95f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c95f-124">See Also</span></span>


[<span data-ttu-id="6c95f-125">Enterprise-VoIP-Cmdlets in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c95f-125">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="6c95f-126">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="6c95f-126">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

<span data-ttu-id="6c95f-127"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="6c95f-127"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

