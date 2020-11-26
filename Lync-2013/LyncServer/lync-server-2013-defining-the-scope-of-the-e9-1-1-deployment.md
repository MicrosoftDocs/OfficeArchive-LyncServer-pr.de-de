---
title: 'Lync Server 2013: Definieren des Bereichs der E9-1-1-Bereitstellung'
description: 'Lync Server 2013: Definieren des Bereichs der E9-1-1-Bereitstellung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14e442718b7230dbc94aebdf6099aae9b430d5e9
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49430966"
---
# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="afefe-103">Definieren des Bereichs der E9-1-1-Bereitstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afefe-103">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="afefe-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="afefe-104">

<span> </span></span></span>

<span data-ttu-id="afefe-105">_**Letztes Änderungsdatum des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="afefe-105">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="afefe-106">Bevor Sie Microsoft lync Server 2013 für E9-1-1 konfigurieren, müssen Sie Ihre E9-1-1-Bereitstellung planen.</span><span class="sxs-lookup"><span data-stu-id="afefe-106">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="afefe-107">Stellen Sie sich die folgenden Fragen:</span><span class="sxs-lookup"><span data-stu-id="afefe-107">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="afefe-108">**Worin bestehen die Richtlinien und Vorschriften in Ihrer Organisation im Hinblick auf E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="afefe-108">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="afefe-109">Die gesetzlichen E9-1-1-Anforderungen für Nebenstellenanlagen (im E9-1-1-Jargon als „Telefonsysteme mit mehreren Leitungen“ oder „Mehrleitungstelefonsysteme“ bezeichnet) unterscheiden sich von Staat zu Staat.</span><span class="sxs-lookup"><span data-stu-id="afefe-109">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="afefe-110">Wenden Sie sich an Ihr Rechtsteam, um sich mit den Verpflichtungen vertraut zu machen, die möglicherweise für Ihre Bereitstellung von lync Server in ihren relevanten Regionen gelten.</span><span class="sxs-lookup"><span data-stu-id="afefe-110">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="afefe-111">**Welche Bereiche innerhalb Ihres Unternehmens müssen für E9-1-1 aktiviert werden?**</span><span class="sxs-lookup"><span data-stu-id="afefe-111">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="afefe-p103">Sie können E9-1-1 innerhalb des gesamten Unternehmens oder für ausgewählte Standorte aktivieren. Beispielsweise können für Büros in verschiedenen Staaten unterschiedliche E9-1-1-Anforderungen gelten und Standorte außerhalb der USA können ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="afefe-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="afefe-114">**Wie möchten Sie E9-1-1-Zweigstellen bereitstellen?**</span><span class="sxs-lookup"><span data-stu-id="afefe-114">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="afefe-115">Sie müssen mit dem Konzept der VoIP-Ausfallsicherheit für Zweigstellenstandorte vertraut sein, wenn Sie E9-1-1 in einer Zweigstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="afefe-115">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="afefe-116">Wenn Sie über zentralisierte E-9-1-1-SIP-Trunks verfügen und ein WAN-Ausfall auftritt, können Clients, die sich anmelden, möglicherweise keinen Standort vom standortinformationsdienst abrufen oder eine Verbindung mit dem Notdienste-Dienstanbieter herstellen.</span><span class="sxs-lookup"><span data-stu-id="afefe-116">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="afefe-117">Lync Server bietet verschiedene Strategien für die Behandlung von VoIP-Flexibilität in Zweigniederlassungen, einschließlich: mit belastbaren Datennetzwerken, Bereitstellungeines SIP-Trunks an jeder Verzweigung oder durch Drücken von Notrufen beim Ausfall des lokalen Gateways.</span><span class="sxs-lookup"><span data-stu-id="afefe-117">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="afefe-118">Ausführliche Informationen finden Sie unter [Planen der sprach Sicherheit in der Zweigstelle in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="afefe-118">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="afefe-119">**Planen Sie die Aktivierung von E9-1-1 für Benutzer außerhalb des Netzwerks?**</span><span class="sxs-lookup"><span data-stu-id="afefe-119">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="afefe-120">Die automatische Standorterfassung steht nur für Clients zur Verfügung, die sich im Netzwerk der Organisation befinden, sodass Ihre Organisation entscheiden muss, ob Sie E9-1-1-Anrufe unterstützt, die von lync-Clients außerhalb des Lokals getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="afefe-120">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises.</span></span> <span data-ttu-id="afefe-121">Möchten Sie beispielsweise Benutzern die Möglichkeit geben, Notrufe zu tätigen, wenn Sie von zu Hause oder von einem Kundenstandort aus arbeiten?</span><span class="sxs-lookup"><span data-stu-id="afefe-121">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="afefe-122">Wenn sich ein Client außerhalb des Unternehmensnetzwerks befindet, kann der Client so konfiguriert werden, dass er den Benutzer zur Eingabe eines Speicherorts auffordert.</span><span class="sxs-lookup"><span data-stu-id="afefe-122">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="afefe-123">Da diese vom Benutzer bereitgestellten Speicherorte jedoch nicht mit dem Master Street Address Guide (MSAG) vorab validiert werden können, muss der Dienstanbieter für Notdienste die Gültigkeit des Standorts verbal mit dem Anrufer bestätigen, bevor er den Anruf an den öffentlichen Sicherheits Beantwortungs Punkt (PSAP) weiterleiten kann.</span><span class="sxs-lookup"><span data-stu-id="afefe-123">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="afefe-124">Lync-Clients von Benutzern, die mithilfe von VPN eine Verbindung mit dem Netzwerk Ihrer Organisation herstellen, können interne IP-Adressinformationen aufnehmen, aber da diese Adressen nicht zur Identifizierung des tatsächlichen Standorts des Benutzers verwendet werden können, ist es wichtig, dass VPN-Subnetze vom standortinformationsdienst ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="afefe-124">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="afefe-125">**Möchten Sie eine Weiterleitung von Notrufen an Standorte außerhalb der USA bereitstellen?**</span><span class="sxs-lookup"><span data-stu-id="afefe-125">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="afefe-p106">Eine Notrufweiterleitung kann beispielsweise für Unternehmensbereiche bereitgestellt werden, für die kein Anbieter einer Notrufunterstützung zur Verfügung steht (beispielsweise an internationalen Standorten). Erstellen Sie hierzu einen neuen Standort, und weisen Sie den Standorten, die auf eine PSTN-Verwendung verweisen, bei der der Anruf durch das lokale Gateway weitergeleitet wird, VoIP-Richtlinien zu.</span><span class="sxs-lookup"><span data-stu-id="afefe-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

<span data-ttu-id="afefe-128"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="afefe-128"></div>

<span> </span>

</div>

</div>

</span></span></div>

