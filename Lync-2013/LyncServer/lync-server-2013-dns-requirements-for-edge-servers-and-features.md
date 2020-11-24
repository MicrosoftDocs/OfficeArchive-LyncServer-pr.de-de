---
title: 'Lync Server 2013: DNS-Anforderungen für Edgeserver und Features'
description: 'Lync Server 2013: DNS-Anforderungen für Edgeserver und Features.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Edge Servers and features
ms:assetid: e3bf05c8-96fb-4dd2-acb1-f0d141c9e2ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721912(v=OCS.15)
ms:contentKeyID: 49733846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bcfd00080e765924eecc3138bc3d552ce331b63
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49395023"
---
# <a name="dns-requirements-for-edge-servers-and-features-in-lync-server-2013"></a><span data-ttu-id="a4b67-103">DNS-Anforderungen für Edgeserver und Features in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4b67-103">DNS requirements for Edge Servers and features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="a4b67-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="a4b67-104">

<span> </span></span></span>

<span data-ttu-id="a4b67-105">_**Letztes Änderungsdatum des Themas:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="a4b67-105">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="a4b67-106">Lync Server 2013-Edgeserver, Edge-Pools und Reverse-Proxies haben spezifische Anforderungen für DNS-Einträge (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="a4b67-106">Lync Server 2013 Edge Servers, Edge pools, and reverse proxies have specific requirements for Domain Name System (DNS) records.</span></span> <span data-ttu-id="a4b67-107">In lync Server 2013, wenn IPv4 und IPv6 verwendet werden, müssen Sie sowohl Host A-als auch AAAA-Einträge planen.</span><span class="sxs-lookup"><span data-stu-id="a4b67-107">In Lync Server 2013 when IPv4 and IPv6 are in use, you must plan for both host A and AAAA records.</span></span>

<span data-ttu-id="a4b67-108">Die folgenden Themen definieren die Verwendung von DNS-Einträgen für Ihre Bereitstellungsplanung:</span><span class="sxs-lookup"><span data-stu-id="a4b67-108">The topics listed below define the use of DNS records for your deployment planning:</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a4b67-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a4b67-109">In This Section</span></span>

  - [<span data-ttu-id="a4b67-110">DNS-Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4b67-110">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="a4b67-111">DNS-Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4b67-111">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="a4b67-112">DNS-Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4b67-112">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="a4b67-113">DNS-Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4b67-113">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="a4b67-114">DNS-Zusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4b67-114">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="a4b67-115">DNS-Zusammenfassung für Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4b67-115">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

  - [<span data-ttu-id="a4b67-116">DNS-Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4b67-116">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

<span data-ttu-id="a4b67-117"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="a4b67-117"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

