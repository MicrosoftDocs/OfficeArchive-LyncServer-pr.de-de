---
title: 'Lync Server 2013: Auswählen einer Topologie'
description: 'Lync Server 2013: Auswählen einer Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01ded739c3c5e4e0bd8c0f25f3f0fe8ff1f350b9
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49434908"
---
# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="c81cb-103">Auswählen einer Topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81cb-103">Choosing a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="c81cb-104">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c81cb-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c81cb-105">Wenn Sie eine Topologie auswählen, können Sie eine der folgenden unterstützten Topologie-Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="c81cb-105">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c81cb-106">Wenn Sie über Erfahrungen mit Microsoft lync Server 2010 verfügen, finden Sie, sofern nicht anders angegeben, die Anleitungen hier weitgehend unverändert.</span><span class="sxs-lookup"><span data-stu-id="c81cb-106">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="c81cb-107">Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81cb-107">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="c81cb-108">Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81cb-108">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="c81cb-109">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81cb-109">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="c81cb-110">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81cb-110">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="c81cb-111">Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81cb-111">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="c81cb-112">Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c81cb-112">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="c81cb-113">Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c81cb-113">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="c81cb-114">In der folgenden Tabelle sind die Funktionen zusammengefasst, die mit den unterstützten Microsoft lync Server 2013-Topologien verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c81cb-114">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="c81cb-115">Die Spaltenüberschriften geben die Funktionalität an, die für eine bestimmte Edge-Konfigurationsoption verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c81cb-115">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="c81cb-116">Wenn Sie beispielsweise die Option skalierte Kante (DNS Load Balanced) verwenden, können Sie sehen, dass Sie eine hohe Verfügbarkeit unterstützt, nicht routingfähige private IP-Adressen (mit NAT) oder routingfähige öffentliche IP-Adressen verwenden, die den Edge-externen Schnittstellen zugewiesen sind, und die Kosten reduzieren, da ein Hardwarelastenausgleich nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c81cb-116">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="c81cb-117">Unterstützte Edge-Failover-Szenarien bei der DNS-Lastverteilung sind lync-zu-Point-Sitzungen, lync-Konferenzsitzungen, lync-zu-PSTN-Sitzungen, Office 365 und Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c81cb-117">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions, Office 365, and Microsoft 365.</span></span> <span data-ttu-id="c81cb-118">Edge-Failover-Szenarien, die nicht vom DNS-Lastenausgleich profitieren, sind Failover für Remotebenutzer Exchange Unified Messaging (um) (vor Exchange 2010 SP1), öffentliche Instant Messaging (im)-Konnektivität und Verbund mit Servern, auf denen Office Communications Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c81cb-118">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="c81cb-119">Zusammenfassung der Optionen für die Edgeserver-Topologie</span><span class="sxs-lookup"><span data-stu-id="c81cb-119">Summary of Edge Server Topology Options</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c81cb-120">Topologie</span><span class="sxs-lookup"><span data-stu-id="c81cb-120">Topology</span></span></th>
<th><span data-ttu-id="c81cb-121">Hochverfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="c81cb-121">High availability</span></span></th>
<th><span data-ttu-id="c81cb-122">Zusätzliche DNS-A-Einträge für externen Edgeserver im Edge-Pool erforderlich</span><span class="sxs-lookup"><span data-stu-id="c81cb-122">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="c81cb-123">Edge-Failover für lync-zu-lync-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="c81cb-123">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="c81cb-124">Edge-Failover für lync-zu-lync-EUM/PIC/OCS-Verbund Sitzungen</span><span class="sxs-lookup"><span data-stu-id="c81cb-124">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c81cb-125">Single Edge mit NAT</span><span class="sxs-lookup"><span data-stu-id="c81cb-125">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="c81cb-126">Nein</span><span class="sxs-lookup"><span data-stu-id="c81cb-126">No</span></span></p></td>
<td><p><span data-ttu-id="c81cb-127">Nein</span><span class="sxs-lookup"><span data-stu-id="c81cb-127">No</span></span></p></td>
<td><p><span data-ttu-id="c81cb-128">Nein</span><span class="sxs-lookup"><span data-stu-id="c81cb-128">No</span></span></p></td>
<td><p><span data-ttu-id="c81cb-129">Nein</span><span class="sxs-lookup"><span data-stu-id="c81cb-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c81cb-130">Single Edge mit öffentlicher IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c81cb-130">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="c81cb-131">Nein</span><span class="sxs-lookup"><span data-stu-id="c81cb-131">No</span></span></p></td>
<td><p><span data-ttu-id="c81cb-132">Nein</span><span class="sxs-lookup"><span data-stu-id="c81cb-132">No</span></span></p></td>
<td><p><span data-ttu-id="c81cb-133">Nein</span><span class="sxs-lookup"><span data-stu-id="c81cb-133">No</span></span></p></td>
<td><p><span data-ttu-id="c81cb-134">Nein</span><span class="sxs-lookup"><span data-stu-id="c81cb-134">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c81cb-135">Skalierte Kante (DNS Load Balanced) mithilfe von NAT</span><span class="sxs-lookup"><span data-stu-id="c81cb-135">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="c81cb-136">Ja</span><span class="sxs-lookup"><span data-stu-id="c81cb-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="c81cb-137">Ja</span><span class="sxs-lookup"><span data-stu-id="c81cb-137">Yes</span></span></p></td>
<td><p><span data-ttu-id="c81cb-138">Ja</span><span class="sxs-lookup"><span data-stu-id="c81cb-138">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c81cb-139">Skalierter Edge (DNS Load Balanced) mit öffentlicher IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c81cb-139">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="c81cb-140">Ja</span><span class="sxs-lookup"><span data-stu-id="c81cb-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="c81cb-141">Ja</span><span class="sxs-lookup"><span data-stu-id="c81cb-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="c81cb-142">Ja</span><span class="sxs-lookup"><span data-stu-id="c81cb-142">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c81cb-143">Lastenausgleich für skalierte Edge-Hardware</span><span class="sxs-lookup"><span data-stu-id="c81cb-143">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="c81cb-144">Ja</span><span class="sxs-lookup"><span data-stu-id="c81cb-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="c81cb-145">Nein (ein DNS A-Eintrag pro VIP)</span><span class="sxs-lookup"><span data-stu-id="c81cb-145">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="c81cb-146">Ja</span><span class="sxs-lookup"><span data-stu-id="c81cb-146">Yes</span></span></p></td>
<td><p><span data-ttu-id="c81cb-147">Ja</span><span class="sxs-lookup"><span data-stu-id="c81cb-147">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c81cb-148">\**\** _ Failover für Public Instant Messaging (im)-Konnektivität und Föderation mit Servern, auf denen Office Communications Server ausgeführt wird, ist im DNS-Lastenausgleich nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c81cb-148">\**\** _ Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="c81cb-149">Exchange um-Failover (Remotebenutzer) mithilfe des DNS-Lastenausgleichs erfordert Exchange Server 2010 SP1 oder höher.</span><span class="sxs-lookup"><span data-stu-id="c81cb-149">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="c81cb-150">Topologien mit einem Edge und einem skalierten Edge (DNS Load Balanced) können verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c81cb-150">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="c81cb-151">Routingfähige öffentliche IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="c81cb-151">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="c81cb-152">Nicht routingfähige private IP-Adresse, wenn eine symmetrische Netzwerkadressübersetzung (Network Address Translation, NAT) verwendet wird</span><span class="sxs-lookup"><span data-stu-id="c81cb-152">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="c81cb-153">Wenn Sie die öffentliche IP-Adresse oder private IP-Adresse mit NAT verwenden, verwenden Sie weiterhin die gleiche Anzahl von IP-Adressen basierend auf Ihrer Konfigurationswahl im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="c81cb-153">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="c81cb-154">Sie können den Edgeserver so konfigurieren, dass eine einzelne IP-Adresse mit unterschiedlichen Ports pro Dienst verwendet wird, oder Sie können unterschiedliche IP-Adressen pro Dienst verwenden, aber denselben Port verwenden (standardmäßig TCP 443).</span><span class="sxs-lookup"><span data-stu-id="c81cb-154">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="c81cb-155">Wenn Sie sich entschließen, nicht routingfähige private IP-Adressen mit NAT zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="c81cb-155">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="c81cb-156">Sie müssen routingfähige private IP-Adressen für alle drei externen Schnittstellen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c81cb-156">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="c81cb-157">Sie müssen symmetrische NAT für eingehenden und ausgehenden Datenverkehr konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c81cb-157">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="c81cb-158">Die Topologie für skalierte Kanten (Hardwarelastenausgleich) muss öffentliche IP-Adressen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c81cb-158">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="c81cb-159">Lync Server 2013 unterstützt das Platzieren von Access-, Webkonferenz-und a/V-Edge-externen Schnittstellen hinter einem Router oder einer Firewall, die Netzwerkadressübersetzung (Network Address Translation, NAT) sowohl für einzelne als auch für skalierte konsolidierte Edge-Server-Topologien ausführt.</span><span class="sxs-lookup"><span data-stu-id="c81cb-159">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="c81cb-160">Die Verwendung von NAT für alle externen Edge-Schnittstellen erfordert die Verwendung des DNS-Lastenausgleichs.</span><span class="sxs-lookup"><span data-stu-id="c81cb-160">Using NAT for all Edge external interfaces requires the use of DNS load balancing.</span></span> <span data-ttu-id="c81cb-161">Im Vergleich zur Verwendung von Hardwarelastenausgleichs können Sie mithilfe des DNS-Lastenausgleichs ohne NAT die Anzahl der öffentlichen IP-Adressen pro Edgeserver in einem Edge-Pool reduzieren, wie in der folgenden Liste beschrieben:</span><span class="sxs-lookup"><span data-stu-id="c81cb-161">When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="c81cb-162">Der von lync Server 2013 skalierte konsolidierte Edge (DNS Load Balanced) erfordert drei öffentliche IP-Adressen für jeden Edgeserver in einem Edge-Pool.</span><span class="sxs-lookup"><span data-stu-id="c81cb-162">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="c81cb-163">Der von lync Server 2013 skalierte konsolidierte Edge (Hardwarelastenausgleich) erfordert drei öffentliche IP-Adressen für virtuelle IP-Adressen vom Lastenausgleichsmodul (eine einmalige Anforderung, die nicht inkrementiert, wenn dem Pool weitere Edgeserver hinzugefügt werden) sowie drei öffentliche IP-Adressen pro Edgeserver in einem Pool.</span><span class="sxs-lookup"><span data-stu-id="c81cb-163">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="c81cb-164">IP-Adressen Anforderungen für den skalierten konsolidierten Edge (IP-Adresse pro Rolle)</span><span class="sxs-lookup"><span data-stu-id="c81cb-164">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c81cb-165">Anzahl der Edgeserver pro Pool</span><span class="sxs-lookup"><span data-stu-id="c81cb-165">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="c81cb-166">Anzahl der erforderlichen IP-Adressen lync Server 2013 (DNS Load Balanced)</span><span class="sxs-lookup"><span data-stu-id="c81cb-166">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="c81cb-167">Anzahl der erforderlichen IP-Adressen lync Server 2013 (Hardwarelastenausgleich)</span><span class="sxs-lookup"><span data-stu-id="c81cb-167">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c81cb-168">2</span><span class="sxs-lookup"><span data-stu-id="c81cb-168">2</span></span></p></td>
<td><p><span data-ttu-id="c81cb-169">6</span><span class="sxs-lookup"><span data-stu-id="c81cb-169">6</span></span></p></td>
<td><p><span data-ttu-id="c81cb-170">3 (1 pro VIP) + 6</span><span class="sxs-lookup"><span data-stu-id="c81cb-170">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c81cb-171">3</span><span class="sxs-lookup"><span data-stu-id="c81cb-171">3</span></span></p></td>
<td><p><span data-ttu-id="c81cb-172">9</span><span class="sxs-lookup"><span data-stu-id="c81cb-172">9</span></span></p></td>
<td><p><span data-ttu-id="c81cb-173">3 (1 pro VIP) + 9</span><span class="sxs-lookup"><span data-stu-id="c81cb-173">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c81cb-174">4</span><span class="sxs-lookup"><span data-stu-id="c81cb-174">4</span></span></p></td>
<td><p><span data-ttu-id="c81cb-175">12</span><span class="sxs-lookup"><span data-stu-id="c81cb-175">12</span></span></p></td>
<td><p><span data-ttu-id="c81cb-176">3 (1 pro VIP) + 12</span><span class="sxs-lookup"><span data-stu-id="c81cb-176">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c81cb-177">5</span><span class="sxs-lookup"><span data-stu-id="c81cb-177">5</span></span></p></td>
<td><p><span data-ttu-id="c81cb-178">15</span><span class="sxs-lookup"><span data-stu-id="c81cb-178">15</span></span></p></td>
<td><p><span data-ttu-id="c81cb-179">3 (1 pro VIP) + 15</span><span class="sxs-lookup"><span data-stu-id="c81cb-179">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="c81cb-180">IP-Adressen Anforderungen für skalierten konsolidierten Edge (einzelne IP-Adresse für alle Rollen)</span><span class="sxs-lookup"><span data-stu-id="c81cb-180">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c81cb-181">Anzahl der Edgeserver pro Pool</span><span class="sxs-lookup"><span data-stu-id="c81cb-181">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="c81cb-182">Anzahl der erforderlichen IP-Adressen lync Server 2013 (DNS Load Balanced)</span><span class="sxs-lookup"><span data-stu-id="c81cb-182">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="c81cb-183">Anzahl der erforderlichen IP-Adressen lync Server 2013 (Hardwarelastenausgleich)</span><span class="sxs-lookup"><span data-stu-id="c81cb-183">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c81cb-184">2</span><span class="sxs-lookup"><span data-stu-id="c81cb-184">2</span></span></p></td>
<td><p><span data-ttu-id="c81cb-185">2</span><span class="sxs-lookup"><span data-stu-id="c81cb-185">2</span></span></p></td>
<td><p><span data-ttu-id="c81cb-186">1 (1 pro VIP) + 2</span><span class="sxs-lookup"><span data-stu-id="c81cb-186">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c81cb-187">3</span><span class="sxs-lookup"><span data-stu-id="c81cb-187">3</span></span></p></td>
<td><p><span data-ttu-id="c81cb-188">3</span><span class="sxs-lookup"><span data-stu-id="c81cb-188">3</span></span></p></td>
<td><p><span data-ttu-id="c81cb-189">1 (1 pro VIP) + 3</span><span class="sxs-lookup"><span data-stu-id="c81cb-189">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c81cb-190">4</span><span class="sxs-lookup"><span data-stu-id="c81cb-190">4</span></span></p></td>
<td><p><span data-ttu-id="c81cb-191">4</span><span class="sxs-lookup"><span data-stu-id="c81cb-191">4</span></span></p></td>
<td><p><span data-ttu-id="c81cb-192">1 (1 pro VIP) + 4</span><span class="sxs-lookup"><span data-stu-id="c81cb-192">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c81cb-193">5</span><span class="sxs-lookup"><span data-stu-id="c81cb-193">5</span></span></p></td>
<td><p><span data-ttu-id="c81cb-194">5</span><span class="sxs-lookup"><span data-stu-id="c81cb-194">5</span></span></p></td>
<td><p><span data-ttu-id="c81cb-195">1 (1 pro VIP) + 5</span><span class="sxs-lookup"><span data-stu-id="c81cb-195">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c81cb-196">Die primären Entscheidungspunkte für die Topologie-Auswahl sind hohe Verfügbarkeit und Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="c81cb-196">The primary decision points for topology selection are high availability and load balancing.</span></span> <span data-ttu-id="c81cb-197">Die Voraussetzung für hohe Verfügbarkeit kann die Entscheidung über den Lastenausgleich beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="c81cb-197">The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="c81cb-198">_ *Höchste Verfügbarkeit*\* Wenn Sie eine höhere Verfügbarkeit benötigen, müssen Sie mindestens zwei Edgeserver in einem Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c81cb-198">_ *High availability*\*   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="c81cb-199">Ein einzelner Edge-Pool unterstützt bis zu zwölf Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="c81cb-199">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="c81cb-200">Wenn mehr Kapazität erforderlich ist, können Sie mehrere Edge-Pools bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c81cb-200">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="c81cb-201">In der Regel benötigen 10% einer bestimmten Nutzerbasis externen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="c81cb-201">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="c81cb-202">Mit dem Topology Builder können Sie bis zu zwanzig Edgeserver in einem einzigen Edge-Pool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c81cb-202">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="c81cb-203">Die getestete und unterstützte maximale Anzahl von Edgeserver in einem Pool ist zwölf, und der Topologie-Generator, der eine Zahl größer als zwölf zulässt, sollte nicht als implizierte Unterstützung für mehr als zwölf Edgeserver in einem einzigen Edge-Pool ausgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c81cb-203">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="c81cb-204">**Hardware Lastenausgleich**   Der Hardware Lastenausgleich wird für den Lastenausgleich von lync Server 2013-Edgeserver unterstützt, wenn öffentlich routingfähige IP-Adressen für die externen Edge-Schnittstellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c81cb-204">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="c81cb-205">Diese Vorgehensweise wird beispielsweise in Situationen verwendet, in denen ein Failover für eine der folgenden Anwendungen erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="c81cb-205">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="c81cb-206">Verbindung mit öffentlichen Chatdiensten</span><span class="sxs-lookup"><span data-stu-id="c81cb-206">Public IM connectivity</span></span>
    
      - <span data-ttu-id="c81cb-207">Föderation mit Unternehmen, auf denen Microsoft Office Communications Server 2007 oder Microsoft Office Communications Server 2007 R2 ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="c81cb-207">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="c81cb-208">Externer Zugriff auf Exchange 2007 Unified Messaging (um) oder Exchange 2010 um</span><span class="sxs-lookup"><span data-stu-id="c81cb-208">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="c81cb-209">Der DNS-Lastenausgleich für Exchange 2010 SP1 und höher wird für Exchange um unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c81cb-209">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="c81cb-210">Diese drei Anwendungen funktionieren weiterhin, sind aber nicht für den DNS-Lastenausgleich bekannt und stellen nur eine Verbindung mit dem ersten Edgeserver im Pool her.</span><span class="sxs-lookup"><span data-stu-id="c81cb-210">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool.</span></span> <span data-ttu-id="c81cb-211">Wenn dieser Server nicht verfügbar ist, schlägt die Verbindung fehl.</span><span class="sxs-lookup"><span data-stu-id="c81cb-211">If that server is unavailable, the connection will fail.</span></span> <span data-ttu-id="c81cb-212">Wenn beispielsweise mehrere Edgeserver in einem Pool bereitgestellt werden, um die Auslastung des Federated-Datenverkehrs zu behandeln, erhält nur ein Zugriffsproxy tatsächlich Datenverkehr, während die anderen Server im Leerlauf sind.</span><span class="sxs-lookup"><span data-stu-id="c81cb-212">For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c81cb-213">Die Verwendung des DNS-Lastenausgleichs wird empfohlen, wenn Sie mit Unternehmen mit lync Server 2010 und Office 365 oder Microsoft 365 eine Föderation verwenden.</span><span class="sxs-lookup"><span data-stu-id="c81cb-213">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Office 365 or Microsoft 365.</span></span> <span data-ttu-id="c81cb-214">Beachten Sie, dass es erhebliche Auswirkungen auf die Leistung gibt, wenn die meisten ihrer Verbundpartner Office Communications Server 2007 oder Office Communications Server 2007 R2 verwenden.</span><span class="sxs-lookup"><span data-stu-id="c81cb-214">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="c81cb-215"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="c81cb-215"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

