---
title: DNS-Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen und NAT
description: DNS Summary – einzelner konsolidierter Edge mit privaten IP-Adressen mithilfe von NAT.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80402e04c1993fddda4d33ece22374e73175b5f5
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437693"
---
# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="f4aca-103">DNS-Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4aca-103">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="f4aca-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="f4aca-104">

<span> </span></span></span>

<span data-ttu-id="f4aca-105">_**Letztes Änderungsdatum des Themas:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="f4aca-105">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="f4aca-106">Die Anforderungen für den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ einfach.</span><span class="sxs-lookup"><span data-stu-id="f4aca-106">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="f4aca-107">Darüber hinaus sind viele Datensätze optional, je nachdem, wie Sie Clients mit lync 2013 konfigurieren und ob Sie die Föderation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f4aca-107">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="f4aca-108">Details zu den DNS-Anforderungen von lync 2013 finden Sie unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4aca-108">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="f4aca-109">Details zur automatischen Konfiguration von Clients, auf denen lync 2013 ausgeführt wird, wenn "Split-Brain DNS" nicht konfiguriert ist, finden Sie unter "automatische Konfiguration ohne Split-Brain DNS" unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4aca-109">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="f4aca-110">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die für die Unterstützung der einzelnen konsolidierten Edge-Topologie erforderlich sind, die in der einzelnen konsolidierten Edge-Topologie-Abbildung dargestellt ist.</span><span class="sxs-lookup"><span data-stu-id="f4aca-110">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="f4aca-111">Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration von lync 2013-und lync 2010-Clients erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f4aca-111">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="f4aca-112">Wenn Sie beabsichtigen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugehörigen automatischen Konfigurationseinträge nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f4aca-112">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="f4aca-113">Wichtig: Anforderungen des Edge-Server-Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="f4aca-113">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="f4aca-114">Um Routingprobleme zu vermeiden, stellen Sie sicher, dass Ihre Edgeserver mindestens zwei Netzwerkadapter aufweisen und dass das Standardgateway nur auf dem Netzwerkadapter festgesetzt ist, der der externen Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f4aca-114">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="f4aca-115">Beispielsweise würde das Standardgateway auf die externe Firewall verweisen (10.45.16.1), wie es in der einzigen konsolidierten Edge-Topologie-Abbildung in [einem konsolidierten Edge mit privaten IP-Adressen und NAT in lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f4aca-115">For example, as shown in the Single Consolidated Edge Topology figure in [Single consolidated edge with private IP addresses and NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), the default gateway would point to the external firewall (10.45.16.1).</span></span>

<span data-ttu-id="f4aca-116">Sie können zwei Netzwerkadapter auf dem Edgeserver wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f4aca-116">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="f4aca-117">**Netzwerkadapter 1 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="f4aca-117">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="f4aca-118">Interne Schnittstelle mit zugewiesenem 172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="f4aca-118">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="f4aca-119">Es wurde kein Standardgateway definiert.</span><span class="sxs-lookup"><span data-stu-id="f4aca-119">No default gateway is defined.</span></span>
    
    <span data-ttu-id="f4aca-120">Stellen Sie sicher, dass eine Route vom Netzwerk mit der Edge-internen Schnittstelle zu allen Netzwerken vorhanden ist, die Server mit lync Server 2013-oder lync Server 2013-Clients enthalten (beispielsweise von 172.25.33.0 bis 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="f4aca-120">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="f4aca-121">**Netzwerkadapter 2 (externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="f4aca-121">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="f4aca-122">Diesem Netzwerkadapter werden drei private IP-Adressen zugewiesen, beispielsweise 10.45.16.10 für Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 für AV Edge.</span><span class="sxs-lookup"><span data-stu-id="f4aca-122">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f4aca-123">Es ist jedoch möglich, eine einzige IP-Adresse für alle drei Edge-Service-Interfaces zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4aca-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="f4aca-124">Obwohl dadurch IP-Adressen gespeichert werden, sind für jeden Dienst unterschiedliche Portnummern erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f4aca-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="f4aca-125">Die Standardportnummer ist 443/TCP, wodurch sichergestellt wird, dass die meisten Remote Firewalls den Datenverkehr zulassen.</span><span class="sxs-lookup"><span data-stu-id="f4aca-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="f4aca-126">Das Ändern der Portwerte in (zum Beispiel) 5061/TCP für den Access-Edge, 444/TCP für den Webkonferenz-Edge und 443/TCP für den AV-Edge kann zu Problemen bei Remotebenutzern führen, bei denen eine Firewall, die Sie behindern, den Datenverkehr über 5061/TCP und 444/TCP nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="f4aca-126">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="f4aca-127">Darüber hinaus erleichtern drei unterschiedliche IP-Adressen die Problembehandlung, da Sie nach IP-Adressen filtern können.</span><span class="sxs-lookup"><span data-stu-id="f4aca-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="f4aca-128">Die IP-Adresse des Zugriffs Rands ist primär mit dem Standardgateway auf Integrated Router (10.45.16.1) eingestellt.</span><span class="sxs-lookup"><span data-stu-id="f4aca-128">Access Edge IP address is primary with default gateway set to integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="f4aca-129">Web Conferencing und A/V Edge-IP-Adressen sekundär.</span><span class="sxs-lookup"><span data-stu-id="f4aca-129">Web conferencing and A/V Edge IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="f4aca-130">Die Konfiguration des Edge-Servers mit zwei Netzwerkadaptern ist eine von zwei Optionen.</span><span class="sxs-lookup"><span data-stu-id="f4aca-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="f4aca-131">Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edge-Servers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4aca-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="f4aca-132">Der Hauptvorteil dieser Option ist ein eindeutiger Netzwerkadapter pro Edgeserver und eine potenziell genauere Datensammlung, wenn eine Problembehandlung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f4aca-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="f4aca-133">DNS-Einträge für einzelne konsolidierte Edges mit privaten IP-Adressen mit NAT (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="f4aca-133">DNS Records Required for Single Consolidated Edge with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4aca-134">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="f4aca-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f4aca-135">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="f4aca-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="f4aca-136">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="f4aca-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="f4aca-137">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="f4aca-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4aca-138">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="f4aca-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f4aca-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4aca-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f4aca-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="f4aca-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="f4aca-141">Access Edge External Interface (Contoso) wiederholen Sie diese nach Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="f4aca-141">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4aca-142">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="f4aca-142">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f4aca-143">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4aca-143">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f4aca-144">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="f4aca-144">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="f4aca-145">Externe Schnittstelle für Webkonferenz-Edge</span><span class="sxs-lookup"><span data-stu-id="f4aca-145">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4aca-146">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="f4aca-146">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f4aca-147">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4aca-147">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f4aca-148">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="f4aca-148">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="f4aca-149">Externe Schnittstelle A/V Edge</span><span class="sxs-lookup"><span data-stu-id="f4aca-149">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4aca-150">Externer DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="f4aca-150">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="f4aca-151">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4aca-151">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f4aca-152">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4aca-152">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f4aca-153">Access Edge-externe Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f4aca-153">Access Edge external interface.</span></span> <span data-ttu-id="f4aca-154">Erforderlich für die automatische Konfiguration von lync 2013-und lync 2010-Clients, um extern zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f4aca-154">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="f4aca-155">Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="f4aca-155">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4aca-156">Externer DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="f4aca-156">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="f4aca-157">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4aca-157">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f4aca-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4aca-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f4aca-159">Für die automatische DNS-Ermittlung von Verbundpartnern, die als "zugelassene SIP-Domäne" bezeichnet werden (genannt Enhanced Federation in früheren Versionen), ist eine externe SIP-Access-Edge-Schnittstelleerforderlich. Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="f4aca-159">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4aca-160">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="f4aca-160">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f4aca-161">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f4aca-161">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f4aca-162">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="f4aca-162">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="f4aca-163">Konsolidierte Edge-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4aca-163">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="f4aca-164">Die in der vorhergehenden Tabelle aufgelisteten Datensätze werden entweder mit einer <EM>.net</EM> -Erweiterung oder einer <EM>com</EM> -Erweiterung angezeigt, um die Zone hervorzuheben, in der Sie sich befinden müssen, wenn Sie nicht das DNS von Split-Brain verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4aca-164">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="f4aca-165">Wenn Sie das Split-Brain-DNS verwenden, befinden sich alle Datensätze in der gleichen <EM>com</EM> -Zone, wobei der einzige Unterschied darin besteht, ob Sie sich in der Version internal oder External DNS Zone befinden.</span><span class="sxs-lookup"><span data-stu-id="f4aca-165">If you are using split-brain DNS, all records would be in the same <EM>.com</EM> zone, with the only distinction being whether they are in the internal or external DNS zone version.</span></span> <span data-ttu-id="f4aca-166">Ausführliche Informationen finden Sie unter "Split-Brain DNS" unter <A href="lync-server-2013-determine-dns-requirements.md">Ermitteln der DNS-Anforderungen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f4aca-166">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="f4aca-167">Für den Verbund erforderliche Datensätze</span><span class="sxs-lookup"><span data-stu-id="f4aca-167">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4aca-168">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="f4aca-168">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f4aca-169">FQDN</span><span class="sxs-lookup"><span data-stu-id="f4aca-169">FQDN</span></span></th>
<th><span data-ttu-id="f4aca-170">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="f4aca-170">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="f4aca-171">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="f4aca-171">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4aca-172">Externer DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="f4aca-172">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="f4aca-173">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4aca-173">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f4aca-174">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4aca-174">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f4aca-175">Die externe SIP-Schnittstelle für die automatische DNS-Erkennung Ihres Verbandes zu anderen potenziellen Verbundpartnern ist erforderlich und wird als "zugelassene SIP-Domänen" bezeichnet (so genannte erweiterte Föderation in früheren Versionen). Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="f4aca-175">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="f4aca-176">Dieser SRV-Eintrag ist für Mobilität und das Clearinghaus für Push-Benachrichtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f4aca-176">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="f4aca-177">DNS-Zusammenfassung für erweiterbares Messaging und Anwesenheits Protokoll</span><span class="sxs-lookup"><span data-stu-id="f4aca-177">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4aca-178">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="f4aca-178">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f4aca-179">FQDN</span><span class="sxs-lookup"><span data-stu-id="f4aca-179">FQDN</span></span></th>
<th><span data-ttu-id="f4aca-180">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="f4aca-180">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="f4aca-181">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="f4aca-181">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4aca-182">Externer DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="f4aca-182">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="f4aca-183">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4aca-183">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f4aca-184">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4aca-184">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f4aca-185">XMPP-Proxy-externe Schnittstelle im Access Edge-Dienst oder Edge-Pool. Wiederholen Sie diese Schritte für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen der Kontakt mit XMPP-Kontakten über die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Website Richtlinie, in der sich der Benutzer befindet, oder die Benutzerrichtlinie, die auf den lync-aktivierten Benutzer angewendet wurde, zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="f4aca-185">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="f4aca-186">Eine zulässige XMPP-Domäne muss auch in der XMPP-Föderationspartner-Richtlinie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f4aca-186">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="f4aca-187">Weitere Informationen finden Sie in den Themen unter <strong>Siehe auch</strong> .</span><span class="sxs-lookup"><span data-stu-id="f4aca-187">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4aca-188">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="f4aca-188">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f4aca-189">xmpp.contoso.com (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="f4aca-189">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="f4aca-190">IP-Adresse des Zugriffs-Edgedienst auf dem Edgeserver oder Edge-Pool, der XMPP-Proxy hostet</span><span class="sxs-lookup"><span data-stu-id="f4aca-190">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="f4aca-191">Verweist auf den Access Edge-Dienst oder den Edge-Pool, der den XMPP-Proxydienst hostet.</span><span class="sxs-lookup"><span data-stu-id="f4aca-191">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="f4aca-192">In der Regel verweist der von Ihnen erstellte SRV-Eintrag auf diesen Host-Eintrag (a oder AAAA).</span><span class="sxs-lookup"><span data-stu-id="f4aca-192">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table><span data-ttu-id="f4aca-193">


</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="f4aca-193">


</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

