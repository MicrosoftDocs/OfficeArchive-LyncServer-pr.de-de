---
title: 'Lync Server 2013: Port Zusammenfassung – AutoErmittlung'
description: 'Lync Server 2013: Port Zusammenfassung – AutoErmittlung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49442817"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="abf3e-103">Port Zusammenfassung – AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abf3e-103">Port summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="abf3e-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="abf3e-104">

<span> </span></span></span>

<span data-ttu-id="abf3e-105">_**Letztes Änderungsdatum des Themas:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="abf3e-105">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="abf3e-106">Der lync Server 2013-AutoErmittlungsdienst wird auf dem Director-und Front-End-Pool Server ausgeführt und kann, wenn er in DNS mithilfe der `lyncdiscover.<domain>` und `lyncdiscoverinternal.<domain>` Hosteinträge veröffentlicht wird, von Clients zum Auffinden von lync Server-Features verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="abf3e-106">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="abf3e-107">Damit Mobile Geräte mit lync Mobile die AutoErmittlung verwenden können, müssen Sie möglicherweise zuerst die Listen alternativer Zertifikats Subjekte auf jedem Director und Front-End-Server ändern, auf dem der AutoErmittlungsdienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="abf3e-107">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="abf3e-108">Darüber hinaus ist es möglicherweise erforderlich, die Listen Betreff alternativer Name auf Zertifikaten zu ändern, die für externe Webdienst Veröffentlichungsregeln für umgekehrte Proxys verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="abf3e-108">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="abf3e-109">Die Entscheidung darüber, ob die Listen Betreff alternativer Namen in umgekehrten Proxys verwendet werden, basiert darauf, ob Sie den AutoErmittlungsdienst auf Port 80 oder auf Port 443 veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="abf3e-109">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="abf3e-110">**Veröffentlicht auf Port 80**   Bei mobilen Geräten sind keine Zertifikat Änderungen erforderlich, wenn die ursprüngliche Abfrage des AutoErmittlungsdiensts über Port 80 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="abf3e-110">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="abf3e-111">Dies liegt daran, dass Mobile Geräte, auf denen lync ausgeführt wird, auf den Reverse-Proxy auf Port 80 extern zugreifen und dann intern auf Port 8080 an einen Director oder Front-End-Server umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="abf3e-111">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="abf3e-112">**Veröffentlicht auf Port 443**   Die Liste Subject Alternative Name für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, muss einen `lyncdiscover.<sipdomain>` Eintrag für jede SIP-Domäne innerhalb Ihrer Organisation enthalten.</span><span class="sxs-lookup"><span data-stu-id="abf3e-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="abf3e-113">Für neue Installationen oder Upgrades von lync Server 2010, bei denen Sie Mobility bereitgestellt haben, haben Sie entweder Port 80 für die AutoErmittlung des mobilitätsdiensts verwendet oder Zertifikate mit dem richtigen Antragstellernamen und den alternativen Subjektnamen neu ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="abf3e-113">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="abf3e-114">Überprüfen Sie die Zertifikate auf Ihrem Director und dem Front-End-Server, um den ausgewählten Pfad zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="abf3e-114">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="abf3e-115">Firewall-Details für Reverse Proxy Server: externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="abf3e-115">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abf3e-116">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="abf3e-116">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="abf3e-117">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="abf3e-117">Source IP Address</span></span></th>
<th><span data-ttu-id="abf3e-118">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="abf3e-118">Destination IP Address</span></span></th>
<th><span data-ttu-id="abf3e-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="abf3e-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abf3e-120">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="abf3e-120">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="abf3e-121">Beliebig</span><span class="sxs-lookup"><span data-stu-id="abf3e-121">Any</span></span></p></td>
<td><p><span data-ttu-id="abf3e-122">Reverse Proxy-Listener</span><span class="sxs-lookup"><span data-stu-id="abf3e-122">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="abf3e-123">Optional Umleitung zu HTTPS, wenn der Benutzer http://publishedSiteFQDN eingibt &lt; &gt; .</span><span class="sxs-lookup"><span data-stu-id="abf3e-123">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="abf3e-124">Dies ist auch bei Verwendung von Office Web Apps für Conferencing und dem AutoErmittlungsdienst für mobile Geräte, die lync ausführen, in Situationen erforderlich, in denen die Organisation das Zertifikat des externen Webdienst-Veröffentlichungsregel nicht ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="abf3e-124">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf3e-125">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="abf3e-125">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="abf3e-126">Beliebig</span><span class="sxs-lookup"><span data-stu-id="abf3e-126">Any</span></span></p></td>
<td><p><span data-ttu-id="abf3e-127">Reverse Proxy-Listener</span><span class="sxs-lookup"><span data-stu-id="abf3e-127">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="abf3e-128">Adressbuch Downloads, Adressbuch-Webabfrage Dienst, AutoErmittlung, Clientupdates, Besprechungsinhalte, Geräte Updates, Gruppenerweiterung, Office Web Apps für Konferenzen, Einwahlkonferenzen und Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="abf3e-128">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="abf3e-129">Firewall-Details für Reverse Proxy Server: interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="abf3e-129">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abf3e-130">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="abf3e-130">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="abf3e-131">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="abf3e-131">Source IP Address</span></span></th>
<th><span data-ttu-id="abf3e-132">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="abf3e-132">Destination IP Address</span></span></th>
<th><span data-ttu-id="abf3e-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="abf3e-133">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abf3e-134">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="abf3e-134">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="abf3e-135">Interne Reverse-Proxy-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="abf3e-135">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="abf3e-136">Front-End-Server, Front-End-Pool, Director, Director-Pool, Office Web Apps für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="abf3e-136">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="abf3e-137">Erforderlich, wenn der AutoErmittlungsdienst für mobile Geräte mit lync in Situationen verwendet wird, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="abf3e-137">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="abf3e-138">Datenverkehr, der an Port 80 auf der externen Schnittstelle des Reverse Proxys gesendet wird, wird von der internen Schnittstelle des Reverse-Proxys an einen Pool auf Port 8080 umgeleitet, sodass die Pool-Webdienste Sie vom internen Webverkehr unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="abf3e-138">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abf3e-139">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="abf3e-139">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="abf3e-140">Interne Reverse-Proxy-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="abf3e-140">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="abf3e-141">Front-End-Server, Front-End-Pool, Director, Director-Pool, Office Web Apps für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="abf3e-141">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="abf3e-142">Datenverkehr, der an Port 443 auf der externen Schnittstelle des Reverse Proxys gesendet wird, wird von der internen Schnittstelle des Reverse-Proxys an einen Pool auf Port 4443 umgeleitet, sodass die Pool-Webdienste Sie vom internen Webverkehr unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="abf3e-142">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table><span data-ttu-id="abf3e-143">


</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="abf3e-143">


</div>

<span> </span>

</div>

</div>

</span></span></div>

