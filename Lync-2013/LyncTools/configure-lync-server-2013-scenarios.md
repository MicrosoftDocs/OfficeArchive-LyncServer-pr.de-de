---
title: Konfigurieren von lync Server 2013-Szenarien
description: Konfigurieren von lync Server 2013-Szenarien
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4a5b7bd271191067779ac358807cc54918b16bc
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49440073"
---
# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="a193c-103">Konfigurieren von lync Server 2013-Szenarien</span><span class="sxs-lookup"><span data-stu-id="a193c-103">Configure Lync Server 2013 Scenarios</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="a193c-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="a193c-104">

<span> </span></span></span>

<span data-ttu-id="a193c-105">_**Letztes Änderungsdatum des Themas:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="a193c-105">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="a193c-106">Zum Ausführen des lync Server 2013-Stress-und-Leistungstools (LyncPerfTool) muss die lync Server 2013-Topologie zunächst für die Szenarios konfiguriert werden, die ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a193c-106">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="a193c-107">Wenn lync Server 2013 nicht konfiguriert ist oder falsch konfiguriert ist, schlägt die Auslastungssimulation in den meisten Fällen fehl.</span><span class="sxs-lookup"><span data-stu-id="a193c-107">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="a193c-108">Mit dem lync Server 2013-Stress-und-Leistungs Tool haben wir Beispielskripts zur lync Server-Verwaltungsshell und grundlegende Ressourcendateien bereitgestellt, die als Ausgangspunkt für die Konfiguration von lync Server 2013 verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a193c-108">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="a193c-109">In diesem Thema werden die bereitgestellten Windows PowerShell-Beispiele beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a193c-109">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="a193c-110">Beachten Sie, dass es nicht das Ziel dieses Themas ist, die Konfiguration von lync Server 2013 im Allgemeinen zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="a193c-110">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="a193c-111">Details zum Arbeiten mit Windows PowerShell in lync Server 2013 finden Sie in der Dokumentation zur lync Server-Verwaltungsshell unter <https://technet.microsoft.com/library/gg398474.aspx> .</span><span class="sxs-lookup"><span data-stu-id="a193c-111">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="a193c-112">Informationen zum Ausführen von lync Server-Verwaltungsshell-Skripts</span><span class="sxs-lookup"><span data-stu-id="a193c-112">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="a193c-113">Wir haben Beispielskripts für die lync Server-Verwaltungsshell bereitgestellt, die möglicherweise zur Vorbereitung der Auslastungssimulation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a193c-113">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="a193c-114">Da die Skripts für die Auslastungssimulation vorgesehen sind, sind Sie einfach und frei zügig und daher möglicherweise nicht für die Produktion geeignet.</span><span class="sxs-lookup"><span data-stu-id="a193c-114">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="a193c-115">Alle Skripts sind Beispiele und müssen überprüft und in einigen Fällen geändert werden, um Ihre Topologie wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="a193c-115">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="a193c-116">Wir gehen davon aus, dass das Szenario des Reaktionsgruppendiensts (RGS) mindestens geändert werden muss, um die Agents anzugeben, die den Agentengruppen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="a193c-116">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="a193c-117">Sie haben jedoch die Möglichkeit, diese Last nicht zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="a193c-117">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="a193c-118">Achten Sie darauf, die bereitgestellten Beispiele zu überprüfen und zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="a193c-118">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="a193c-119">In Skripts werden alle vorhandenen Einstellungen in der Topologie überschrieben.</span><span class="sxs-lookup"><span data-stu-id="a193c-119">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a193c-120">Ausführliche Informationen zur Verwendung von Windows PowerShell und der lync Server-Verwaltungsshell finden Sie im Windows PowerShell-Blog zu lync Server 2013 unter <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A> .</span><span class="sxs-lookup"><span data-stu-id="a193c-120">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="a193c-121">Client Version-Moniker für Spannungs-und Leistungs Tool</span><span class="sxs-lookup"><span data-stu-id="a193c-121">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="a193c-122">Möglicherweise müssen Sie die Richtlinie für die Client Versionsüberprüfung konfigurieren, wenn Sie die Einstellungen von den Standardwerten geändert haben.</span><span class="sxs-lookup"><span data-stu-id="a193c-122">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="a193c-123">Ausführliche Informationen finden Sie unter "Konfigurieren unterstützter Clientversionen" unter <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx> .</span><span class="sxs-lookup"><span data-stu-id="a193c-123">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="a193c-124">Das Stress-und Leistungs Tool von lync Server 2013 verwendet die folgenden Benutzer-Agent-Versionen standardmäßig bei der Kommunikation mit lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="a193c-124">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="a193c-125">LSPT/15.0.0.0 (lync Server 2013 Stress and Performance Tool)</span><span class="sxs-lookup"><span data-stu-id="a193c-125">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="a193c-126">OCPHONE/. 0.522</span><span class="sxs-lookup"><span data-stu-id="a193c-126">OCPHONE/.0.522</span></span>

<span data-ttu-id="a193c-127">Diese sind für den Mobilitäts Client (UCWA) in LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="a193c-127">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="a193c-128">Ucwa-perf-Tool/Webkonferenz</span><span class="sxs-lookup"><span data-stu-id="a193c-128">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="a193c-129">Ucwa perf Tool/Mobil</span><span class="sxs-lookup"><span data-stu-id="a193c-129">Ucwa Perf Tool/Mobile</span></span>

<span data-ttu-id="a193c-130"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="a193c-130"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

