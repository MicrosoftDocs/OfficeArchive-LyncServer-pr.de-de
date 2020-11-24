---
title: 'Lync Server 2013: Bereitstellungsoptionen für PSTN-Gateways'
description: 'Lync Server 2013: Bereitstellungsoptionen für PSTN-Gateways.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871bc4d573e927f83cdb07d4fb2b5d5b954e6383
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394594"
---
# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="3ff05-103">Bereitstellungsoptionen für PSTN-Gateways in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ff05-103">PSTN gateway deployment options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="3ff05-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="3ff05-104">

<span> </span></span></span>

<span data-ttu-id="3ff05-105">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="3ff05-105">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="3ff05-106">PSTN Gateways</span><span class="sxs-lookup"><span data-stu-id="3ff05-106">PSTN Gateways</span></span>

<span data-ttu-id="3ff05-107">PSTN-Gateways (Public Switched Telephone Network) sind Hardwarekomponenten von Drittanbietern, die Signale und Medien zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN übersetzen, entweder direkt oder über die Verbindung zu SIP-Stämmen.</span><span class="sxs-lookup"><span data-stu-id="3ff05-107">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="3ff05-108">In beiden Topologien beendet das Gateway das PSTN.</span><span class="sxs-lookup"><span data-stu-id="3ff05-108">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="3ff05-109">Das Gateway ist in seinem eigenen Subnetz isoliert und wird über den Vermittlungs Server mit dem Unternehmensnetzwerk verbunden.</span><span class="sxs-lookup"><span data-stu-id="3ff05-109">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="3ff05-110">In einem Unternehmen mit mehreren Websites werden in der Regel mindestens ein Gateway an jedem Standort bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3ff05-110">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="3ff05-111">Zweigstellenstandorte können eine Verbindung mit dem PSTN entweder über ein Gateway oder über eine Survivable Branch-Appliance herstellen, die Gateway und Server in einem einzigen Feld kombiniert.</span><span class="sxs-lookup"><span data-stu-id="3ff05-111">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="3ff05-112">Wenn Verzweigungs Websites ein Gateway verwenden, sind auf der Website sowohl eine Registrierungsstelle als auch ein Vermittlungs Server erforderlich, es sei denn, die WAN-Verbindung ist widerstandsfähig.</span><span class="sxs-lookup"><span data-stu-id="3ff05-112">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="3ff05-113">Auf einem oder mehreren Vermittlungsservern, die sich auf Front-End-Servern befinden, können Anrufe an die einen oder mehrere Gateways an jedem Standort weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3ff05-113">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="3ff05-114">Wir empfehlen, dass die auf der Website erforderliche Registrierungsstelle, der Vermittlungs Server und das Gateway als Survivable Branch Appliance bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3ff05-114">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="3ff05-115">Die Ermittlung von Anzahl, Größe und Standort von PSTN-Gateways ist vielleicht die wichtigste und kostspieligste Entscheidung, die Sie bei der Planung Ihrer Enterprise-VoIP-Infrastruktur treffen müssen.</span><span class="sxs-lookup"><span data-stu-id="3ff05-115">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="3ff05-116">Here are the main questions to consider.</span><span class="sxs-lookup"><span data-stu-id="3ff05-116">Here are the main questions to consider.</span></span> <span data-ttu-id="3ff05-117">Beachten Sie, dass die Antworten auf diese Fragen alle voneinander abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="3ff05-117">Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="3ff05-118">How many PSTN gateways are needed?</span><span class="sxs-lookup"><span data-stu-id="3ff05-118">How many PSTN gateways are needed?</span></span> <span data-ttu-id="3ff05-119">Die Antwort richtet sich nach der Anzahl der Benutzer, der voraussichtlichen Anzahl von gleichzeitigen anrufen (Traffic Load) und der Anzahl der Websites (jeder Standort benötigt einen).</span><span class="sxs-lookup"><span data-stu-id="3ff05-119">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="3ff05-120">What size should the gateways be?</span><span class="sxs-lookup"><span data-stu-id="3ff05-120">What size should the gateways be?</span></span> <span data-ttu-id="3ff05-121">Die Antwort hängt von der Anzahl der Benutzer auf der Website und von der Auslastung des Datenverkehrs ab.</span><span class="sxs-lookup"><span data-stu-id="3ff05-121">The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="3ff05-122">Where should the gateways be located?</span><span class="sxs-lookup"><span data-stu-id="3ff05-122">Where should the gateways be located?</span></span> <span data-ttu-id="3ff05-123">Die Antwort hängt teilweise von der Topologie und teilweise von der geografischen Verteilung Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="3ff05-123">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="3ff05-124"> You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span><span class="sxs-lookup"><span data-stu-id="3ff05-124">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="3ff05-125">M:N Trunk Support</span><span class="sxs-lookup"><span data-stu-id="3ff05-125">M:N Trunk Support</span></span>

