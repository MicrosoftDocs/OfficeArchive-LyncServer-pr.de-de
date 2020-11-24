---
title: 'Lync Server 2013: Konfigurieren der Anrufsteuerung'
description: 'Lync Server 2013: Konfigurieren der Anrufsteuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c6da7e20f45e61f7364af3e8b749def05bd29fd
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394935"
---
# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="e7aa8-103">Konfigurieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7aa8-103">Configure call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e7aa8-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e7aa8-104">

<span> </span></span></span>

<span data-ttu-id="e7aa8-105">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e7aa8-105">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e7aa8-106">Anrufannahme Steuerung (CAC) ist eine Lösung, die bestimmt, ob eine Echtzeitsitzung basierend auf der verfügbaren Bandbreite eingerichtet werden kann, um die schlechte Audio-und Videoqualität für Benutzer in überlasteten Netzwerken zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="e7aa8-106">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="e7aa8-107">CAC steuert den Echtzeitverkehr nur für Audio und Video und hat keinen Einfluss auf den Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="e7aa8-107">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="e7aa8-108">CAC kann den Anruf über einen Internet Pfad weiterleiten, wenn der standardmäßige WAN-Pfad nicht die erforderliche Bandbreite aufweist.</span><span class="sxs-lookup"><span data-stu-id="e7aa8-108">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="e7aa8-109">Ausführliche Informationen finden Sie unter [Planen der Anrufsteuerung in lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e7aa8-109">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="e7aa8-110">Dieser Abschnitt enthält eine Reihe von Beispielverfahren, die veranschaulichen, wie CAC in Ihrem Netzwerk bereitgestellt und verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="e7aa8-110">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7aa8-111">Bevor Sie CAC bereitstellen, müssen Sie alle erforderlichen Informationen für Ihre Unternehmensnetzwerk Topologie sammeln, wie in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Beispiel: Sammeln Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013</A> in der Planungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e7aa8-111">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="e7aa8-112">Stellen Sie außerdem sicher, dass CAC-Komponenten installiert und aktiviert wurden, wie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in lync Server 2013</A> beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e7aa8-112">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e7aa8-113">Alle Beispiele für die CAC-Bereitstellung und-Verwaltung in diesem Abschnitt werden mithilfe der lync Server-Verwaltungsshell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e7aa8-113">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="e7aa8-114">Alternativ können Sie auch den Abschnitt <STRONG>Netzwerkkonfiguration</STRONG> der lync Server-Systemsteuerung verwenden, um CAC zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e7aa8-114">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e7aa8-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e7aa8-115">In This Section</span></span>

  - [<span data-ttu-id="e7aa8-116">Konfigurieren von netzwerkregionen für CAC in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7aa8-116">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="e7aa8-117">Erstellen von Bandbreitenrichtlinien Profilen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7aa8-117">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="e7aa8-118">Konfigurieren von Netzwerk Websites für CAC in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7aa8-118">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="e7aa8-119">Zuordnen von Subnetzen zu Netzwerkstandorten für CAC in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7aa8-119">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="e7aa8-120">Erstellen von Netzwerkbereichs Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7aa8-120">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="e7aa8-121">Erstellen von Netzwerk interregions-Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7aa8-121">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="e7aa8-122">Erstellen von Netzwerk-standortübergreifenden Richtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7aa8-122">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="e7aa8-123">Aktivieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7aa8-123">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="e7aa8-124">Checkliste für die Bereitstellung der Anrufsteuerung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7aa8-124">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

<span data-ttu-id="e7aa8-125"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e7aa8-125"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

