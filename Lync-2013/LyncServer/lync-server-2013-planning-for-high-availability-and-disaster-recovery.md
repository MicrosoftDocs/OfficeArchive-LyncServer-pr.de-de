---
title: 'Lync Server 2013: Planen der hohen Verfügbarkeit und der Notfallwiederherstellung'
description: 'Lync Server 2013: Planen von Höchstverfügbarkeit und Disaster Recovery'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb5f430201c48738421c4fbe72151ca58173898
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49442957"
---
# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="89ee9-103">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89ee9-103">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="89ee9-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="89ee9-104">

<span> </span></span></span>

<span data-ttu-id="89ee9-105">_**Letztes Änderungsdatum des Themas:** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="89ee9-105">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="89ee9-106">Wie in lync Server 2010 basiert das wichtigste Hochverfügbarkeits-Schema für die meisten Serverrollen in lync Server 2013 auf Server Redundanz über Pooling.</span><span class="sxs-lookup"><span data-stu-id="89ee9-106">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="89ee9-107">Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen.</span><span class="sxs-lookup"><span data-stu-id="89ee9-107">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="89ee9-108">Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors.</span><span class="sxs-lookup"><span data-stu-id="89ee9-108">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="89ee9-109">Lync Server 2013 fügt neue Disaster Recovery-Maßnahmen für Front-End-Pools hinzu, indem geografische dispersement Ihrer Server in zwei Rechenzentren eingeführt werden, um den Service fortzusetzen, wenn ein ganzer Pool oder eine gesamte Website heruntergefahren wird.</span><span class="sxs-lookup"><span data-stu-id="89ee9-109">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="89ee9-110">Lync Server 2013 verbessert auch die höhere Verfügbarkeit von Back-End-Servern, indem die synchrone SQL-Spiegelung für Ihre Back-End-Datenbankenunter stützt wird.</span><span class="sxs-lookup"><span data-stu-id="89ee9-110">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="89ee9-111">In diesem Abschnitt werden diese wichtigen Funktionen für hohe Verfügbarkeit und Disaster Recovery erläutert, und es werden auch die Schritte beschrieben, die Sie für eine hohe Verfügbarkeit und Disaster Recovery für Ihre anderen Serverrollen ausführen können.</span><span class="sxs-lookup"><span data-stu-id="89ee9-111">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="89ee9-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="89ee9-112">In This Section</span></span>

  - [<span data-ttu-id="89ee9-113">Notfallwiederherstellung eines Front-End-Pools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89ee9-113">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="89ee9-114">Notfallwiederherstellung für Edgeserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89ee9-114">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="89ee9-115">Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89ee9-115">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="89ee9-116">Anrufverwaltungsfunktionen für die Notfallwiederherstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89ee9-116">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="89ee9-117">Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89ee9-117">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="89ee9-118">Ausfallsicherheit für innerstädtische Standorte in Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="89ee9-118">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

<span data-ttu-id="89ee9-119"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="89ee9-119"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

