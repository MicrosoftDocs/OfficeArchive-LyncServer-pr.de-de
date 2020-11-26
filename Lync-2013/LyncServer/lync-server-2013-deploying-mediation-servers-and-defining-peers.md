---
title: 'Lync Server 2013: Bereitstellen von Vermittlungsservern und Definieren von Peers'
description: 'Lync Server 2013: Bereitstellen von Vermittlungsservern und Definieren von Peers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc3afce038371920beea1cc52549d8d027429e08
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49429895"
---
# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="b89ec-103">Bereitstellen von Vermittlungsservern und Definieren von Peers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b89ec-103">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="b89ec-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="b89ec-104">

<span> </span></span></span>

<span data-ttu-id="b89ec-105">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b89ec-105">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b89ec-106">Die Enterprise-VoIP-Arbeitsauslastung, Einwahlkonferenzen und erweiterte Enterprise-VoIP-Anwendungen (reaktionsgruppenanwendung, Anruf Park Anwendung, Anrufsteuerung (CAC) usw.) stehen in Front-End-Pools zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b89ec-106">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="b89ec-107">Mit lync Server 2013 ist die Funktionalität des Vermittlungsservers in den Front-End-Server integriert.</span><span class="sxs-lookup"><span data-stu-id="b89ec-107">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="b89ec-108">Ein separater eigenständiger Vermittlungs Server ist nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b89ec-108">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="b89ec-109">Front-End-Pools können direkt mit unterstützten Gateways (einem Public Switched Telephone Network (PSTN)-Gateway oder einer IP-Telefonanlage) kommunizieren, wodurch die Notwendigkeit eines Vermittlungsservers, der als Vermittler fungiert, entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="b89ec-109">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="b89ec-110">Die einzige Ausnahme stellt die Konfiguration eines SIP-Trunks zum Herstellen einer Verbindung mit einem Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten dar.</span><span class="sxs-lookup"><span data-stu-id="b89ec-110">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="b89ec-111">Wenn Sie Ihre Enterprise-VoIP-Infrastruktur mit Ihrem SIP-Trunk-Anbieter verbinden möchten, muss ein separater Vermittlungs Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b89ec-111">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="b89ec-112">Die Verbindung zwischen lync Server (der Vermittlungsserver Komponente in einem Front-End-Pool oder einem eigenständigen Vermittlungsserver) und einem Gateway wird als logische Zuordnung als " *trunk*" definiert.</span><span class="sxs-lookup"><span data-stu-id="b89ec-112">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="b89ec-113">In den Themen in diesem Abschnitt wird beschrieben, wie Sie einen trunk definieren und wie Sie einen eigenständigen Vermittlungs Server bereitstellen, wenn Sie eine Verbindung mit einem SIP-Stamm herstellen.</span><span class="sxs-lookup"><span data-stu-id="b89ec-113">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b89ec-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b89ec-114">In This Section</span></span>

  - [<span data-ttu-id="b89ec-115">Definieren eines Vermittlungsservers im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b89ec-115">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="b89ec-116">Definieren eines Gateways im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b89ec-116">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="b89ec-117">Installieren der Dateien für den Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b89ec-117">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="b89ec-118">Definieren zusätzlicher Trunks im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b89ec-118">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="b89ec-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b89ec-119">Related Sections</span></span>

[<span data-ttu-id="b89ec-120">Konfigurieren von Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b89ec-120">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

<span data-ttu-id="b89ec-121"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="b89ec-121"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