<span data-ttu-id="3ff05-126">Die Vermittlungsserver können Anrufe über mehrere Gateways (Session Border Controllers, SBCS), die von Internet-Telefoniedienst-Anbietern bereitgestellt werden, oder eine Kombination der beiden leiten.</span><span class="sxs-lookup"><span data-stu-id="3ff05-126">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="3ff05-127">Darüber hinaus können mehrere Vermittlungsserver im Pool mit mehreren Gateways interagieren.</span><span class="sxs-lookup"><span data-stu-id="3ff05-127">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="3ff05-128">Die logische Route, die zwischen einem Vermittlungs Server und einem Gateway definiert wird, wird als *trunk* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3ff05-128">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="3ff05-129">Wenn ein interner Benutzer einen PSTN-Anruf annimmt, wählt die ausgehende Routinglogik im Front-End-Pool aus, welcher trunk über alle möglichen Kombinationen weitergeleitet werden soll, die möglicherweise für das Routing dieses bestimmten Anrufs verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3ff05-129">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="3ff05-130">Wenn ein Anruf aufgrund eines Problems mit einem bestimmten Vermittlungsserver im Pool durch einen DNS-Lastenausgleich nicht erreicht wird, wird der Anruf an einen alternativen Vermittlungsserver im Pool wiederholt.</span><span class="sxs-lookup"><span data-stu-id="3ff05-130">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="3ff05-131">Ausführliche Informationen zur Planung mehrerer Gateways finden Sie unter [M:N trunk in lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="3ff05-131">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="3ff05-132">Details zu weiteren Verbesserungen des ausgehenden Routings finden Sie unter [VoIP-Routen in lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="3ff05-132">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="3ff05-133">Gateway Topologies</span><span class="sxs-lookup"><span data-stu-id="3ff05-133">Gateway Topologies</span></span>

<span data-ttu-id="3ff05-134">Führen Sie die folgenden Schritte aus, wenn Sie die grundlegenden Fragen der Gateway-Bereitstellung beachten:</span><span class="sxs-lookup"><span data-stu-id="3ff05-134">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="3ff05-135">Zählen Sie die Websites, auf denen Sie PSTN-Konnektivität mithilfe von Enterprise-VoIP bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="3ff05-135">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="3ff05-136">Schätzen Sie den Datenverkehr an jeder Website (Anzahl der Benutzer und durchschnittliche Anzahl von Anrufen pro Stunde pro Benutzer).</span><span class="sxs-lookup"><span data-stu-id="3ff05-136">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="3ff05-137">Bereitstellen eines oder mehrerer Gateways an jedem Standort, um den erwarteten Datenverkehr zu verarbeiten</span><span class="sxs-lookup"><span data-stu-id="3ff05-137">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="3ff05-138">Die resultierende verteilte Gateway-Topologie wird in der folgenden Abbildung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3ff05-138">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="3ff05-139">**Topologie des verteilten Gateways**</span><span class="sxs-lookup"><span data-stu-id="3ff05-139">**Distributed gateway topology**</span></span>

<span data-ttu-id="3ff05-140">![Topologie-Diagramm für verteilte Gateways](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Topologie-Diagramm für verteilte Gateways")</span><span class="sxs-lookup"><span data-stu-id="3ff05-140">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="3ff05-141">Bei dieser Topologie werden Anrufe zwischen Mitarbeitern an jedem Standort und zwischen Websites über Ihr Intranet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="3ff05-141">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="3ff05-142">Anrufe an das PSTN werden über das Enterprise IP-Netzwerk an die Gateways weitergeleitet, die dem Standort der Zielrufnummern am nächsten sind. Was aber, wenn Ihre Organisation Dutzende oder Hunderte oder sogar Tausende von Websites unterstützt, die sich über einen oder mehrere Kontinente verteilen, wie es viele Finanzinstitute und andere große Unternehmen tun?</span><span class="sxs-lookup"><span data-stu-id="3ff05-142">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="3ff05-143">In solchen Fällen ist die Bereitstellungeines separaten Gateways an jedem Standort nicht praktikabel.</span><span class="sxs-lookup"><span data-stu-id="3ff05-143">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="3ff05-144">Um dieses Problem zu beheben, bevorzugen viele große Unternehmen, wie in der nachstehenden Abbildung zu sehen, ein oder einige wenige große Telefonie-Zentrale Standorte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3ff05-144">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="3ff05-145">**Topologie des zentralen Telefonie-Standorts**</span><span class="sxs-lookup"><span data-stu-id="3ff05-145">**Telephony central site topology**</span></span>

<span data-ttu-id="3ff05-146">![Datencenter-Gateway-Topologie](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Datencenter-Gateway-Topologie")</span><span class="sxs-lookup"><span data-stu-id="3ff05-146">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="3ff05-147">In dieser Topologie sind mehrere große Gateways, die für die erwartete Benutzerauslastung ausreichend sind, an jedem zentralen Standort bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3ff05-147">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="3ff05-148">Alle Anrufe an Benutzer im Unternehmen werden vom Telefondienstanbieter des Unternehmens an einen zentralen Standort weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="3ff05-148">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="3ff05-149">Die Routing Logik am zentralen Standort bestimmt, ob der Anruf über das Intranet oder das PSTN weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ff05-149">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="3ff05-150">Gateway Location</span><span class="sxs-lookup"><span data-stu-id="3ff05-150">Gateway Location</span></span>

<span data-ttu-id="3ff05-151">Der Gateway-Speicherort kann auch die von Ihnen ausgewählten Typen von Gateways und Ihre Konfiguration ermitteln.</span><span class="sxs-lookup"><span data-stu-id="3ff05-151">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="3ff05-152">Es gibt Dutzende von PSTN-Protokollen, von denen keiner weltweit Standard ist.</span><span class="sxs-lookup"><span data-stu-id="3ff05-152">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="3ff05-153">Wenn sich alle Ihre Gateways in einem einzelnen Land/einer Region befinden, handelt es sich nicht um ein Problem, aber wenn Sie Gateways in verschiedenen Ländern/Regionen finden, müssen die einzelnen Gateways entsprechend den PSTN-Standards für dieses Land/diese Region konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3ff05-153">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="3ff05-154">Darüber hinaus sind Gateways, die für den Einsatz in Kanada zertifiziert sind, möglicherweise nicht in Indien, Brasilien oder der Europäischen Union zertifiziert.</span><span class="sxs-lookup"><span data-stu-id="3ff05-154">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="3ff05-155">Gateway Size and Number</span><span class="sxs-lookup"><span data-stu-id="3ff05-155">Gateway Size and Number</span></span>

<span data-ttu-id="3ff05-156">Die PSTN-Gateways, die in den meisten Organisationen für die Bereitstellung von Bereichsgröße von 2 bis so viele 960-Ports in Frage kommen.</span><span class="sxs-lookup"><span data-stu-id="3ff05-156">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="3ff05-157">(Es gibt sogar größere Gateways, die aber hauptsächlich von Telefondienstanbietern verwendet werden.) Verwenden Sie die folgenden Richtlinien, wenn Sie die Anzahl der von Ihrer Organisation benötigten Ports schätzen:</span><span class="sxs-lookup"><span data-stu-id="3ff05-157">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="3ff05-158">Organisationen mit leichter Telefonie-Nutzung (ein PSTN-Anruf pro Benutzer pro Stunde) sollten für alle 15 Benutzer einen Port zuteilen.</span><span class="sxs-lookup"><span data-stu-id="3ff05-158">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="3ff05-159">Wenn Sie beispielsweise 20 Benutzer haben, benötigen Sie ein Gateway mit zwei Anschlüssen.</span><span class="sxs-lookup"><span data-stu-id="3ff05-159">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="3ff05-160">Organisationen mit mittlerer Telefonie-Nutzung (zwei PSTN-Anrufe pro Benutzer pro Stunde) sollten einem Port für alle 10 Nutzer zugeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="3ff05-160">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="3ff05-161">Wenn Sie beispielsweise über 100-Benutzer verfügen, benötigen Sie insgesamt 10 Ports, die einem oder mehreren Gateways zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="3ff05-161">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="3ff05-162">Organisationen mit hoher Telefonnutzung (drei oder mehr PSTN-Anrufe pro Benutzer pro Stunde) sollten für alle fünf Benutzer einen Port zuteilen.</span><span class="sxs-lookup"><span data-stu-id="3ff05-162">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="3ff05-163">Wenn Sie beispielsweise über 47.000-Benutzer verfügen, benötigen Sie insgesamt 9.400-Ports, die unter mindestens 10 große Gateways zugeteilt sind.</span><span class="sxs-lookup"><span data-stu-id="3ff05-163">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="3ff05-164">Zusätzliche Ports können abgerufen werden, wenn die Anzahl der Benutzer oder der Datenverkehr in Ihrer Organisation zunimmt.</span><span class="sxs-lookup"><span data-stu-id="3ff05-164">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="3ff05-165">Für eine bestimmte Anzahl von Benutzern, die Sie unterstützen müssen, haben Sie die Wahl, weniger, größere Gateways oder kleinere bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3ff05-165">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="3ff05-166">In der Regel werden mindestens zwei Gateways für eine Organisation empfohlen, um die Verfügbarkeit zu gewährleisten, wenn ein Gateway ausfällt.</span><span class="sxs-lookup"><span data-stu-id="3ff05-166">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="3ff05-167">Jedes von Ihnen bereitgestellte PSTN-Gateway muss mindestens über einen entsprechenden Vermittlungs Server verfügen.</span><span class="sxs-lookup"><span data-stu-id="3ff05-167">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

<span data-ttu-id="3ff05-168"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="3ff05-168"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

