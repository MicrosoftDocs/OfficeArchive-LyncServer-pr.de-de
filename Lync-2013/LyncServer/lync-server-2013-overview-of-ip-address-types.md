---
title: 'Lync Server 2013: Übersicht über IP-Adresstypen'
description: 'Lync Server 2013: Übersicht über IP-Adresstypen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81492b2e006a6f44f6deb78e6a0560f6e319992f
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49445134"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="d1266-103">Übersicht über IP-Adresstypen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1266-103">Overview of IP address types for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="d1266-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="d1266-104">

<span> </span></span></span>

<span data-ttu-id="d1266-105">_**Letztes Änderungsdatum des Themas:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="d1266-105">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="d1266-106">Bei der Konfiguration von IP-Adressen in lync Server 2013 stehen Ihnen drei Optionen zur Auswahl.</span><span class="sxs-lookup"><span data-stu-id="d1266-106">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="d1266-107">Sie können lync Server 2013 so konfigurieren, dass nur IP, Version 4 (IPv4), nur IP Version 6 (IPv6) oder eine Kombination aus beidem (als *dualer Stack* bezeichnet) unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d1266-107">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="d1266-108">Bei jedem Konfigurationstyp sind bestimmte Punkte zu beachten:</span><span class="sxs-lookup"><span data-stu-id="d1266-108">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="d1266-109">**Nur IPv4**   IPv6 wurde erstellt, weil die IPv4-Adressen für die Welt nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="d1266-109">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="d1266-110">IPv6 wird sich letztendlich weltweit durchsetzen, aber viele Unternehmen und Geräte, mit denen Ihr Unternehmen möglicherweise kommunizieren muss, unterstützen derzeit noch nicht IPv6 und möglicherweise bleibt das auch noch eine ganze Weile so.</span><span class="sxs-lookup"><span data-stu-id="d1266-110">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="d1266-111">Eine reine IPv4-Konfiguration wird dabei helfen, sicherzustellen, dass Ihre lync Server-Implementierung mit den meisten vorhandenen Geräten kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="d1266-111">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="d1266-112">**Nur IPv6**   Umgekehrt schließt eine vollständige IPv6-Implementierung zu diesem Zeitpunkt die Kommunikation mit vielen vorhandenen Geräten aus.</span><span class="sxs-lookup"><span data-stu-id="d1266-112">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="d1266-113">**Dual-Stack**   Dual Stack ist ein Netzwerk, in dem sowohl IPv4-als auch IPv6-Adressen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d1266-113">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="d1266-114">Diese Konfiguration wird in lync Server 2013 unterstützt, da in den meisten Fällen der Übergang von Full-IPv4 zu voll-IPv6 mehrere Jahre dauern wird.</span><span class="sxs-lookup"><span data-stu-id="d1266-114">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="d1266-115">In den folgenden Abschnitten wird die Kompatibilität zwischen diesen drei Konfigurationen für verschiedene lync Server-Features erläutert.</span><span class="sxs-lookup"><span data-stu-id="d1266-115">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1266-p104">Client- oder Serverkonfiguration mit reinem IPv6 wird nur zu Labor- oder Validierungszwecken unterstützt. Eine reine IPv6-Konfiguration wird in der serienmäßigen Bereitstellung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d1266-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="d1266-118">Clientregistrierung</span><span class="sxs-lookup"><span data-stu-id="d1266-118">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1266-119">Clientendpunkt-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="d1266-119">Client endpoint network</span></span></th>
<th><span data-ttu-id="d1266-120">Servernetzwerk</span><span class="sxs-lookup"><span data-stu-id="d1266-120">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1266-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d1266-122">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-122">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-123">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-123">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d1266-124">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-124">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1266-125">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-126">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-126">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-127">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-128">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-128">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1266-129">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-129">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-130">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-130">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d1266-132">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-132">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1266-133">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-133">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d1266-134">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-134">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="d1266-135">Peer-to-Peer-Client</span><span class="sxs-lookup"><span data-stu-id="d1266-135">Peer-to-Peer Client</span></span>

<span data-ttu-id="d1266-p105">Peer-to-Peer-Kommunikation umfasst Audio, Audio/Video, Anwendungsfreigabe und Dateiübertragung. Nach der erfolgreichen Registrierung beider Clients werden die folgenden Kombinationen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d1266-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1266-138">Clientendpunkt 1</span><span class="sxs-lookup"><span data-stu-id="d1266-138">Client endpoint 1</span></span></th>
<th><span data-ttu-id="d1266-139">Clientendpunkt 2</span><span class="sxs-lookup"><span data-stu-id="d1266-139">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1266-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d1266-141">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-141">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-142">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-142">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d1266-143">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-143">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1266-144">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-144">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-145">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-145">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d1266-147">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-147">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1266-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-148">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d1266-149">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-149">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="d1266-150">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="d1266-150">Conferencing</span></span>

