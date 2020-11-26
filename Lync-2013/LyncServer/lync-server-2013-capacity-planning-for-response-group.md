---
title: 'Lync Server 2013: Kapazitätsplanung für Reaktionsgruppen'
description: 'Lync Server 2013: Kapazitätsplanung für Reaktionsgruppe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78c543f558f67deaaeb781b308aa5f68d39cd785
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49435530"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="ed654-103">Kapazitätsplanung für Reaktionsgruppen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed654-103">Capacity planning for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="ed654-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="ed654-104">

<span> </span></span></span>

<span data-ttu-id="ed654-105">_**Letztes Änderungsdatum des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="ed654-105">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="ed654-106">In der folgenden Tabelle wird das Benutzermodell der Reaktionsgruppe beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ed654-106">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed654-p101">Bei den Zahlen in der folgenden Tabelle wird davon ausgegangen, dass Sie 16-kHz-, Mono-, 16-Bit-WAV-Dateien für alle Audiodateien für Reaktionsgruppen verwenden. Wenn Sie andere Dateiformate, z. B. Windows Media Audio (WMA), einsetzen, können die Zahlen abweichen.</span><span class="sxs-lookup"><span data-stu-id="ed654-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ed654-109">Bedenken Sie bei der Kapazitätsplanung für die Notfallwiederherstellung, dass jeder Pool eines Poolpaars in der Lage sein sollte, die Arbeitslasten für alle Reaktionsgruppen in beiden Pools zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ed654-109">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="ed654-110">Benutzermodell für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="ed654-110">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed654-111">Metrik</span><span class="sxs-lookup"><span data-stu-id="ed654-111">Metric</span></span></th>
<th><span data-ttu-id="ed654-112">Pro Enterprise Edition-Pool (mit 8 Front-End-Servern)</span><span class="sxs-lookup"><span data-stu-id="ed654-112">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="ed654-113">Pro Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="ed654-113">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed654-114">Eingehende Anrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="ed654-114">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="ed654-115">16</span><span class="sxs-lookup"><span data-stu-id="ed654-115">16</span></span></p></td>
<td><p><span data-ttu-id="ed654-116">2</span><span class="sxs-lookup"><span data-stu-id="ed654-116">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed654-117">Gleichzeitige mit interaktiver Sprachantwort (IVR) oder Wartemusik (MoH) verbundene Anrufe</span><span class="sxs-lookup"><span data-stu-id="ed654-117">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="ed654-118">480</span><span class="sxs-lookup"><span data-stu-id="ed654-118">480</span></span></p></td>
<td><p><span data-ttu-id="ed654-119">60</span><span class="sxs-lookup"><span data-stu-id="ed654-119">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed654-120">Gleichzeitige anonyme Sitzungen (ohne Chat)</span><span class="sxs-lookup"><span data-stu-id="ed654-120">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="ed654-121">224</span><span class="sxs-lookup"><span data-stu-id="ed654-121">224</span></span></p></td>
<td><p><span data-ttu-id="ed654-122">28</span><span class="sxs-lookup"><span data-stu-id="ed654-122">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed654-123">Gleichzeitige anonyme Sitzungen (mit Chat)</span><span class="sxs-lookup"><span data-stu-id="ed654-123">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="ed654-124">64</span><span class="sxs-lookup"><span data-stu-id="ed654-124">64</span></span></p></td>
<td><p><span data-ttu-id="ed654-125">8</span><span class="sxs-lookup"><span data-stu-id="ed654-125">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed654-126">Aktive Agents (formell und informell)</span><span class="sxs-lookup"><span data-stu-id="ed654-126">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="ed654-127">1200</span><span class="sxs-lookup"><span data-stu-id="ed654-127">1200</span></span></p></td>
<td><p><span data-ttu-id="ed654-128">1200</span><span class="sxs-lookup"><span data-stu-id="ed654-128">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed654-129">Anzahl der Sammelanschlüsse</span><span class="sxs-lookup"><span data-stu-id="ed654-129">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="ed654-130">400</span><span class="sxs-lookup"><span data-stu-id="ed654-130">400</span></span></p></td>
<td><p><span data-ttu-id="ed654-131">400</span><span class="sxs-lookup"><span data-stu-id="ed654-131">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed654-132">Anzahl der IVR-Gruppen (Verwendung der Spracherkennung)</span><span class="sxs-lookup"><span data-stu-id="ed654-132">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="ed654-133">200</span><span class="sxs-lookup"><span data-stu-id="ed654-133">200</span></span></p></td>
<td><p><span data-ttu-id="ed654-134">200</span><span class="sxs-lookup"><span data-stu-id="ed654-134">200</span></span></p></td>
</tr>
</tbody>
</table><span data-ttu-id="ed654-135">


</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="ed654-135">


</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

