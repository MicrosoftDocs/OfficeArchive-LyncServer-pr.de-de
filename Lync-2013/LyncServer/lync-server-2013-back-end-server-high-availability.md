---
title: 'Lync Server 2013: höchst Verfügbarkeit des Back-End-Servers'
description: 'Lync Server 2013: Server für den Back-End-Server mit höherer Verfügbarkeit.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 805cbf96e107329aa5c374cfa1e2d01234d360a3
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49438134"
---
# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="be88e-103">Höhere Verfügbarkeit von Back-End-Servern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be88e-103">Back End Server high availability in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="be88e-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="be88e-104">

<span> </span></span></span>

<span data-ttu-id="be88e-105">_**Letztes Änderungsdatum des Themas:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="be88e-105">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="be88e-106">Um eine optimale Verfügbarkeit für Ihre Back-End-Server zu gewährleisten, können Sie entweder synchrone SQL-Spiegelung oder SQL-Clustering verwenden.</span><span class="sxs-lookup"><span data-stu-id="be88e-106">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="be88e-107">Die Verwendung einer dieser Lösungen ist optional, wird jedoch empfohlen, um die Geschäftskontinuität in Ihrer Organisation beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="be88e-107">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="be88e-108">Die asynchrone SQL-Spiegelung wird für den Back-End-Server mit einer höheren Verfügbarkeit in lync Server 2013 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be88e-108">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="be88e-109">Im restlichen Dokument bedeutet SQL-Spiegelung eine synchrone SQL-Spiegelung, sofern nichts anderes ausdrücklich angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="be88e-109">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="be88e-110">Sie können die SQL-Spiegelung mit dem Topology Builder ganz einfach einrichten.</span><span class="sxs-lookup"><span data-stu-id="be88e-110">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="be88e-111">Zum Einrichten von SQL-Failoverclustering müssen Sie SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="be88e-111">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="be88e-112">Wenn Sie entweder SQL-Spiegelung oder SQL-Clustering in einem Pool verwenden, der mit einem anderen Front-End-Pool für die Disaster Recovery gekoppelt ist, sollten Sie in beiden Pools dieselbe Lösung für das Back-End-Angebot verwenden.</span><span class="sxs-lookup"><span data-stu-id="be88e-112">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="be88e-113">Mit SQL-Clustering sollten Sie keinen Pool mit SQL-Spiegelung mit einem Pool koppeln.</span><span class="sxs-lookup"><span data-stu-id="be88e-113">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="be88e-114">Wenn Sie die SQL-Spiegelung bereitstellen, werden alle lync Server-Datenbanken im Pool gespiegelt, einschließlich des zentralen Verwaltungsspeichers, wenn Sie sich in diesem Pool befinden, sowie die Anwendungsdatenbank der Reaktionsgruppe und die Anwendungsdatenbank des Anruf Parks, wenn diese Anwendungen im Pool ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="be88e-114">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="be88e-115">Bei der SQL-Spiegelung müssen Sie keinen freigegebenen Speicher für die Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="be88e-115">With SQL mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="be88e-116">Jeder Server verwaltet eine Kopie der Datenbanken im lokalen Speicher.</span><span class="sxs-lookup"><span data-stu-id="be88e-116">Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="be88e-117">Sie können festlegen, dass die SQL-Spiegelung mit oder ohne Zeugen bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="be88e-117">You may choose to deploy SQL mirroring with or without a witness.</span></span> <span data-ttu-id="be88e-118">Wir empfehlen die Verwendung eines Spiegelungszeugen, da dadurch das automatische Failover des Back-End-Servers ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="be88e-118">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="be88e-119">Andernfalls muss ein Administrator das Failover manuell auslösen.</span><span class="sxs-lookup"><span data-stu-id="be88e-119">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="be88e-120">Beachten Sie, dass selbst bei der Bereitstellung eines Spiegelungszeugen ein Administrator bei Bedarf das Failover des Back-End-Servers manuell auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="be88e-120">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="be88e-p106">Wenn Sie einen Spiegelungszeugen verwenden, können Sie einen einzelnen Spiegelungszeugen für mehrere Back-End-Serverpaare verwenden. Es gibt keine strikte 1:1-Entsprechung zwischen Spiegelungszeugen und Back-End-Serverpaaren. Bereitstellungen, bei denen ein einzelner Spiegelungszeuge für mehrere Back-End-Serverpaare verwendet wird, sind nicht ganz so stabil wie Topologien mit einem separaten Spiegelungszeugen für jedes Back-End-Serverpaar.</span><span class="sxs-lookup"><span data-stu-id="be88e-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="be88e-124">Weitere Informationen zur Unterstützung von SQL-Clustern finden Sie unter unter [Stützung von Datenbanksoftware in lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="be88e-124">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="be88e-125">Details zum Bereitstellen von SQL-Clustering finden Sie unter [Konfigurieren des SQL Server-Clusters für lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="be88e-125">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="be88e-126">Wiederherstellungszeit für automatisches Failover des Back-End-Servers mit SQL-Spiegelung</span><span class="sxs-lookup"><span data-stu-id="be88e-126">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="be88e-127">Für das automatische Back-End-Failover mit SQL-Spiegelung beträgt das Entwicklungsziel für das Wiederherstellungszeitziel (RTO) 5 Minuten.</span><span class="sxs-lookup"><span data-stu-id="be88e-127">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="be88e-128">Aufgrund der synchronen SQL-Spiegelung erwarten wir keine Datenverluste bei Back-End-Serverfehlern, außer in seltenen Fällen, in denen sowohl die Front-End-Server als auch der Back-End-Server gleichzeitig Herunterfahren, während Daten zwischen den Servern verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="be88e-128">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="be88e-129">Für den Wiederherstellungspunkt (Recovery Point Objective, RPO) wird ein Zielwert von 5 Minuten angestrebt.</span><span class="sxs-lookup"><span data-stu-id="be88e-129">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="be88e-130">Benutzerfreundlichkeit während des Back-End-Server Fehlers bei der SQL-Spiegelung</span><span class="sxs-lookup"><span data-stu-id="be88e-130">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="be88e-131">Die Benutzerfreundlichkeit bei einem Ausfall hängt von der Art des Ausfalls und Ihrer Topologie ab.</span><span class="sxs-lookup"><span data-stu-id="be88e-131">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="be88e-132">Wenn Sie die SQL-Spiegelung verwenden und einen Zeugen konfiguriert haben und der Prinzipal fehlschlägt, erfolgt das Failover des Back-End-Servers automatisch und schnell.</span><span class="sxs-lookup"><span data-stu-id="be88e-132">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="be88e-133">Aktive Benutzer sollten bei ihren laufenden Sitzungen keine große Unterbrechung feststellen.</span><span class="sxs-lookup"><span data-stu-id="be88e-133">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="be88e-134">Wenn kein Zeuge konfiguriert ist, dauert es einige Zeit, bis der Administrator das Failover manuell aufruft.</span><span class="sxs-lookup"><span data-stu-id="be88e-134">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="be88e-135">Während dieser Zeit sind möglicherweise aktive Benutzer betroffen.</span><span class="sxs-lookup"><span data-stu-id="be88e-135">During that time, active users may be affected.</span></span> <span data-ttu-id="be88e-136">Sie werden Ihre Sitzungen wie gewohnt für etwa 30 Minuten fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="be88e-136">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="be88e-137">Wenn die primäre Person immer noch nicht wiederhergestellt wird oder ein Administrator nicht an die Sicherung gescheitert ist, werden die Benutzer in den Stabilitäts Modus versetzt, was bedeutet, dass Sie keine Aufgaben ausführen können, die eine dauerhafte Änderung auf lync Server erfordern (beispielsweise das Hinzufügen eines Kontakts).</span><span class="sxs-lookup"><span data-stu-id="be88e-137">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="be88e-p111">Wenn sowohl der Prinzipalserver als auch der Spiegel-Back-End-Server ausfallen oder wenn einer dieser Server und der Spiegelungszeuge ausfallen, ist der Back-End-Server nicht mehr verfügbar (selbst wenn der Prinzipalserver weiterhin einsatzbereit ist). In diesem Fall werden die aktiven Benutzer nach einer Weile auf den Ausfallsicherheitsmodus umgestellt.</span><span class="sxs-lookup"><span data-stu-id="be88e-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

<span data-ttu-id="be88e-140"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="be88e-140"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