<span data-ttu-id="d1266-151">Konferenz umfasst Audio/Video, Anwendungsfreigabe und Datenzusammenarbeit (Whiteboards und Dateifreigabe).</span><span class="sxs-lookup"><span data-stu-id="d1266-151">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1266-152">Clientendpunkt-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="d1266-152">Client endpoint network</span></span></th>
<th><span data-ttu-id="d1266-153">Servernetzwerk</span><span class="sxs-lookup"><span data-stu-id="d1266-153">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1266-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d1266-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-155">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-156">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-156">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d1266-157">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-157">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1266-158">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-159">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-159">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-160">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-161">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-161">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1266-162">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-162">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-163">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d1266-165">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-165">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1266-166">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-166">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d1266-167">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-167">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="d1266-168">Vermittlungsserver/PSTN</span><span class="sxs-lookup"><span data-stu-id="d1266-168">Mediation Server/PSTN</span></span>

<span data-ttu-id="d1266-169">Lync Server 2013 unterstützt keine medienumgehung für PSTN-Anrufe (Public Switched Telephone Network), wenn der Datenverkehr über eine IPv6-Schnittstelle erfolgt.</span><span class="sxs-lookup"><span data-stu-id="d1266-169">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="d1266-170">Wenn Medienumgehung erforderlich ist, sollten Sie das PSTN-Gateway mit IPv4 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d1266-170">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1266-171">Primäre Schnittstelle\*</span><span class="sxs-lookup"><span data-stu-id="d1266-171">Primary interface\*</span></span></th>
<th><span data-ttu-id="d1266-172">PSTN-Schnittstelle (auf dem Vermittlungsserver)</span><span class="sxs-lookup"><span data-stu-id="d1266-172">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="d1266-173">Einstellung für das PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="d1266-173">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1266-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-174">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d1266-175">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-176">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-176">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-177">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-177">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-178">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-179">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-179">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1266-180">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-180">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-181">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-181">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-182">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-182">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d1266-183">\* Die primäre Schnittstelle ist die Schnittstelle, die mit den lync Server-Komponenten kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="d1266-183">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="d1266-184">Peer-to-Peer-Kommunikation mit Remotebenutzern</span><span class="sxs-lookup"><span data-stu-id="d1266-184">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="d1266-185">Peer-to-Peer-Kommunikation mit Remotebenutzern umfasst Sofortnachrichten, Audio/Video, Anwendungsfreigabe und Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="d1266-185">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1266-186">Netzwerk des Remotebenutzers</span><span class="sxs-lookup"><span data-stu-id="d1266-186">Remote user network</span></span></th>
<th><span data-ttu-id="d1266-187">Edgeserver (externer Edge)</span><span class="sxs-lookup"><span data-stu-id="d1266-187">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1266-188">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-188">IPv4</span></span></p></td>
<td><p><span data-ttu-id="d1266-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-189">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-190">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-191">IPv4</span><span class="sxs-lookup"><span data-stu-id="d1266-191">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1266-192">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-192">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="d1266-193">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-193">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d1266-195">Dualer Stapel</span><span class="sxs-lookup"><span data-stu-id="d1266-195">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1266-196">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-196">IPv6</span></span></p></td>
<td><p><span data-ttu-id="d1266-197">IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-197">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="d1266-198">Konfiguration mit Front-End-Pool und Edgepool</span><span class="sxs-lookup"><span data-stu-id="d1266-198">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="d1266-199">Die folgende Tabelle zeigt die Support Matrix zwischen dem Front-End-Serverpool und dem internen Edge-Serverpool.</span><span class="sxs-lookup"><span data-stu-id="d1266-199">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="d1266-200">Schema der unterstützten Kombinationen zwischen Front-End-Pool und Edgepool (interner Edge)</span><span class="sxs-lookup"><span data-stu-id="d1266-200">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="d1266-201"><strong>Edgepool: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="d1266-201"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="d1266-202"><strong>Edgepool: Dualer Stapel</strong></span><span class="sxs-lookup"><span data-stu-id="d1266-202"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="d1266-203"><strong>Edgepool: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="d1266-203"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-204"><strong>Front-End-Pool: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="d1266-204"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="d1266-205">Ja</span><span class="sxs-lookup"><span data-stu-id="d1266-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1266-206">Ja</span><span class="sxs-lookup"><span data-stu-id="d1266-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1266-207">Nein</span><span class="sxs-lookup"><span data-stu-id="d1266-207">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1266-208"><strong>Front-End-Pool: Dualer Stapel</strong></span><span class="sxs-lookup"><span data-stu-id="d1266-208"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="d1266-209">Ja</span><span class="sxs-lookup"><span data-stu-id="d1266-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1266-210">Ja</span><span class="sxs-lookup"><span data-stu-id="d1266-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1266-211">Nein</span><span class="sxs-lookup"><span data-stu-id="d1266-211">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-212"><strong>Front-End-Pool: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="d1266-212"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="d1266-213">Nein</span><span class="sxs-lookup"><span data-stu-id="d1266-213">No</span></span></p></td>
<td><p><span data-ttu-id="d1266-214">Nein</span><span class="sxs-lookup"><span data-stu-id="d1266-214">No</span></span></p></td>
<td><p><span data-ttu-id="d1266-215">Ja\*</span><span class="sxs-lookup"><span data-stu-id="d1266-215">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d1266-216">\* Verwenden Sie diese Kombination nur in einer Lab-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="d1266-216">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="d1266-217">Die folgende Tabelle zeigt, welche Kombinationen zwischen den internen und externen Edge-Schnittstellen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d1266-217">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="d1266-218">Schema der unterstützten Kombinationen zwischen Edgepool (interner Edge) und Edgepool (externer Edge)</span><span class="sxs-lookup"><span data-stu-id="d1266-218">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="d1266-219"><strong>Edgepool (Externer Edge): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="d1266-219"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="d1266-220"><strong>Edgepool (Externer Edge): Dualer Stapel</strong></span><span class="sxs-lookup"><span data-stu-id="d1266-220"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="d1266-221"><strong>Edgepool (Externer Edge): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="d1266-221"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-222"><strong>Edgepool (Interner Edge): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="d1266-222"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="d1266-223">Ja</span><span class="sxs-lookup"><span data-stu-id="d1266-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1266-224">Ja</span><span class="sxs-lookup"><span data-stu-id="d1266-224">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1266-225">Nein</span><span class="sxs-lookup"><span data-stu-id="d1266-225">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1266-226"><strong>Edgepool (Interner Edge): Dualer Stapel</strong></span><span class="sxs-lookup"><span data-stu-id="d1266-226"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="d1266-227">Nein</span><span class="sxs-lookup"><span data-stu-id="d1266-227">No</span></span></p></td>
<td><p><span data-ttu-id="d1266-228">Ja</span><span class="sxs-lookup"><span data-stu-id="d1266-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="d1266-229">Nein</span><span class="sxs-lookup"><span data-stu-id="d1266-229">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1266-230"><strong>Edgepool (Interner Edge): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="d1266-230"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="d1266-231">Nein</span><span class="sxs-lookup"><span data-stu-id="d1266-231">No</span></span></p></td>
<td><p><span data-ttu-id="d1266-232">Nein</span><span class="sxs-lookup"><span data-stu-id="d1266-232">No</span></span></p></td>
<td><p><span data-ttu-id="d1266-233">Ja\*</span><span class="sxs-lookup"><span data-stu-id="d1266-233">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d1266-234">\* Verwenden Sie diese Kombination nur in einer Lab-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="d1266-234">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="d1266-235">Erweiterte Unterstützung für Enterprise-VoIP für IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-235">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="d1266-236">Bereitstellungen, die Anrufsteuerung (Call Admission Control, CAC), E911-Notrufdienste oder Medienumgehung beinhalten, können nur mit IPv4 oder als Implementierung mit dualem Stapel konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="d1266-236">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1266-237">In einer Dual-Stacked-Bereitstellung, auch wenn ein lync-Client eine Verbindung mit einem lync-Server mithilfe von IPv6 herstellt, bemüht sich lync, eine geeignete IPv4-Adresse zuzuordnen, um E9-1-1 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d1266-237">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="d1266-238">Der standortinformationsdienst mit IPv6-Adressen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d1266-238">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="d1266-p107">Exchange Unified Messaging (UM) unterstützt IPv6 nicht. Stellen Sie sicher, dass die DNS-Auflösung für Exchange UM keine IPv6-Adresse zurückgibt. Die Verwendung von IPv6 kann Fehler verursachen, wenn Anrufe an Voicemail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d1266-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="d1266-242">Andere lync Server 2013-Feature-Unterstützung für IPv6</span><span class="sxs-lookup"><span data-stu-id="d1266-242">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="d1266-243">Zusätzlich zu den zuvor erwähnten Features und Komponenten unterstützt lync Server 2013 IPv6 für die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="d1266-243">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="d1266-244">**Beständiger Chat**</span><span class="sxs-lookup"><span data-stu-id="d1266-244">**Persistent Chat**</span></span>
    
    <span data-ttu-id="d1266-245">Sie konfigurieren IPv6 für beständigen Chat mithilfe des Topologie-Generators.</span><span class="sxs-lookup"><span data-stu-id="d1266-245">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="d1266-246">Details zum Konfigurieren des beständigen Chats finden Sie in der Dokumentation zum Bereitstellen des beständigen Chats.</span><span class="sxs-lookup"><span data-stu-id="d1266-246">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="d1266-247">**QoE-Berichte und Berichte über die Aufzeichnung von Kommunikationsdatensätzen (KDS)**</span><span class="sxs-lookup"><span data-stu-id="d1266-247">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="d1266-248">In Monitoring-Berichten wird die IP-Adresse so angegeben, wie sie in der Monitoring Server-Datenbank gespeichert ist, unabhängig davon, ob der Adresstyp IPv4 oder IPv6 ist.</span><span class="sxs-lookup"><span data-stu-id="d1266-248">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

<span data-ttu-id="d1266-249"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="d1266-249"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

