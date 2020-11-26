---
title: 'Lync Server 2013: DNS-Anforderungen für einfache URLs'
description: 'Lync Server 2013: DNS-Anforderungen für einfache URLs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84cc893fc06e9c57dcad6506d692b4484827b56a
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437759"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="0a481-103">DNS-Anforderungen für einfache URLs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a481-103">DNS requirements for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="0a481-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="0a481-104">

<span> </span></span></span>

<span data-ttu-id="0a481-105">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0a481-105">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0a481-106">Lync Server 2013 unterstützt einfache URLs, mit denen Sie Ihren Benutzern die Teilnahme an Besprechungen erleichtern und die Verwaltung von lync Server-Verwaltungstools für Ihre Administratoren einfacher machen können.</span><span class="sxs-lookup"><span data-stu-id="0a481-106">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="0a481-107">Ausführliche Informationen zu einfachen URLs finden Sie unter [Planen einfacher URLs in lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="0a481-107">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="0a481-108">Lync Server unterstützt die folgenden drei einfachen URLs: Besprechung, Einwahl und Administrator. Sie müssen einfache URLs für Meet und Dial-in einrichten, und die einfache Administrator-URL ist optional.</span><span class="sxs-lookup"><span data-stu-id="0a481-108">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="0a481-109">Die DNS-Einträge (Domain Name System), die Sie zur Unterstützung einfacher URLs benötigen, hängen davon ab, wie Sie diese einfachen URLs definiert haben und ob Sie die Disaster Recovery für einfache URLs unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="0a481-109">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="0a481-110">Einfache URL-Option 1</span><span class="sxs-lookup"><span data-stu-id="0a481-110">Simple URL Option 1</span></span>

<span data-ttu-id="0a481-111">In Option 1 erstellen Sie für jede einfache URL eine neue Basis-URL.</span><span class="sxs-lookup"><span data-stu-id="0a481-111">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="0a481-112">Wenn ein Benutzer auf einen einfachen URL-Besprechungslink klickt, wird der Server, auf dem der DNS-a-Eintrag aufgelöst wird, ermittelt, um die richtige Client Software zu starten.</span><span class="sxs-lookup"><span data-stu-id="0a481-112">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start.</span></span> <span data-ttu-id="0a481-113">Nachdem die Client Software gestartet wurde, kommuniziert sie automatisch mit dem Pool, in dem die Konferenz gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="0a481-113">After the client software is started, it automatically communicates with the pool where the conference is hosted.</span></span> <span data-ttu-id="0a481-114">Auf diese Weise werden Benutzer an den entsprechenden Server für Besprechungsinhalte weitergeleitet, unabhängig davon, in welchem Server oder Pool die einfache URL-DNS-A-Einträge aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="0a481-114">This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="0a481-115">Einfache URL-Option 1</span><span class="sxs-lookup"><span data-stu-id="0a481-115">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a481-116"><strong>Einfache URL</strong></span><span class="sxs-lookup"><span data-stu-id="0a481-116"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="0a481-117"><strong>Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="0a481-117"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a481-118">Treffen</span><span class="sxs-lookup"><span data-stu-id="0a481-118">Meet</span></span></p></td>
<td><p><span data-ttu-id="0a481-119"> https://meet.contoso.comusw. https://meet.fabrikam.com (eine für jede SIP-Domäne in Ihrer Organisation)</span><span class="sxs-lookup"><span data-stu-id="0a481-119">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a481-120">Einwahl</span><span class="sxs-lookup"><span data-stu-id="0a481-120">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a481-121">Admin</span><span class="sxs-lookup"><span data-stu-id="0a481-121">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0a481-122">Wenn Sie Option 1 verwenden, müssen Sie Folgendes definieren:</span><span class="sxs-lookup"><span data-stu-id="0a481-122">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="0a481-123">Für jede einfache URL-Besprechung benötigen Sie einen DNS-a-Eintrag, der die URL zur IP-Adresse des Directors auflöst, wenn Sie eine bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="0a481-123">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="0a481-124">Andernfalls sollte Sie in die IP-Adresse des Load Balancer eines Front-End-Pools aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="0a481-124">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="0a481-125">Wenn Sie keinen Pool bereitgestellt haben und eine Standard Edition-Server Bereitstellung verwenden, muss der DNS-a-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="0a481-125">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="0a481-126">Wenn in Ihrer Organisation mehr als eine SIP-Domäne vorhanden ist und Sie diese Option verwenden, müssen Sie für jede SIP-Domäne einfache URLs erstellen, und für jede einfache URL muss ein DNS-a-Eintrag erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0a481-126">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="0a481-127">Wenn Sie beispielsweise sowohl contoso.com als auch fabrikam.com haben, erstellen Sie DNS-A-Einträge für beide https://meet.contoso.com und https://meet.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="0a481-127">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="0a481-128">Wenn Sie aber über mehrere SIP-Domänen verfügen und den DNS-Eintrag und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten, verwenden Sie Option 3 wie weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a481-128">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="0a481-129">Für die einfache Dial-in-URL benötigen Sie einen DNS-a-Eintrag, der die URL zur IP-Adresse des Directors auflöst, wenn Sie eine bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="0a481-129">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="0a481-130">Andernfalls sollte Sie in die IP-Adresse des Load Balancer eines Front-End-Pools aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="0a481-130">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="0a481-131">Wenn Sie keinen Pool bereitgestellt haben und eine Standard Edition-Server Bereitstellung verwenden, muss der DNS-a-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="0a481-131">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="0a481-132">Die einfache Administrator-URL ist nur intern.</span><span class="sxs-lookup"><span data-stu-id="0a481-132">The Admin simple URL is internal only.</span></span> <span data-ttu-id="0a481-133">Hierfür ist ein DNS-a-Eintrag erforderlich, bei dem die URL zur IP-Adresse des Directors aufgelöst wird, wenn eine solche bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0a481-133">It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="0a481-134">Andernfalls sollte Sie in die IP-Adresse des Load Balancer eines Front-End-Pools aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="0a481-134">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="0a481-135">Wenn Sie keinen Pool bereitgestellt haben und eine Standard Edition-Server Bereitstellung verwenden, muss der DNS-a-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="0a481-135">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="0a481-136">Einfache URL-Option 2</span><span class="sxs-lookup"><span data-stu-id="0a481-136">Simple URL Option 2</span></span>

<span data-ttu-id="0a481-137">Bei Option 2 verfügen die einfachen URLs für Besprechungen, Einwahl und Administratoren über eine allgemeine Basis-URL, beispielsweise lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0a481-137">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com.</span></span> <span data-ttu-id="0a481-138">Daher benötigen Sie nur einen DNS-A-Eintrag für diese einfachen URLs, wodurch lync.contoso.com in die IP-Adresse eines Director-Pools oder eines Front-End-Pools aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0a481-138">Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span> <span data-ttu-id="0a481-139">Wenn Sie keinen Pool bereitgestellt haben und eine Standard Edition-Server Bereitstellung verwenden, muss der DNS-a-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="0a481-139">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="0a481-140">Beachten Sie Folgendes: Wenn in Ihrer Organisation mehr als eine SIP-Domäne vorhanden ist, müssen Sie für jede SIP-Domäne immer noch einfache URLs erstellen, und für jede einfache URL muss ein DNS-a-Eintrag erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0a481-140">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="0a481-141">In diesem Beispiel werden drei einfache URLs, die alle auf lync.contoso.com basieren, als zusätzliche einfache URL für fabrikam.com mit einer anderen Basis-URL eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="0a481-141">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="0a481-142">In diesem Beispiel müssen Sie DNS-A-Einträge für beide https://lync.contoso.com und erstellen https://lync.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="0a481-142">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="0a481-143">Die einfache URL-Option 3 zeigt eine andere Möglichkeit zur Behandlung von Namen-und DNS-Einträgen, wenn Sie über mehrere SIP-Domänen verfügen.</span><span class="sxs-lookup"><span data-stu-id="0a481-143">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="0a481-144">Einfache URL-Option 2</span><span class="sxs-lookup"><span data-stu-id="0a481-144">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a481-145"><strong>Einfache URL</strong></span><span class="sxs-lookup"><span data-stu-id="0a481-145"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="0a481-146"><strong>Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="0a481-146"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a481-147">Treffen</span><span class="sxs-lookup"><span data-stu-id="0a481-147">Meet</span></span></p></td>
<td><p><span data-ttu-id="0a481-148"> https://lync.contoso.com/Meetusw. https://lync.fabrikam.com/Meet (eine für jede SIP-Domäne in Ihrer Organisation)</span><span class="sxs-lookup"><span data-stu-id="0a481-148">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a481-149">Einwahl</span><span class="sxs-lookup"><span data-stu-id="0a481-149">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a481-150">Admin</span><span class="sxs-lookup"><span data-stu-id="0a481-150">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="0a481-151">Einfache URL-Option 3</span><span class="sxs-lookup"><span data-stu-id="0a481-151">Simple URL Option 3</span></span>

<span data-ttu-id="0a481-152">Option 3 ist besonders nützlich, wenn Sie über viele SIP-Domänen verfügen und diese über getrennte einfache URLs verfügen möchten, aber den DNS-Eintrag und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0a481-152">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> <span data-ttu-id="0a481-153">In diesem Beispiel benötigen Sie nur einen DNS-A-Eintrag, mit dem lync.contoso.com in die IP-Adresse eines Director-Pools oder eines Front-End-Pools aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0a481-153">In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="0a481-154">Einfache URL-Option 3</span><span class="sxs-lookup"><span data-stu-id="0a481-154">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a481-155"><strong>Einfache URL</strong></span><span class="sxs-lookup"><span data-stu-id="0a481-155"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="0a481-156"><strong>Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="0a481-156"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a481-157">Treffen</span><span class="sxs-lookup"><span data-stu-id="0a481-157">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a481-158">Einwahl</span><span class="sxs-lookup"><span data-stu-id="0a481-158">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a481-159">Admin</span><span class="sxs-lookup"><span data-stu-id="0a481-159">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="0a481-160">Disaster Recovery-Option für einfache URLs</span><span class="sxs-lookup"><span data-stu-id="0a481-160">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="0a481-161">Wenn Sie über mehrere Websites verfügen, die Front-End-Pools enthalten und Ihr DNS-Anbieter GeoDNS unterstützt, können Sie Ihre DNS-Einträge für einfache URLs einrichten, um die Disaster Recovery zu unterstützen, damit die einfache URL-Funktionalität auch dann fortgesetzt wird, wenn ein ganzer Front-End-Pool ausfällt.</span><span class="sxs-lookup"><span data-stu-id="0a481-161">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="0a481-162">Dieses Disaster Recovery-Feature unterstützt die einfachen URLs Meet und Dial-in.</span><span class="sxs-lookup"><span data-stu-id="0a481-162">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="0a481-163">Um dies zu konfigurieren, erstellen Sie zwei GeoDNS-Adressen.</span><span class="sxs-lookup"><span data-stu-id="0a481-163">To configure this, create two GeoDNS addresses.</span></span> <span data-ttu-id="0a481-164">Jede Adresse hat zwei DNS-A-oder CNAME-Einträge, die in zwei Pools aufgelöst werden, die für Disaster Recovery-Zwecke kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="0a481-164">Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes.</span></span> <span data-ttu-id="0a481-165">Eine GeoDNS-Adresse wird für den internen Zugriff verwendet und in die IP-Adresse des internen webfqdn oder des Lastenausgleichsmoduls für die beiden Pools aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="0a481-165">One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="0a481-166">Die andere GeoDNS-Adresse wird für den externen Zugriff verwendet und in die IP-Adresse des externen webfqdn oder des Load Balancer für die beiden Pools aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="0a481-166">The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="0a481-167">Im folgenden finden Sie ein Beispiel für die einfache URL "erfüllen" mit den FQDNs für die Pools.</span><span class="sxs-lookup"><span data-stu-id="0a481-167">The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="0a481-168">Erstellen Sie dann CNAME-Einträge, die ihre einfache URL (beispielsweise Meet.contoso.com) zu den beiden GeoDNS-Adressen auflösen.</span><span class="sxs-lookup"><span data-stu-id="0a481-168">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="0a481-169">Wenn in Ihrem Netzwerk <EM>hairpinning</EM> (Routing aller einfachen URL-Datenverkehr über den externen Link, einschließlich Datenverkehr, der aus Ihrer Organisation stammt) verwendet wird, können Sie einfach die externe GeoDNS-Adresse konfigurieren und ihre einfache URL für die Besprechung nur an diese externe Adresse auflösen.</span><span class="sxs-lookup"><span data-stu-id="0a481-169">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="0a481-170">Wenn Sie diese Methode verwenden, können Sie jede GeoDNS-Adresse so konfigurieren, dass entweder eine Round Robin-Methode zum Verteilen von Anforderungen an die beiden Pools verwendet wird, oder wenn Sie eine Verbindung in erster Linie mit einem Pool (wie dem geografisch näher gelegenen Pool) herstellen und den anderen Pool nur bei einem Verbindungsfehler verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a481-170">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="0a481-171">Sie können die gleiche Konfiguration für die Einwahl einfache URL einrichten.</span><span class="sxs-lookup"><span data-stu-id="0a481-171">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="0a481-172">Erstellen Sie dazu zusätzliche Datensätze wie im vorherigen Beispiel, die `dialin` `meet` in den DNS-Einträgen ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="0a481-172">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="0a481-173">Verwenden Sie für die einfache Administrator-URL eine der drei oben in diesem Abschnitt aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="0a481-173">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="0a481-174">Sobald diese Konfiguration eingerichtet ist, müssen Sie eine Überwachungsanwendung verwenden, um die HTTP-Überwachung so einzurichten, dass Fehler überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="0a481-174">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="0a481-175">Überwachen Sie für externen Zugriff, um sicherzustellen, dass HTTPS AutoDiscovery-Anforderungen an die externe Web-FQDN-oder Load Balancer-IP-Adresse für die beiden Pools erhalten erfolgreich sind.</span><span class="sxs-lookup"><span data-stu-id="0a481-175">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="0a481-176">Die folgenden Anforderungen dürfen beispielsweise keinen **Accept** -Header enthalten und müssen **200 OK** zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0a481-176">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="0a481-177">Für den internen Zugriff müssen Sie Port 5061 auf der internal Web FQDN-oder Load Balancer-IP-Adresse für die beiden Pools überwachen.</span><span class="sxs-lookup"><span data-stu-id="0a481-177">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="0a481-178">Wenn Verbindungsfehler erkannt werden, müssen die VIP für diese Pools die Ports 80, 443 und 444 schließen.</span><span class="sxs-lookup"><span data-stu-id="0a481-178">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

<span data-ttu-id="0a481-179"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="0a481-179"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

