---
title: 'Lync Server 2013: Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT'
description: 'Lync Server 2013: Zertifikatzusammenfassung – skalierter konsolidierter Edge, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 41677dbd-3d07-498a-8591-df255b606647
ms:mtpsurl: https://technet.microsoft.com/library/Gg425921(v=OCS.15)
ms:contentKeyID: 48183959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d51beca2ee3627fc77c3132985193fd16e1ca987
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49435264"
---
# <a name="certificate-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="087d5-103">Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="087d5-103">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="087d5-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="087d5-104">

<span> </span></span></span>

<span data-ttu-id="087d5-105">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="087d5-105">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="087d5-106">Microsoft lync Server 2013 verwendet Zertifikate zur gegenseitigen Authentifizierung anderer Server und zum Verschlüsseln von Daten von Server zu Server und Server auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="087d5-106">Microsoft Lync Server 2013 uses certificates to mutually authenticate other servers and to encrypt data from server to server and server to client.</span></span> <span data-ttu-id="087d5-107">Für Zertifikate ist eine Namensübereinstimmung der DNS-Einträge (Domain Name System) erforderlich, die den Servern zugeordnet sind, sowie der Antragstellername (SN) und der Alternative Name (Subject Alternative Name, San) auf dem Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="087d5-107">Certificates require name matching of the domain name system (DNS) records associated with the servers and the subject name (SN) and subject alternative name (SAN) on the certificate.</span></span> <span data-ttu-id="087d5-108">Damit Server, DNS-Einträge und Zertifikat Einträge erfolgreich zugeordnet werden können, müssen Sie die vollqualifizierten Domänennamen für den vorgesehenen Server sorgfältig planen, wie Sie in DNS und den Einträgen SN und San auf dem Zertifikat registriert sind.</span><span class="sxs-lookup"><span data-stu-id="087d5-108">To successfully map servers, DNS records and certificate entries, you must carefully plan your intended server fully qualified domain names as registered in DNS and the SN and SAN entries on the certificate.</span></span>

<span data-ttu-id="087d5-109">Das Zertifikat, das den externen Schnittstellen des Edge-Servers zugewiesen ist, wird von einer öffentlichen Zertifizierungsstelle angefordert.</span><span class="sxs-lookup"><span data-stu-id="087d5-109">The certificate assigned to the external interfaces of the Edge Server is requested from a public certification authority (CA).</span></span> <span data-ttu-id="087d5-110">Öffentliche Zertifizierungsstellen, die den Erfolg bei der Bereitstellung von Zertifikaten für die Zwecke der Unified Communications bewiesen haben, sind im folgenden Artikel aufgeführt: [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) Wenn Sie das Zertifikat anfordern, können Sie die vom lync Server-Bereitstellungs-Assistenten generierte Zertifikatanforderung verwenden oder die Anforderung manuell oder durch einen Prozess erstellen, der von der öffentlichen Zertifizierungsstelle bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="087d5-110">Public CAs that have demonstrated success in supplying certificates for the purposes of Unified Communications are listed in the following article: [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) When requesting the certificate, you can use the certificate request generated by the Lync Server Deployment Wizard or create the request manually or by a process provided by the public CA.</span></span> <span data-ttu-id="087d5-111">Beim Zuweisen des Zertifikats wird das Zertifikat der Access-Edgedienst-Schnittstelle, der Webkonferenz-Edgedienst-Schnittstelle und dem Audio/Video-Authentifizierungsdienst zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="087d5-111">When assigning the certificate, the certificate is assigned to the Access Edge service interface, the Web Conferencing Edge service interface, and the Audio/Video Authentication service.</span></span> <span data-ttu-id="087d5-112">Der Audio-und Video Authentifizierungsdienst sollte nicht mit dem a/V-Edgedienst verwechselt werden, der kein Zertifikat zum Verschlüsseln der Audio-und Videodatenströme verwendet.</span><span class="sxs-lookup"><span data-stu-id="087d5-112">The Audio/Video Authentication service should not be confused with the A/V Edge service which does not use a certificate to encrypt the audio and video streams.</span></span> <span data-ttu-id="087d5-113">Die Schnittstelle für den internen Edgeserver kann ein Zertifikat von einer internen Zertifizierungsstelle (in Ihrer Organisation) oder einem Zertifikat einer öffentlichen Zertifizierungsstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="087d5-113">The internal Edge Server interface can use a certificate from an internal (to your organization) CA or a certificate from a public CA.</span></span> <span data-ttu-id="087d5-114">Das interne Schnittstellen Zertifikat verwendet nur SN und benötigt keine San-Einträge.</span><span class="sxs-lookup"><span data-stu-id="087d5-114">The internal interface certificate uses only the SN and does not need or use SAN entries.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="087d5-115">Die folgende Tabelle zeigt einen zweiten SIP-Eintrag (SIP.fabrikam.com) in der Liste Betreff-alternativer Name als Referenz.</span><span class="sxs-lookup"><span data-stu-id="087d5-115">The following table shows a second SIP entry (sip.fabrikam.com) in the subject alternative name list for reference.</span></span> <span data-ttu-id="087d5-116">Für jede SIP-Domäne in Ihrer Organisation müssen Sie einen entsprechenden FQDN hinzufügen, der in der Liste Zertifikat Antragsteller-alternativer Name aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="087d5-116">For each SIP domain in your organization, you need to add a corresponding FQDN listed in the certificate subject alternative name list.</span></span>



