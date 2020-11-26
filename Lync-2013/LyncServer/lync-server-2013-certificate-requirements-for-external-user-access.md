---
title: 'Lync Server 2013: Zertifikatanforderungen für den Zugriff durch externe Benutzer'
description: 'Lync Server 2013: Zertifikatanforderungen für den Zugriff durch externe Benutzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4701037aeba3ab6a4e51bf117efaa3aecc0f5084
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49435369"
---
# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="77da2-103">Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77da2-103">Certificate requirements for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="77da2-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="77da2-104">

<span> </span></span></span>

<span data-ttu-id="77da2-105">_**Letztes Änderungsdatum des Themas:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="77da2-105">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="77da2-106">Die Microsoft lync Server 2013-Kommunikationssoftware unterstützt die Verwendung eines einzelnen öffentlichen Zertifikats für Access-und Webkonferenz-Edge-externe Schnittstellen sowie den a/V-Authentifizierungsdienst.</span><span class="sxs-lookup"><span data-stu-id="77da2-106">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="77da2-107">Die interne Edge-Schnittstelle verwendet in der Regel ein privates Zertifikat, das von einer internen Zertifizierungsstelle ausgestellt wurde, kann aber auch ein öffentliches Zertifikat verwenden, vorausgesetzt, dass es von einer vertrauenswürdigen öffentlichen Zertifizierungsstelle stammt.</span><span class="sxs-lookup"><span data-stu-id="77da2-107">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="77da2-108">Der Reverseproxy in Ihrer Bereitstellung verwendet ein öffentliches Zertifikat und verschlüsselt die Kommunikation vom Reverse Proxy an Clients und den Reverse-Proxy an interne Server mithilfe von http (also Transport Layer Security over HTTP).</span><span class="sxs-lookup"><span data-stu-id="77da2-108">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="77da2-109">Im folgenden sind die Anforderungen für das öffentliche Zertifikat für Access-und Webkonferenz-Edge-externe Schnittstellen sowie der A/V-Authentifizierungsdienst:</span><span class="sxs-lookup"><span data-stu-id="77da2-109">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="77da2-110">Das Zertifikat muss von einer genehmigten öffentlichen Zertifizierungsstelle ausgestellt werden, die den alternativen Antragstellernamen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77da2-110">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="77da2-111">Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 929395, "Unified Communications Certificate Partners für Exchange Server und für Communications Server" unter [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="77da2-111">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="77da2-112">Wenn das Zertifikat in einem Edge-Pool verwendet wird, muss es als exportierbar erstellt werden, wobei auf jedem Edgeserver im Edge-Pool dasselbe Zertifikat verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="77da2-112">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool.</span></span> <span data-ttu-id="77da2-113">Die Anforderung des exportierbaren privaten Schlüssels beruht auf dem A/V-Authentifizierungsdienst, bei dem derselbe private Schlüssel auf allen Edgeserver im Pool verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="77da2-113">The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="77da2-114">Wenn Sie die Verfügbarkeit für Ihre Audio-und Video Dienste maximieren möchten, überprüfen Sie die Zertifikatanforderungen für die Implementierung eines entkoppelte a/v-Edgedienst Zertifikats (d. h. ein separates a/v-Edgedienst Zertifikat aus den anderen externen Edge-Zertifikat Zwecken).</span><span class="sxs-lookup"><span data-stu-id="77da2-114">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="77da2-115">Ausführliche Informationen finden Sie unter [Änderungen in lync Server 2013, die Auswirkungen auf die Planung von Edge](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)-Servern haben, [Planen von Edgeserver-Zertifikaten in lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) und bereit [Stellen von AV-und OAuth-Zertifikaten in lync Server 2013 mithilfe von-Rolle in CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span><span class="sxs-lookup"><span data-stu-id="77da2-115">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="77da2-116">Der Antragstellername des Zertifikats ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Access Edge Service oder das Hardware-Lastenausgleichsmodul VIP (beispielsweise Access.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="77da2-116">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="77da2-117">).</span><span class="sxs-lookup"><span data-stu-id="77da2-117">).</span></span> <span data-ttu-id="77da2-118">Der Name des Antragstellers darf kein Platzhalterzeichen aufweisen, er muss ein expliziter Name sein.</span><span class="sxs-lookup"><span data-stu-id="77da2-118">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77da2-119">Bei lync Server 2013 ist dies nicht mehr erforderlich, wird jedoch weiterhin für die Kompatibilität mit Office Communications Server empfohlen.</span><span class="sxs-lookup"><span data-stu-id="77da2-119">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="77da2-120">Die Liste Subject Alternative Name enthält die FQDNs der folgenden:</span><span class="sxs-lookup"><span data-stu-id="77da2-120">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="77da2-121">Die externe Schnittstelle für den Access Edge-Dienst oder das Hardwarelastenausgleich-VIP-Element (beispielsweise SIP.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="77da2-121">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="77da2-122">Auch wenn der Name des Zertifikat Antragstellers mit dem FQDN des Access-Edge identisch ist, muss der Alternative Subjektname auch den Access Edge-FQDN enthalten, da Transport Layer Security (TLS) den Antragstellernamen ignoriert und die alternativen Subjektnamen Einträge für die Überprüfung verwendet.</span><span class="sxs-lookup"><span data-stu-id="77da2-122">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="77da2-123">Die externe Schnittstelle für Web Conferencing Edge oder Hardware Load Balancer VIP (beispielsweise webcon.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="77da2-123">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="77da2-124">Wenn Sie die automatische Konfiguration oder Föderation des Clients verwenden, schließen Sie auch alle in Ihrem Unternehmen verwendeten SIP-Domänen-FQDNs ein (beispielsweise SIP.contoso.com, SIP.fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="77da2-124">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="77da2-125">Der A/V-Edgedienst verwendet nicht den Namen des Antragstellers oder die Einträge des alternativen betreffs.</span><span class="sxs-lookup"><span data-stu-id="77da2-125">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77da2-126">Die Reihenfolge der FQDNs in der Liste der alternativen Subjektnamen spielt keine Rolle.</span><span class="sxs-lookup"><span data-stu-id="77da2-126">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="77da2-127">Wenn Sie mehrere Edgeserver mit Lastenausgleich an einer Website bereitstellen, muss das auf jedem Edgeserver installierte a/V-Authentifizierungsdienst Zertifikat von der gleichen Zertifizierungsstelle sein und denselben privaten Schlüssel verwenden.</span><span class="sxs-lookup"><span data-stu-id="77da2-127">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key.</span></span> <span data-ttu-id="77da2-128">Beachten Sie, dass der private Schlüssel des Zertifikats exportierbar sein muss, unabhängig davon, ob er auf einem Edgeserver oder auf vielen Edgeserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="77da2-128">Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers.</span></span> <span data-ttu-id="77da2-129">Sie muss auch exportierbar sein, wenn Sie das Zertifikat von einem anderen Computer als dem Edgeserver anfordern.</span><span class="sxs-lookup"><span data-stu-id="77da2-129">It must also be exportable if you request the certificate from any computer other than the Edge Server.</span></span> <span data-ttu-id="77da2-130">Da der A/V-Authentifizierungsdienst den Antragstellernamen oder den alternativen Antragstellernamen nicht verwendet, können Sie das Access-Edge-Zertifikat wieder verwenden, sofern die Anforderungen für den Antragstellernamen und den alternativen Antragstellernamen für den Access-Edge und den Webkonferenz-Edge erfüllt sind und der private Schlüssel des Zertifikats exportierbar ist.</span><span class="sxs-lookup"><span data-stu-id="77da2-130">Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="77da2-131">Voraussetzungen für das private (oder öffentliche) Zertifikat, das für die Edge-interne Schnittstelle verwendet wird, sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="77da2-131">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="77da2-132">Das Zertifikat kann von einer internen Zertifizierungsstelle oder einer genehmigten öffentlichen Zertifikat Zertifizierungsstelle ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="77da2-132">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="77da2-133">Der Antragstellername des Zertifikats entspricht in der Regel dem FQDN des Edge-internen Interfaces oder dem Hardware Load Balancer VIP (beispielsweise lsedge.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="77da2-133">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com).</span></span> <span data-ttu-id="77da2-134">Sie können jedoch ein Platzhalterzertifikat auf dem internen Rand verwenden.</span><span class="sxs-lookup"><span data-stu-id="77da2-134">However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="77da2-135">Es ist keine Liste der alternativen Betreff-Namen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77da2-135">No subject alternative name list is required.</span></span>

<span data-ttu-id="77da2-136">Der Reverse-Proxy in ihren Bereitstellungsdienst Anforderungen für:</span><span class="sxs-lookup"><span data-stu-id="77da2-136">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="77da2-137">Zugriff externer Benutzer auf Besprechungsinhalte für Besprechungen</span><span class="sxs-lookup"><span data-stu-id="77da2-137">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="77da2-138">Zugriff durch externe Benutzer zum Erweitern und Anzeigen von Mitgliedern von Verteilergruppen</span><span class="sxs-lookup"><span data-stu-id="77da2-138">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="77da2-139">Zugriff externer Benutzer auf herunterladbare Dateien aus dem Adressbuchdienst</span><span class="sxs-lookup"><span data-stu-id="77da2-139">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="77da2-140">Zugriff externer Benutzer auf den lync Web App-Client</span><span class="sxs-lookup"><span data-stu-id="77da2-140">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="77da2-141">Zugriff externer Benutzer auf die Webseite "Einstellungen für Einwahlkonferenzen"</span><span class="sxs-lookup"><span data-stu-id="77da2-141">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="77da2-142">Zugriff externer Benutzer auf den standortinformationsdienst</span><span class="sxs-lookup"><span data-stu-id="77da2-142">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="77da2-143">Zugriff auf externe Geräte für den Geräteaktualisierungsdienst und Abrufen von Updates</span><span class="sxs-lookup"><span data-stu-id="77da2-143">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="77da2-144">Der Reverse-Proxy veröffentlicht die URLs der internen Server-Webkomponenten.</span><span class="sxs-lookup"><span data-stu-id="77da2-144">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="77da2-145">Die Webkomponenten-URLs werden auf dem Director, Front-End-Server oder Front-End-Pool als **externe Webdienste** im Topologie-Generator definiert.</span><span class="sxs-lookup"><span data-stu-id="77da2-145">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="77da2-146">Platzhaltereinträge werden im Feld Subject Alternative Name des dem Reverse-Proxy zugewiesenen Zertifikats unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77da2-146">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="77da2-147">Details zum Konfigurieren der Zertifikatanforderung für den Reverseproxy finden Sie unter [anfordern und Konfigurieren eines Zertifikats für den Reverse http-Proxy in lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="77da2-147">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="77da2-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77da2-148">See Also</span></span>


[<span data-ttu-id="77da2-149">Unterstützung von Platzhalterzertifikaten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77da2-149">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

<span data-ttu-id="77da2-150"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="77da2-150"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

