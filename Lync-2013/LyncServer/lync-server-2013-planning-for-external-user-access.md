---
title: 'Lync Server 2013: Planen des Zugriffs externer Benutzer'
description: 'Lync Server 2013: Planen des Zugriffs durch externe Benutzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8f1854791ed837b963d4c80f3467e4e89555592
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49393787"
---
# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="e50c4-103">Planen des Zugriffs externer Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e50c4-103">Planning for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e50c4-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e50c4-104">

<span> </span></span></span>

<span data-ttu-id="e50c4-105">_**Letztes Änderungsdatum des Themas:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="e50c4-105">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="e50c4-106">Die Kommunikation in den meisten Organisationen umfasst Dienste und Benutzer, die sich nicht in Ihrem internen Netzwerk befinden.</span><span class="sxs-lookup"><span data-stu-id="e50c4-106">Communications in most organizations involve services and users that are not inside your internal network.</span></span> <span data-ttu-id="e50c4-107">Zu diesen Diensten und Benutzern gehören Mitarbeiter, die vorübergehend oder dauerhaft extern sind, Mitarbeiter von Kunden-oder Partnerorganisationen, Personen, die öffentliche Instant Messaging-Dienste (im) verwenden, und potenzielle Kunden, Partner und anonyme Benutzer, die Sie zu Besprechungen und Präsentationen einladen.</span><span class="sxs-lookup"><span data-stu-id="e50c4-107">These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations.</span></span> <span data-ttu-id="e50c4-108">In dieser Dokumentation werden diese Personen gemeinsam als *externe Benutzer* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e50c4-108">In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="e50c4-109">Mit Microsoft lync Server 2013 können Benutzer in Ihrer Organisation Chats und Anwesenheitsinformationen für die Kommunikation mit externen Benutzern verwenden, und Sie können an Audio/Video-Konferenzen und Webkonferenzen mit Ihren externen Mitarbeitern und anderen Typen externer Benutzer teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="e50c4-109">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="e50c4-110">Sie können auch externen Zugriff von mobilen Geräten und über Enterprise-VoIP unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e50c4-110">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="e50c4-111">Externe Benutzer, die keine Mitglieder Ihrer Organisation sind, können an lync Server 2013-Besprechungen teilnehmen und anonyme Teilnehmer zulassen.</span><span class="sxs-lookup"><span data-stu-id="e50c4-111">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="e50c4-112">Um die Kommunikation in der Firewall Ihrer Organisation zu unterstützen, stellen Sie den lync Server 2013-Edgeserver in Ihrem Umkreisnetzwerk bereit (auch bekannt als DMZ, demilitarisierte Zone und abgeschirmtes Subnetz).</span><span class="sxs-lookup"><span data-stu-id="e50c4-112">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="e50c4-113">Der Edgeserver steuert, wie Benutzer außerhalb der Firewall eine Verbindung mit ihrer internen lync Server 2013-Bereitstellung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="e50c4-113">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="e50c4-114">Außerdem steuert Sie die Kommunikation mit externen Benutzern, die innerhalb der Firewall entstehen.</span><span class="sxs-lookup"><span data-stu-id="e50c4-114">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="e50c4-115">Je nach Ihren Anforderungen können Sie einen oder mehrere Edgeserver an einem oder mehreren Speicherorten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e50c4-115">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="e50c4-116">In diesem Abschnitt werden Szenarien für den Zugriff durch externe Benutzer in lync Server 2013 beschrieben, und es wird erläutert, wie Sie Ihre Edge-und Reverse-Proxy Topologie planen.</span><span class="sxs-lookup"><span data-stu-id="e50c4-116">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e50c4-117">Obwohl Sie einen Edgeserver zur Unterstützung von Enterprise-VoIP und externem Benutzer Zugriff benötigen, konzentriert sich dieser Abschnitt auf die Unterstützung für Chat, Anwesenheit, A/V-Konferenzen, Föderation, Webkonferenzen und lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="e50c4-117">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="e50c4-118">Details zur Unterstützung von Enterprise-VoIP finden Sie unter <A href="lync-server-2013-planning-for-enterprise-voice.md">Planen von Enterprise-VoIP in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e50c4-118">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e50c4-119">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e50c4-119">In This Section</span></span>

  - [<span data-ttu-id="e50c4-120">Änderungen in Lync Server 2013, die die Planung für Edgeserver betreffen</span><span class="sxs-lookup"><span data-stu-id="e50c4-120">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="e50c4-121">Systemanforderungen für Komponenten für den Zugriff durch externe Benutzer für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e50c4-121">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="e50c4-122">Übersicht über den Zugriff durch externe Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e50c4-122">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="e50c4-123">Grundlegendes zu AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e50c4-123">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="e50c4-124">Auswählen einer Topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e50c4-124">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="e50c4-125">Datenerfassung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e50c4-125">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="e50c4-126">Ermitteln von DNS-Anforderungen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e50c4-126">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="e50c4-127">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e50c4-127">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="e50c4-128">Planen von Edgeserver-Zertifikaten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e50c4-128">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="e50c4-129">Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e50c4-129">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

<span data-ttu-id="e50c4-130"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e50c4-130"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

