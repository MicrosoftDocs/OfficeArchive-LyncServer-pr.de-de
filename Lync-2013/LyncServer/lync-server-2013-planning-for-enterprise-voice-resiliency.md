---
title: 'Lync Server 2013: Planen der Ausfallsicherheit für Enterprise-VoIP'
description: 'Lync Server 2013: Planung für Enterprise-VoIP-Widerstandsfähigkeit.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice resiliency
ms:assetid: ca116700-1055-4ca5-9b87-4c7f380c3655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398840(v=OCS.15)
ms:contentKeyID: 48185408
ms.date: 10/17/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2adcf09b87264666924a16543a1b21e8e3cae39f
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49443006"
---
# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="c0e6c-103">Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0e6c-103">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="c0e6c-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="c0e6c-104">

<span> </span></span></span>

<span data-ttu-id="c0e6c-105">_**Letztes Änderungsdatum des Themas:** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="c0e6c-105">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="c0e6c-106">Die sprach Stabilität bezieht sich auf die Möglichkeit von Benutzern, weiterhin Anrufe zu tätigen und zu empfangen, wenn ein zentraler Standort, der lync Server 2013 hostet, nicht mehr zur Verfügung steht, ob es sich um einen WAN-Fehler (Wide Area Network) oder eine andere Ursache handelt.</span><span class="sxs-lookup"><span data-stu-id="c0e6c-106">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="c0e6c-107">Wenn ein zentraler Standort ausfällt, muss der Enterprise-VoIP-Dienst durch ein nahtloses Failover zu einer Sicherungswebsite unterbrechungsfrei fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="c0e6c-107">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="c0e6c-108">Bei einem WAN-Fehler müssen Branch Site-Aufrufe an ein lokales PSTN-Gateway umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c0e6c-108">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="c0e6c-109">In diesem Abschnitt wird die Planung der sprach Sicherheit bei einem zentralen Standort-oder WAN-Fehler erläutert.</span><span class="sxs-lookup"><span data-stu-id="c0e6c-109">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c0e6c-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c0e6c-110">In This Section</span></span>

  - [<span data-ttu-id="c0e6c-111">Planen von VoIP-Ausfallsicherheit für den zentralen Standort in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0e6c-111">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="c0e6c-112">Planen von VoIP-Ausfallsicherheit für Zweigstellen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0e6c-112">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

<span data-ttu-id="c0e6c-113"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="c0e6c-113"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

