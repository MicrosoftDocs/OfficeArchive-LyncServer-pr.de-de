---
title: 'Lync Server 2013: Konfigurieren von DNS für die AutoErmittlung'
description: 'Lync Server 2013: Konfigurieren von DNS für die AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98a56cf3aa260bcbec9099e65958a9b17c3eaf26
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433185"
---
# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="8cdac-103">Konfigurieren von DNS für die AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cdac-103">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="8cdac-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="8cdac-104">

<span> </span></span></span>

<span data-ttu-id="8cdac-105">_**Letztes Änderungsdatum des Themas:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="8cdac-105">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="8cdac-106">Um die AutoDiscovery für lync-Clients zu unterstützen, müssen Sie die folgenden DNS-Einträge (Domain Name System) erstellen:</span><span class="sxs-lookup"><span data-stu-id="8cdac-106">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="8cdac-107">Ein interner DNS-Eintrag zur Unterstützung von lync-Clients, die innerhalb des Netzwerks Ihrer Organisation eine Verbindung herstellen</span><span class="sxs-lookup"><span data-stu-id="8cdac-107">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="8cdac-108">Ein externer oder öffentlicher DNS-Eintrag zur Unterstützung von lync-Clients, die eine Verbindung mit dem Internet herstellen</span><span class="sxs-lookup"><span data-stu-id="8cdac-108">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="8cdac-109">Sie müssen einen internen DNS-Eintrag und einen externen DNS-Eintrag für jede SIP-Domäne erstellen.</span><span class="sxs-lookup"><span data-stu-id="8cdac-109">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="8cdac-110">Bei den DNS-Einträgen kann es sich um eine (Host-) oder CNAME-Einträge handeln, basierend auf ihrer Möglichkeit zum Erstellen neuer Zertifikate mit dem zusätzlichen Subject-Namen (Alternate Name, San).</span><span class="sxs-lookup"><span data-stu-id="8cdac-110">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="8cdac-111">Wenn Sie nicht in der Lage sind, ein neues externes (öffentliches) Zertifikat mit dem lyncdiscover anzufordern und bereitzustellen.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="8cdac-111">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\></span></span> <span data-ttu-id="8cdac-112">San verwenden Sie das Verfahren für die Verwendung von http/TCP-Port 80.</span><span class="sxs-lookup"><span data-stu-id="8cdac-112">SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="8cdac-113">In den folgenden Verfahren wird beschrieben, wie interne und externe DNS-Einträge erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8cdac-113">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="8cdac-114">So erstellen Sie DNS-CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="8cdac-114">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="8cdac-115">Melden Sie sich wie folgt bei einem DNS-Server an:</span><span class="sxs-lookup"><span data-stu-id="8cdac-115">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="8cdac-116">Wenn Sie einen internen DNS-Eintrag erstellen möchten, melden Sie sich bei einem DNS-Server in Ihrem Netzwerk als Mitglied der Gruppe der Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="8cdac-116">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="8cdac-117">Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter her.</span><span class="sxs-lookup"><span data-stu-id="8cdac-117">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="8cdac-118">Öffnen Sie das DNS-Administrator-Snap-in: Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8cdac-118">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="8cdac-119">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8cdac-119">Do one of the following:</span></span>
    
      - <span data-ttu-id="8cdac-120">Erweitern Sie für einen internen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre Active Directory-Domäne (beispielsweise "contoso. local").</span><span class="sxs-lookup"><span data-stu-id="8cdac-120">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8cdac-121">Diese Domäne ist die Active Directory-Domäne, in der der lync Server 2013 &nbsp; Director-Pool und der Front-End-Pool installiert sind.</span><span class="sxs-lookup"><span data-stu-id="8cdac-121">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="8cdac-122">Erweitern Sie für einen externen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8cdac-122">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="8cdac-123">Stellen Sie sicher, dass für Ihren Director-Pool wie folgt ein Host-a-Eintrag vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="8cdac-123">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="8cdac-124">Bei einem internen DNS-Eintrag sollte ein Host-a-Eintrag für den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihres Director-Pools (beispielsweise lyncwebdir01. contoso. local) vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="8cdac-124">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="8cdac-125">Bei einem externen DNS-Eintrag sollte ein Host-a-Eintrag für den FQDN externer Webdienste für Ihren Director-Pool vorhanden sein (beispielsweise lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8cdac-125">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="8cdac-126">Stellen Sie sicher, dass für Ihren Front-End-Pool wie folgt ein Host-a-Eintrag vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="8cdac-126">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="8cdac-127">Bei einem internen DNS-Eintrag sollte ein Host-a-Eintrag für den internen Webdienst-FQDN für Ihren Front-End-Pool vorhanden sein (beispielsweise "lyncwebpool01. contoso. local").</span><span class="sxs-lookup"><span data-stu-id="8cdac-127">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="8cdac-128">Bei einem externen DNS-Eintrag sollte ein Host-a-Eintrag für den FQDN externer Dienste für den Front-End-Pool vorhanden sein (beispielsweise lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8cdac-128">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="8cdac-129">Erweitern Sie für einen internen DNS-Eintrag in der Konsolenstruktur Ihres DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8cdac-129">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8cdac-130">Wenn Sie einen externen DNS-Eintrag erstellen, werden <STRONG>Forward-Lookupzonen</STRONG> für Ihre SIP-Domäne bereits aus Schritt 3 erweitert.</span><span class="sxs-lookup"><span data-stu-id="8cdac-130">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="8cdac-131">Klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen, und klicken Sie dann auf **Neuer Alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="8cdac-131">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="8cdac-132">Geben Sie unter **Alias Name** eine der folgenden Optionen ein:</span><span class="sxs-lookup"><span data-stu-id="8cdac-132">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="8cdac-133">Geben Sie für einen internen DNS-Eintrag lyncdiscoverinternal als Hostname für die interne URL des AutoErmittlungsdiensts ein.</span><span class="sxs-lookup"><span data-stu-id="8cdac-133">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="8cdac-134">Geben Sie für einen externen DNS-Eintrag lyncdiscover als Hostnamen für die URL des externen AutoErmittlungsdiensts ein.</span><span class="sxs-lookup"><span data-stu-id="8cdac-134">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="8cdac-135">Führen Sie im **vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Ziel Host** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="8cdac-135">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="8cdac-136">Geben Sie für einen internen DNS-Eintrag den internen FQDN des Webdiensts für Ihren Director-Pool ein, oder suchen Sie nach ihm (beispielsweise lyncwebdir01. contoso. local), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cdac-136">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="8cdac-137">Geben Sie für einen externen DNS-Eintrag den FQDN externer Webdienste für Ihren Director-Pool ein, oder suchen Sie nach ihm (beispielsweise lyncwebextdir.contoso.com), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cdac-137">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8cdac-138">Wenn Sie keinen Director verwenden, verwenden Sie den FQDN für interne und externe Webdienste für den Front-End-Pool oder für einen einzelnen Server den FQDN für den Front-End-Server oder den Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="8cdac-138">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8cdac-139">Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Lookupzone jeder SIP-Domäne erstellen, die Sie in ihrer lync Server 2013-Umgebung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8cdac-139">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="8cdac-140">So erstellen Sie DNS-A-Einträge</span><span class="sxs-lookup"><span data-stu-id="8cdac-140">To create DNS A records</span></span>

1.  <span data-ttu-id="8cdac-141">Melden Sie sich wie folgt bei einem DNS-Server an:</span><span class="sxs-lookup"><span data-stu-id="8cdac-141">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="8cdac-142">Wenn Sie einen internen DNS-Eintrag erstellen möchten, melden Sie sich bei einem DNS-Server in Ihrem Netzwerk als Mitglied der Gruppe der Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="8cdac-142">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="8cdac-143">Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter oder einem externen DNS-Server her.</span><span class="sxs-lookup"><span data-stu-id="8cdac-143">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="8cdac-144">Öffnen Sie das DNS-Administrator-Snap-in: Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8cdac-144">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="8cdac-145">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8cdac-145">Do one of the following:</span></span>
    
      - <span data-ttu-id="8cdac-146">Erweitern Sie für einen internen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre Active Directory-Domäne (beispielsweise "contoso. local").</span><span class="sxs-lookup"><span data-stu-id="8cdac-146">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8cdac-147">Diese Domäne ist die Active Directory-Domäne, in der der lync Server 2013 &nbsp; Director-Pool und der Front-End-Pool installiert sind.</span><span class="sxs-lookup"><span data-stu-id="8cdac-147">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="8cdac-148">Erweitern Sie für einen externen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8cdac-148">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="8cdac-149">Überprüfen Sie, ob ein Host-a-Eintrag (für IPv6, AAAA) für Ihren Director-Pool wie folgt vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="8cdac-149">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="8cdac-150">Für einen internen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den internen Webdienst-FQDN für Ihren Director-Pool vorhanden sein (beispielsweise "lyncwebdir01. contoso. local").</span><span class="sxs-lookup"><span data-stu-id="8cdac-150">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="8cdac-151">Bei einem externen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den FQDN externer Webdienste für Ihren Director-Pool vorhanden sein (beispielsweise lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8cdac-151">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="8cdac-152">Überprüfen Sie, ob ein Host-a-Eintrag (für IPv6, AAAA) für Ihren Front-End-Pool wie folgt vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="8cdac-152">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="8cdac-153">Für einen internen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den internen Webdienst-FQDN für Ihren Front-End-Pool vorhanden sein (beispielsweise "lyncwebpool01. contoso. local").</span><span class="sxs-lookup"><span data-stu-id="8cdac-153">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="8cdac-154">Bei einem externen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den FQDN externer Dienste für Ihren Front-End-Pool vorhanden sein (beispielsweise lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8cdac-154">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="8cdac-155">Erweitern Sie für einen internen DNS-Eintrag in der Konsolenstruktur Ihres DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8cdac-155">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8cdac-156">Wenn Sie einen externen DNS-Eintrag erstellen, werden <STRONG>Forward-Lookupzonen</STRONG> für Ihre SIP-Domäne bereits aus Schritt 3 erweitert.</span><span class="sxs-lookup"><span data-stu-id="8cdac-156">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="8cdac-157">Klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen, und klicken Sie dann auf **neuer Host (A oder AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="8cdac-157">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="8cdac-158">Geben Sie unter **Name** den Namen des Hosts wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="8cdac-158">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="8cdac-159">Geben Sie für einen internen DNS-Eintrag lyncdiscoverinternal als Hostname für die interne URL des AutoErmittlungsdiensts ein.</span><span class="sxs-lookup"><span data-stu-id="8cdac-159">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="8cdac-160">Geben Sie für einen externen DNS-Eintrag lyncdiscover als Hostnamen für die URL des externen AutoErmittlungsdiensts ein.</span><span class="sxs-lookup"><span data-stu-id="8cdac-160">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8cdac-161">Der Domänenname wird aus der Zone übernommen, in der der Datensatz definiert ist und daher nicht als Teil des A-Eintrags eingegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="8cdac-161">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="8cdac-162">Geben Sie unter **IP-Adresse** die IP-Adresse wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="8cdac-162">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="8cdac-163">Geben Sie für einen internen DNS-Eintrag die interne Webdienste-IP-Adresse des Directors ein (oder, wenn Sie ein Lastenausgleichsmodul verwenden, die virtuelle IP (VIP) des Director Load Balancer).</span><span class="sxs-lookup"><span data-stu-id="8cdac-163">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8cdac-164">Wenn Sie keinen Director verwenden, geben Sie die IP-Adresse des Front-End-Servers oder des Standard Edition-Servers ein, oder geben Sie bei Verwendung eines Load Balancer den VIP des Load Balancer des Front-End-Pools ein.</span><span class="sxs-lookup"><span data-stu-id="8cdac-164">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="8cdac-165">Geben Sie für einen externen DNS-Eintrag die externe oder öffentliche IP-Adresse des Reverse-Proxys ein.</span><span class="sxs-lookup"><span data-stu-id="8cdac-165">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="8cdac-166">Klicken Sie auf **Host hinzufügen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cdac-166">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="8cdac-167">Wenn Sie einen zusätzlichen A-Eintrag erstellen möchten, wiederholen Sie die Schritte 8 bis 10.</span><span class="sxs-lookup"><span data-stu-id="8cdac-167">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8cdac-168">Sie müssen ein neues lyncdiscover-und lyncdiscoverinternal-Datensätze in der Forward-Lookupzone jeder SIP-Domäne erstellen, die Sie in ihrer lync Server 2013-Umgebung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8cdac-168">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="8cdac-169">Wenn Sie mit dem Erstellen eines (für IPv6-, AAAA)-Datensatzes fertig sind, klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="8cdac-169">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

<span data-ttu-id="8cdac-170"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="8cdac-170"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

