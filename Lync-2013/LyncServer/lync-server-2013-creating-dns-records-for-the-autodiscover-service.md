---
title: 'Lync Server 2013: Erstellen von DNS-Einträgen für den AutoErmittlungsdienst'
description: 'Lync Server 2013: Erstellen von DNS-Einträgen für den AutoErmittlungsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6903e6b07001289db8b65e8cc962e8d8db4b248b
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431512"
---
# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="d8670-103">Erstellen von DNS-Einträgen für den AutoErmittlungsdienst in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8670-103">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="d8670-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="d8670-104">

<span> </span></span></span>

<span data-ttu-id="d8670-105">_**Letztes Änderungsdatum des Themas:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="d8670-105">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="d8670-106">Für Ihre lync Mobile-Benutzer müssen Sie die AutoErmittlung aktivieren, und ein Teil davon umfasst das Erstellen einiger DNS-Einträge (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="d8670-106">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="d8670-107">Je nach Ihren Anforderungen benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d8670-107">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="d8670-108">Ein interner DNS-Eintrag zur Unterstützung von mobilen Benutzern, die im Netzwerk Ihrer Organisation eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="d8670-108">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="d8670-109">Ein externer oder öffentlicher DNS-Eintrag zur Unterstützung von mobilen Benutzern, die eine Verbindung mit dem Internet herstellen</span><span class="sxs-lookup"><span data-stu-id="d8670-109">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="d8670-110">Warum beides?</span><span class="sxs-lookup"><span data-stu-id="d8670-110">Why both?</span></span> <span data-ttu-id="d8670-111">Sie müssen sowohl einen internen DNS-Eintrag als auch einen externen DNS-Eintrag für jede SIP-Domäne erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8670-111">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="d8670-112">Die von Ihnen erstellten DNS-Einträge können entweder als (Host-) Datensätze oder als CNAME-Einträge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d8670-112">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="d8670-113">Um Ihnen zu helfen, führen wir die folgenden Schritte zum Erstellen dieser internen und externen DNS-Einträge aus.</span><span class="sxs-lookup"><span data-stu-id="d8670-113">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="d8670-114">Wenn Sie weitere Informationen zu den DNS-Anforderungen für mobile Benutzer benötigen, können Sie die [technischen Voraussetzungen für die Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)lesen.</span><span class="sxs-lookup"><span data-stu-id="d8670-114">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="d8670-115">Erstellen eines internen DNS-CNAME-Eintrags</span><span class="sxs-lookup"><span data-stu-id="d8670-115">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="d8670-116">Wenn Sie einen internen DNS-Eintrag erstellen möchten, müssen Sie sich bei einem DNS-Server in Ihrem Netzwerk mit einem Domänenkonto anmelden, das entweder ein Mitglied der Gruppe der Domänenadministratoren oder ein Mitglied der DnsAdmins-Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="d8670-116">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="d8670-117">Öffnen Sie das DNS-Administrator-Snap-in: Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d8670-117">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="d8670-118">Erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die Active Directory-Domäne, in der der lync Server 2013 Director-Pool und der Front-End-Pool installiert sind.</span><span class="sxs-lookup"><span data-stu-id="d8670-118">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="d8670-119">(Beispiel: contoso. local).</span><span class="sxs-lookup"><span data-stu-id="d8670-119">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="d8670-120">Überprüfen Sie, ob ein Host-a-Eintrag (AAAA für IPv6) für Ihren Director-Pool für einen internen DNS-Eintrag vorhanden ist, und geben Sie einen Host einen Eintrag für den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihres Director-Pools (beispielsweise lyncwebdir01. contoso. local) ein.</span><span class="sxs-lookup"><span data-stu-id="d8670-120">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="d8670-121">Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keinen Director-Pool, und Sie müssen den FQDN für Ihren Front-End-Pool oder sogar einen einzelnen Server-FQDN verwenden, wenn dies Ihr Setup ist.</span><span class="sxs-lookup"><span data-stu-id="d8670-121">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="d8670-122">Beachten Sie Folgendes: Überprüfen Sie, ob ein Host a (AAAA für IPv6)-Eintrag für Ihren Front-End-Pool für einen internen DNS-Eintrag vorhanden ist, wenn ein Host a (oder AAAA)-Eintrag für den internen Webdienst-FQDN für Ihren Front-End-Pool vorhanden ist (beispielsweise "lyncwebpool01. contoso. local").</span><span class="sxs-lookup"><span data-stu-id="d8670-122">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="d8670-123">Wenn dies nicht der Fall ist, müssen Sie den FQDN für den Front-End-Server oder den Standard Edition-Server notieren.</span><span class="sxs-lookup"><span data-stu-id="d8670-123">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="d8670-124">Sobald Sie wissen, welche Host A (oder AAAA)-Einträge vorhanden sind, erweitern Sie in der Konsolenstruktur Ihres DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d8670-124">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="d8670-125">Klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen, und klicken Sie dann auf **Neuer Alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="d8670-125">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="d8670-126">Geben Sie unter **Aliasname** den Namen lyncdiscoverinternal als Hostnamen für die interne URL des AutoErmittlungsdiensts ein.</span><span class="sxs-lookup"><span data-stu-id="d8670-126">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="d8670-127">Geben Sie im **vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Ziel Host** den internen Webdienst-FQDN für Ihren Director-Pool ein, oder suchen Sie nach ihm (beispielsweise lyncwebdir01. contoso. local), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8670-127">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="d8670-128">Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Lookupzone jeder SIP-Domäne erstellen, die Sie in ihrer lync Server 2013-Umgebung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d8670-128">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="d8670-129">Erstellen eines externen DNS-CNAME-Eintrags</span><span class="sxs-lookup"><span data-stu-id="d8670-129">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="d8670-130">Wenn Sie einen externen DNS-CNAME-Eintrag erstellen möchten, müssen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter herstellen, und führen Sie dann die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="d8670-130">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="d8670-131">Wir können nicht genau beschreiben, wohin Sie in der Umgebung Ihres DNS-Anbieters wechseln, da es verschiedene Methoden zur Verwaltung Ihres externen DNS geben kann, aber wir hoffen, dass diese Schritte hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="d8670-131">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="d8670-132">Melden Sie sich bei Ihrem externen DNS-Anbieter mit einem Konto an, das DNS-Einträge in dieser Umgebung erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="d8670-132">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="d8670-133">Für diese Umgebung sollte bereits eine SIP-Domäne erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d8670-133">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="d8670-134">Erweitern Sie die **Forward-Lookupzone** für diese SIP-Domäne, oder wählen Sie Sie auf andere Weise abhängig von der verwendeten externen DNS-Schnittstelle aus.</span><span class="sxs-lookup"><span data-stu-id="d8670-134">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="d8670-135">Sie sollten bereits einen Host-a-Eintrag (AAAA für IPv6) für Ihren Director-Pool (wie lyncwebexdir01.contoso.com) sehen, um sicherzustellen, dass er vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d8670-135">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="d8670-136">Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keinen Director-Pool.</span><span class="sxs-lookup"><span data-stu-id="d8670-136">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="d8670-137">Wenn dies der Fall ist, müssen Sie den FQDN Ihres Front-End-Pools verwenden, oder wenn Sie dies für einen einzelnen Server für Ihren Front-End Server oder Standard Edition-Server tun.</span><span class="sxs-lookup"><span data-stu-id="d8670-137">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="d8670-138">Außerdem müssen Sie sicherstellen, dass ein Host a (AAAA für IPv6)-Eintrag für den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihres externen Webdiensts für Ihren Front-End-Pool (wie lyncwebextpool01.contoso.com) vorhanden ist, oder einen FQDN für den FQDN Ihres Single Servers, wenn Sie über keinen Front-End-Pool verfügen.</span><span class="sxs-lookup"><span data-stu-id="d8670-138">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="d8670-139">Wie im vorherigen Schritt beschrieben, benötigen Sie diese unten, wenn Sie nicht über einen Director-Pool verfügen.</span><span class="sxs-lookup"><span data-stu-id="d8670-139">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="d8670-140">Wählen Sie jetzt im geeigneten Format für Ihren externen DNS-Anbieter die Option zum Erstellen eines **neuen Alias (CNAME)** (Dies kann eine Menüoption oder ein Link sein, abhängig vom Format des DNS-Anbieters).</span><span class="sxs-lookup"><span data-stu-id="d8670-140">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="d8670-141">Es sollte eine Form von **Alias Namen** -Textfeld geben wie beim internen DNS sollten Sie lyncdiscover als Hostnamen für die URL des externen AutoErmittlungsdiensts eingeben.</span><span class="sxs-lookup"><span data-stu-id="d8670-141">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="d8670-142">Es sollte auch eine Form eines **vollqualifizierten Domänennamens (Fully Qualified Domain Name, FQDN) für** das Textfeld "Zielhost" geben, hier können Sie den FQDN der externen Webdienste für Ihren Director-Pool eingeben (beispielsweise lyncwebexdir01.contoso.com) und dann auf OK klicken oder alle Aktionen im externen DNS ausführen, um die Erstellung dieses Eintrags zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="d8670-142">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="d8670-143">Wie in Schritt 4 oben zu sehen ist, müssen Sie, falls Sie nicht über einen Director-Pool verfügen, den FQDN des Front-End-Pools oder den von Ihnen eingerichteten Single-Server-FQDN verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8670-143">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="d8670-144">Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Lookupzone jeder SIP-Domäne erstellen, die in ihrer lync 2013-Umgebung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d8670-144">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="d8670-145">Erstellen eines internen DNS-A-Eintrags</span><span class="sxs-lookup"><span data-stu-id="d8670-145">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="d8670-146">Wenn Sie einen internen DNS-Eintrag erstellen möchten, melden Sie sich bei einem DNS-Server in Ihrem Netzwerk mit einem Domänenkonto an, das ein Mitglied der Gruppe "Domain Admins" oder ein Mitglied der DnsAdmins-Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="d8670-146">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="d8670-147">Öffnen Sie das DNS-Administrator-Snap-in: Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d8670-147">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="d8670-148">Für einen internen DNS-Eintrag erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre Active Directory-Domäne (beispielsweise contoso. local), in der der lync Server 2013 Director-Pool und der Front-End-Pool installiert sind.</span><span class="sxs-lookup"><span data-stu-id="d8670-148">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="d8670-149">Überprüfen Sie, ob ein Host-a-Eintrag (AAAA für IPv6) für Ihren Director-Pool für einen internen DNS-Eintrag vorhanden ist, und geben Sie einen Host einen Eintrag für den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihres Director-Pools (beispielsweise lyncwebdir01. contoso. local) ein.</span><span class="sxs-lookup"><span data-stu-id="d8670-149">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="d8670-150">Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keinen Director-Pool, und Sie müssen die IP-Adresse für Ihren Front-End-Pool oder sogar eine einzelne Server-IP-Adresse verwenden, wenn dies Ihr Setup ist.</span><span class="sxs-lookup"><span data-stu-id="d8670-150">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="d8670-151">Beachten Sie Folgendes: Überprüfen Sie, ob ein Host a (AAAA für IPv6)-Eintrag für Ihren Front-End-Pool für einen internen DNS-Eintrag vorhanden ist, wenn ein Host a (oder AAAA)-Eintrag für den internen Webdienst-FQDN für Ihren Front-End-Pool vorhanden ist (beispielsweise "lyncwebpool01. contoso. local").</span><span class="sxs-lookup"><span data-stu-id="d8670-151">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="d8670-152">Wenn dies nicht der Fall ist, müssen Sie die IP-Adresse für den Front-End-Server oder den Standard Edition-Server notieren.</span><span class="sxs-lookup"><span data-stu-id="d8670-152">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="d8670-153">Sobald Sie wissen, welche Host A (oder AAAA)-Einträge vorhanden sind, erweitern Sie in der Konsolenstruktur Ihres DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d8670-153">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="d8670-154">Klicken Sie mit der rechten Maustaste auf den SIP-Domänennamen, und klicken Sie dann auf **neuer Host (A oder AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="d8670-154">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="d8670-155">Geben Sie unter **Name** den Namen lyncdiscoverinternal als Hostname für die interne URL des AutoErmittlungsdiensts ein.</span><span class="sxs-lookup"><span data-stu-id="d8670-155">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="d8670-156">Geben Sie unter **IP-Adresse** die interne Webdienste-IP-Adresse des Directors ein (oder geben Sie bei Verwendung eines Load Balancer die virtuelle IP (VIP) des Director Load Balancer ein).</span><span class="sxs-lookup"><span data-stu-id="d8670-156">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="d8670-157">Wie in Schritt 4 oben festgestellt, müssen Sie möglicherweise die IP-Adresse des Front-End-Servers oder des Standard Edition-Servers eingeben, oder wenn Sie ein Lastenausgleichsmodul verwenden, geben Sie den VIP des Load Balancer des Front-End-Pools ein.</span><span class="sxs-lookup"><span data-stu-id="d8670-157">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="d8670-158">Klicken Sie auf **Host hinzufügen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8670-158">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="d8670-159">Wenn Sie einen zusätzlichen a-oder AAAA-Eintrag erstellen möchten, wiederholen Sie die Schritte 8 bis 10, und unter Berücksichtigung dessen, dass Sie neue Auto Ermittlungs-a-oder AAAA-Einträge in der Forward-Lookupzone jeder SIP-Domäne erstellen müssen, die in ihrer lync Server 2013-Umgebung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d8670-159">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="d8670-160">Wenn Sie mit dem Erstellen eines (für IPv6-, AAAA)-Datensatzes fertig sind, klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="d8670-160">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="d8670-161">Erstellen eines externen DNS-A-Eintrags</span><span class="sxs-lookup"><span data-stu-id="d8670-161">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="d8670-162">Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter her, und führen Sie dann die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="d8670-162">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="d8670-163">Wir können nicht genau beschreiben, wohin Sie in der Umgebung Ihres DNS-Anbieters wechseln, da es verschiedene Methoden zur Verwaltung Ihres externen DNS geben kann, aber wir hoffen, dass diese Schritte hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="d8670-163">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="d8670-164">Sie müssen als Konto angemeldet sein, das DNS-Einträge in dieser Umgebung erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="d8670-164">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="d8670-165">Erweitern Sie für einen externen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d8670-165">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="d8670-166">Erweitern Sie für einen externen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d8670-166">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="d8670-167">Sie sollten bereits einen Host-a-Eintrag (AAAA für IPv6) für Ihren Director-Pool (wie lyncwebexdir01.contoso.com) sehen, um sicherzustellen, dass er da ist und was die IP-Adresse ist.</span><span class="sxs-lookup"><span data-stu-id="d8670-167">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="d8670-168">Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keinen Director-Pool.</span><span class="sxs-lookup"><span data-stu-id="d8670-168">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="d8670-169">Wenn dies der Fall ist, müssen Sie die IP-Adresse des Front-End-Pools verwenden, oder wenn Sie dies für einen einzelnen Server für Ihren Front-End Server oder Standard Edition-Server tun.</span><span class="sxs-lookup"><span data-stu-id="d8670-169">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="d8670-170">Beachten Sie, dass sich Ihre Server auch hinter einem Load-Balancer oder einem Reverse-Proxy befinden können.</span><span class="sxs-lookup"><span data-stu-id="d8670-170">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="d8670-171">Notieren Sie sich die IP-Adressen, und führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="d8670-171">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="d8670-172">Außerdem müssen Sie sicherstellen, dass ein Host a (AAAA für IPv6)-Eintrag für den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihres externen Webdiensts für Ihren Front-End-Pool (wie lyncwebextpool01.contoso.com) vorhanden ist, oder eine IP-Adresse für Ihre Einzelserver-lync-Installation, wenn Sie über keinen Front-End-Pool verfügen.</span><span class="sxs-lookup"><span data-stu-id="d8670-172">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="d8670-173">Wie im vorherigen Schritt beschrieben, benötigen Sie diese unten, wenn Sie nicht über einen Director-Pool verfügen.</span><span class="sxs-lookup"><span data-stu-id="d8670-173">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="d8670-174">Wählen Sie jetzt im geeigneten Format für Ihren externen DNS-Anbieter die Option zum Erstellen eines **neuen Hosts a oder AAAA** (Dies kann eine Menüoption oder ein Link sein, abhängig vom Format des DNS-Anbieters).</span><span class="sxs-lookup"><span data-stu-id="d8670-174">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="d8670-175">Es sollte einen Ort geben, an dem Sie einen **Namen** eingeben können, und geben Sie lyncdiscover als Hostnamen für die URL des externen AutoErmittlungsdiensts ein.</span><span class="sxs-lookup"><span data-stu-id="d8670-175">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="d8670-176">Es sollte auch ein Textfeld für die **IP-Adresse** vorhanden sein, in dem Sie die IP-Adresse für Ihr Director-Pool (beispielsweise lyncwebexdir01.contoso.com) oder möglicherweise die IP-Adresse des Load Balancer Ihres Pools (oder eine Reverse-Proxy-IP-Adresse, die zum gleichen führt) eingeben und dann auf OK klicken oder die Aktion im externen DNS durchführen, um die Erstellung dieses Eintrags</span><span class="sxs-lookup"><span data-stu-id="d8670-176">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="d8670-177">Wie in Schritt 4 oben erwähnt, müssen Sie, falls Sie keinen Director-Pool besitzen, die IP-Adresse des Front-End-Pools oder die IP-Adresse des Einzelservers verwenden, die Sie eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="d8670-177">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="d8670-178">Sie müssen einen neuen Auto Ermittlungs-a-oder AAAA-Eintrag in der Forward-Lookupzone jeder SIP-Domäne erstellen, die in ihrer lync 2013-Umgebung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d8670-178">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

<span data-ttu-id="d8670-179"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="d8670-179"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

