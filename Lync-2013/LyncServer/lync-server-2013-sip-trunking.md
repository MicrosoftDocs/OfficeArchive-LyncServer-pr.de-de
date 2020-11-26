---
title: 'Lync Server 2013: SIP-Trunking'
description: 'Lync Server 2013: SIP-Trunking.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60b68d9d0400c87de2832d7fe7bdabe4057ec47a
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49423806"
---
# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="274d3-103">SIP-Trunking in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="274d3-103">SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="274d3-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="274d3-104">

<span> </span></span></span>

<span data-ttu-id="274d3-105">_**Letztes Änderungsdatum des Themas:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="274d3-105">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="274d3-p101">SIP (Session Initiation Protocol) wird zum Initiieren und Verwalten von VoIP-Kommunikationssitzungen (Voice over IP) für grundlegende Telefondienste und zusätzliche Echtzeitkommunikationsdienste wie Chats, Konferenzfunktionen, Anwesenheitserkennung und Multimediafunktionen verwendet. Dieser Abschnitt umfasst Planungsinformationen für die Implementierung von *SIP-Trunks*, einer Art von SIP-Verbindung, die über die Grenzen Ihres lokalen Netzwerks hinausgeht.</span><span class="sxs-lookup"><span data-stu-id="274d3-p101">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia. This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="274d3-108">Was ist SIP-Trunking?</span><span class="sxs-lookup"><span data-stu-id="274d3-108">What is SIP Trunking?</span></span>

<span data-ttu-id="274d3-p102">Bei einem SIP-Trunk handelt es sich um eine IP-Verbindung für die SIP-Kommunikation zwischen Ihrer Organisation und einem Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP), die über Ihre Firewall hinausgeht. Ein SIP-Trunk wird typischerweise verwendet, um den zentralen Standort Ihrer Organisation mit einem ITSP zu verbinden. In einigen Fällen können Sie das SIP-Trunking auch zum Verbinden einer Zweigstelle mit einem ITSP nutzen.</span><span class="sxs-lookup"><span data-stu-id="274d3-p102">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall. Typically, a SIP trunk is used to connect your organization’s central site to an ITSP. In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="274d3-112">SIP-Trunks und direkte SIP-Verbindungen im Vergleich</span><span class="sxs-lookup"><span data-stu-id="274d3-112">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="274d3-113">Der Begriff *Trunk* wurde aus der leitungsvermittelten Technologie abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="274d3-113">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="274d3-114">Er bezieht sich auf eine dedizierte physische Leitung zur Verbindung von Telefonvermittlungsanlagen.</span><span class="sxs-lookup"><span data-stu-id="274d3-114">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="274d3-115">Wie ihre Vorgänger-, Time Division Multiplexing-(TDM-) Trunks sind SIP-Stämme Verbindungen zwischen zwei getrennten SIP-Netzwerken – dem lync Server 2013 Enterprise und dem ITSP.</span><span class="sxs-lookup"><span data-stu-id="274d3-115">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="274d3-116">Im Gegensatz zu leitungsvermittelten Trunks handelt es sich bei SIP-Trunks um virtuelle Verbindungen, die über jeden der unterstützten Typen von SIP-Trunkingverbindungen hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="274d3-116">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="274d3-117">Details zu den unterstützten Verbindungstypen finden Sie unter [wie kann ich SIP-Trunking in lync Server 2013 implementieren?](lync-server-2013-how-do-i-implement-sip-trunking.md)</span><span class="sxs-lookup"><span data-stu-id="274d3-117">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="274d3-118">Bei direkten SIP-Verbindungen hingegen handelt es sich um SIP-Verbindungen, die nicht über die Grenzen des lokalen Netzwerks hinausgehen (das heißt, es wird eine Verbindung mit einem PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz) oder einer Nebenstellenanlage (Private Branch Exchange, PBX) innerhalb des internen Netzwerks hergestellt).</span><span class="sxs-lookup"><span data-stu-id="274d3-118">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="274d3-119">Ausführliche Informationen dazu, wie Sie direkte SIP-Verbindungen mit lync Server 2013 verwenden können, finden Sie unter [direkte SIP-Verbindungen in lync Server 2013](lync-server-2013-direct-sip-connections.md).</span><span class="sxs-lookup"><span data-stu-id="274d3-119">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="274d3-120">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="274d3-120">In This Section</span></span>

  - [<span data-ttu-id="274d3-121">Übersicht über SIP-Trunking in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="274d3-121">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="274d3-122">Implementierung von SIP-Trunking in Lync Server 2013?</span><span class="sxs-lookup"><span data-stu-id="274d3-122">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="274d3-123">Komponenten und Topologien für das SIP-Trunking in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="274d3-123">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="274d3-124">Branch site SIP trunking in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="274d3-124">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="274d3-125">Prüfliste für die Bereitstellung von SIP-Trunks für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="274d3-125">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

<span data-ttu-id="274d3-126"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="274d3-126"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