</div>

<div>

## <a name="scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat"></a><span data-ttu-id="087d5-117">Skalierter konsolidierter Edge, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT</span><span class="sxs-lookup"><span data-stu-id="087d5-117">Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="087d5-118">Komponente</span><span class="sxs-lookup"><span data-stu-id="087d5-118">Component</span></span></th>
<th><span data-ttu-id="087d5-119">Antragstellername</span><span class="sxs-lookup"><span data-stu-id="087d5-119">Subject name (SN)</span></span></th>
<th><span data-ttu-id="087d5-120">Subject Alternative Names (San)/Order</span><span class="sxs-lookup"><span data-stu-id="087d5-120">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="087d5-121">Kommentare</span><span class="sxs-lookup"><span data-stu-id="087d5-121">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="087d5-122">Skalierter konsolidierter Rand (externer Rand)</span><span class="sxs-lookup"><span data-stu-id="087d5-122">Scaled consolidated Edge (External Edge)</span></span></p></td>
<td><p><span data-ttu-id="087d5-123">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="087d5-123">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="087d5-124">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="087d5-124">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="087d5-125">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="087d5-125">sip.contoso.com</span></span></p>
<p><span data-ttu-id="087d5-126">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="087d5-126">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="087d5-127">Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle sein und muss über die Server-EKU und den Client-EKU verfügen, wenn öffentliche Chat Verbindungen mit AOL bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="087d5-127">Certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="087d5-128">Darüber hinaus muss der private Zertifikatschlüssel für skalierte Edgeserver exportierbar sein, und das Zertifikat und der private Schlüssel werden auf jeden Edgeserver kopiert.</span><span class="sxs-lookup"><span data-stu-id="087d5-128">Additionally, for scaled Edge Servers, the certificate private key must be exportable and the certificate and private key copied to each Edge Server.</span></span> <span data-ttu-id="087d5-129">Das Zertifikat wird den externen Edge-Schnittstellen für Folgendes zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="087d5-129">The certificate is assigned to the external Edge interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="087d5-130">Zugriffs-Edge</span><span class="sxs-lookup"><span data-stu-id="087d5-130">Access Edge</span></span></p></li>
<li><p><span data-ttu-id="087d5-131">Konferenz Kante</span><span class="sxs-lookup"><span data-stu-id="087d5-131">Conferencing Edge</span></span></p></li>
<li><p><span data-ttu-id="087d5-132">A/V-Edge</span><span class="sxs-lookup"><span data-stu-id="087d5-132">A/V Edge</span></span></p></li>
</ul>
<p><span data-ttu-id="087d5-133">Beachten Sie, dass Sans automatisch dem Zertifikat basierend auf ihren Definitionen im Topologie-Generator hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="087d5-133">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="087d5-134">Für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, fügen Sie nach Bedarf San-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="087d5-134">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="087d5-135">Der Antragstellername wird im San repliziert und muss für den korrekten Betrieb vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="087d5-135">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="087d5-136">Skalierter konsolidierter Rand (interner Rand)</span><span class="sxs-lookup"><span data-stu-id="087d5-136">Scaled consolidated Edge (Internal Edge)</span></span></p></td>
<td><p><span data-ttu-id="087d5-137">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="087d5-137">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="087d5-138">Kein San erforderlich</span><span class="sxs-lookup"><span data-stu-id="087d5-138">No SAN required</span></span></p></td>
<td><p><span data-ttu-id="087d5-139">Das Zertifikat kann von einer öffentlichen oder privaten Zertifizierungsstelle ausgestellt werden und muss die Server-EKU enthalten.</span><span class="sxs-lookup"><span data-stu-id="087d5-139">Certificate can be issued by a public or private CA, and must contain the server EKU.</span></span> <span data-ttu-id="087d5-140">Das Zertifikat wird der Schnittstelle für den internen Rand zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="087d5-140">The certificate is assigned to the internal Edge interface.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="087d5-141">Zusammenfassung des Zertifikats – öffentliche Instant Messaging-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="087d5-141">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="087d5-142">Komponente</span><span class="sxs-lookup"><span data-stu-id="087d5-142">Component</span></span></th>
<th><span data-ttu-id="087d5-143">Name des Antragstellers</span><span class="sxs-lookup"><span data-stu-id="087d5-143">Subject name</span></span></th>
<th><span data-ttu-id="087d5-144">Subject Alternative Names (San)/Order</span><span class="sxs-lookup"><span data-stu-id="087d5-144">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="087d5-145">Kommentare</span><span class="sxs-lookup"><span data-stu-id="087d5-145">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="087d5-146">Extern/Access-Edge</span><span class="sxs-lookup"><span data-stu-id="087d5-146">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="087d5-147">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="087d5-147">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="087d5-148">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="087d5-148">sip.contoso.com</span></span></p>
<p><span data-ttu-id="087d5-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="087d5-149">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="087d5-150">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="087d5-150">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="087d5-151">Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle sein und muss über die Server-EKU und den Client-EKU verfügen, wenn öffentliche Chat Verbindungen mit AOL bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="087d5-151">Certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="087d5-152">Das Zertifikat wird den externen Edge-Schnittstellen für Folgendes zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="087d5-152">The certificate is assigned to the external Edge interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="087d5-153">Zugriffs-Edge</span><span class="sxs-lookup"><span data-stu-id="087d5-153">Access Edge</span></span></p></li>
<li><p><span data-ttu-id="087d5-154">Konferenz Kante</span><span class="sxs-lookup"><span data-stu-id="087d5-154">Conferencing Edge</span></span></p></li>
<li><p><span data-ttu-id="087d5-155">A/V-Edge</span><span class="sxs-lookup"><span data-stu-id="087d5-155">A/V Edge</span></span></p></li>
</ul>
<p><span data-ttu-id="087d5-156">Beachten Sie, dass Sans automatisch dem Zertifikat basierend auf ihren Definitionen im Topologie-Generator hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="087d5-156">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="087d5-157">Für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, fügen Sie nach Bedarf San-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="087d5-157">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="087d5-158">Der Antragstellername wird im San repliziert und muss für den korrekten Betrieb vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="087d5-158">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="087d5-159">Zertifikatzusammenfassung für erweiterbares Messaging und Anwesenheits Protokoll</span><span class="sxs-lookup"><span data-stu-id="087d5-159">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="087d5-160">Komponente</span><span class="sxs-lookup"><span data-stu-id="087d5-160">Component</span></span></th>
<th><span data-ttu-id="087d5-161">Name des Antragstellers</span><span class="sxs-lookup"><span data-stu-id="087d5-161">Subject name</span></span></th>
<th><span data-ttu-id="087d5-162">Subject Alternative Names (San)/Order</span><span class="sxs-lookup"><span data-stu-id="087d5-162">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="087d5-163">Kommentare</span><span class="sxs-lookup"><span data-stu-id="087d5-163">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="087d5-164">Zuweisen des Zugriffs-Edgedienst des Edge-Servers oder Edge-Pools</span><span class="sxs-lookup"><span data-stu-id="087d5-164">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="087d5-165">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="087d5-165">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="087d5-166">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="087d5-166">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="087d5-167">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="087d5-167">sip.contoso.com</span></span></p>
<p><span data-ttu-id="087d5-168">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="087d5-168">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="087d5-169">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="087d5-169">xmpp.contoso.com</span></span></p>
<p><span data-ttu-id="087d5-170"><strong>\*.contoso.com</strong></span><span class="sxs-lookup"><span data-stu-id="087d5-170"><strong>\*.contoso.com</strong></span></span></p></td>
<td><p><span data-ttu-id="087d5-171">Die ersten drei San-Einträge sind die normalen San-Einträge für einen Full Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="087d5-171">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="087d5-172">Der contoso.com ist der Eintrag, der für den Verbund mit dem XMPP-Partner auf der Stammdomänen Ebene erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="087d5-172">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="087d5-173">Dieser Eintrag ermöglicht XMPP für alle Domänen mit dem Suffix \*. contoso.com.</span><span class="sxs-lookup"><span data-stu-id="087d5-173">This entry will allow XMPP for all domains with the suffix \*.contoso.com.</span></span></p></td>
</tr>
</tbody>
</table><span data-ttu-id="087d5-174">


</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="087d5-174">


</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

