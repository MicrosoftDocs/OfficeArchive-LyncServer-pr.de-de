---
title: 'Lync Server 2013: Überprüfen der System Einstellungen für Domänennamen für den Lastenausgleich'
description: 'Lync Server 2013: Überprüfen Sie die System Einstellungen des Domänennamens für den Lastenausgleich.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a218a79a541e9c9705a8403146fe7e134e8ed827
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49446325"
---
# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="cbe6b-103">Überprüfen von System Einstellungen für den Domänennamen für den Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbe6b-103">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="cbe6b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="cbe6b-104">

<span> </span></span></span>

<span data-ttu-id="cbe6b-105">_**Letztes Änderungsdatum des Themas:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="cbe6b-105">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="cbe6b-106">Zur Unterstützung des vom DNS-Lastenausgleich verwendeten FQDN müssen Sie DNS bereitstellen, um den Pool-FQDN (wie pool01.contoso.com) in die IP-Adressen aller Server im Pool aufzulösen (beispielsweise 192.168.1.1, 192.168.1.2 usw.).</span><span class="sxs-lookup"><span data-stu-id="cbe6b-106">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="cbe6b-107">Sie sollten nur die IP-Adressen der Server einbeziehen, die derzeit bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cbe6b-107">You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="cbe6b-108">Wenn Sie den DNS-Lastenausgleich für die Edge-Pools verwenden, sind zusätzlich die folgenden DNS-Einträge erforderlich:</span><span class="sxs-lookup"><span data-stu-id="cbe6b-108">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="cbe6b-109">Für den lync Server Access Edge-Dienst müssen Sie einen Eintrag für jeden Server im Pool besitzen.</span><span class="sxs-lookup"><span data-stu-id="cbe6b-109">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="cbe6b-110">Jeder Eintrag muss den FQDN des lync Server Access-Edgedienst (beispielsweise SIP.contoso.com) in die IP-Adresse des lync Server Access Edge-Diensts auf einem der Edgeserver im Pool auflösen.</span><span class="sxs-lookup"><span data-stu-id="cbe6b-110">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="cbe6b-111">Für den lync Server Web Conferencing Edge-Dienst müssen Sie einen Eintrag für jeden Server im Pool besitzen.</span><span class="sxs-lookup"><span data-stu-id="cbe6b-111">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="cbe6b-112">Jeder Eintrag muss den FQDN des lync Server Web Conferencing Edge-Diensts (beispielsweise webconf.contoso.com) in die IP-Adresse des lync Server Web Conferencing Edge-Diensts auf einem der Edgeserver im Pool auflösen.</span><span class="sxs-lookup"><span data-stu-id="cbe6b-112">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="cbe6b-113">Für den lync Server-Audio/Video-Edgedienst muss für jeden Server im Pool ein Eintrag vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="cbe6b-113">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="cbe6b-114">Jeder Eintrag muss den FQDN des lync Server-Audio/Video-Edgedienst (beispielsweise AV.contoso.com) in die IP-Adresse des lync Server-Audio/Video-Edgedienst auf einem der Edgeserver im Pool auflösen.</span><span class="sxs-lookup"><span data-stu-id="cbe6b-114">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="cbe6b-115">Wenn Sie den DNS-Lastenausgleich auf der internen Schnittstelle des Edge-Pools verwenden möchten, müssen Sie einen DNS-Eintrag hinzufügen, der den internen FQDN des Edge-Pools in die IP-Adresse jedes Servers im Pool auflöst.</span><span class="sxs-lookup"><span data-stu-id="cbe6b-115">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="cbe6b-116">Verwenden Sie das Nslookup-Tool, um zu überprüfen, ob DNS die richtigen Werte für den DNS-Lastenausgleich zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="cbe6b-116">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="cbe6b-117">Wenn Sie alle Werte für einen DNS-Eintrag mit nslookup zurückgeben möchten, sollten Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="cbe6b-117">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="cbe6b-118">Sie führen diesen Befehl für jeden FQDN aus, der in der Konfiguration des DNS-Lastenausgleichs verwendet wird, um zu überprüfen, ob alle Daten Satz Sätze für den DNS-Lastenausgleich alle korrekten Einträge zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="cbe6b-118">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

<span data-ttu-id="cbe6b-119"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="cbe6b-119"></div>

<span> </span>

</div>

</div>

</span></span></div>

