---
title: 'Lync Server 2013: Topologien und Komponenten für Front-End-Server, Chat und Anwesenheit'
description: 'Lync Server 2013: Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheitsinformationen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 474911ef0e60d57151aa778688cf2e6a8e1bfcf7
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49439681"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="d272c-103">Topologien und Komponenten für Front-End-Server, Chat und Anwesenheit in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d272c-103">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="d272c-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="d272c-104">

<span> </span></span></span>

<span data-ttu-id="d272c-105">_**Letztes Änderungsdatum des Themas:** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="d272c-105">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="d272c-106">Für Chat und Anwesenheit sind nur diese Komponenten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="d272c-106">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="d272c-107">Die Front-End-Server Ihrer Organisation oder Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="d272c-107">Your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="d272c-108">Chat und Anwesenheitsfunktionen sind auf diesen Servern immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d272c-108">IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="d272c-109">Ein Lastenausgleich, wenn Sie einen Enterprise Edition-Front-End-Pool haben.</span><span class="sxs-lookup"><span data-stu-id="d272c-109">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="d272c-110">Weitere Informationen finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d272c-110">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="d272c-111">Planen der Bereitstellung von Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="d272c-111">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="d272c-112">In lync Server 2013 hat sich die Architektur des Front-End-Pools geändert, und diese Änderungen beeinflussen, wie Sie Ihre Front-End-Pools planen und verwalten sollten.</span><span class="sxs-lookup"><span data-stu-id="d272c-112">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="d272c-113">Wir empfehlen, dass alle Ihre Enterprise Edition-Front-End-Pools mindestens drei Front-End-Server enthalten.</span><span class="sxs-lookup"><span data-stu-id="d272c-113">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="d272c-114">In lync Server verwendet die Architektur der Front-End-Pools ein Modell mit verteilten Systemen, wobei die Daten jedes Benutzers auf drei Front-End-Servern im Pool aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="d272c-114">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="d272c-115">Weitere Informationen zu dieser neuen Architektur finden Sie unter [Topologie-Änderungen in lync Server 2013](lync-server-2013-topology-changes.md).</span><span class="sxs-lookup"><span data-stu-id="d272c-115">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="d272c-116">Wenn Sie keine drei Enterprise Edition-Front-End-Server bereitstellen möchten und eine Disaster Recovery wünschen, empfehlen wir die Verwendung von lync Server Standard Edition und das Erstellen von zwei Pools mit einer gekoppelten Sicherungsbeziehung.</span><span class="sxs-lookup"><span data-stu-id="d272c-116">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="d272c-117">Dadurch wird eine Disaster Recovery-Lösung mit nur zwei Servern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d272c-117">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="d272c-118">Weitere Informationen zu Hochverfügbarkeits-und Disaster Recovery-Topologien und-Features finden Sie unter [Planen von höchst Verfügbarkeit und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="d272c-118">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="d272c-119">Planen der Verwaltung von Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="d272c-119">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="d272c-120">Befolgen Sie für Front-End-Pools die Richtlinien in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="d272c-120">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="d272c-121">Sicherstellen, dass Pools funktionsfähig sind</span><span class="sxs-lookup"><span data-stu-id="d272c-121">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="d272c-122">Mit dem neuen verteilten Modell für Front-End-Pools müssen bestimmte Nummern der Server eines Pools ausgeführt werden, damit der Pool funktioniert.</span><span class="sxs-lookup"><span data-stu-id="d272c-122">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="d272c-123">Es gibt zwei Verlust Modi für einen Pool</span><span class="sxs-lookup"><span data-stu-id="d272c-123">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="d272c-124">Quorumverlust auf Routinggruppenebene, wenn nicht genügend Replikatserver für eine bestimmte Routinggruppe vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d272c-124">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="d272c-125">Eine Routinggruppe ist eine Aggregation einer Gruppe von Benutzern, die im Pool verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d272c-125">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="d272c-126">Jede Routinggruppe verfügt über drei Replikate im Pool: eine primäre und zwei Sekundär Gruppen.</span><span class="sxs-lookup"><span data-stu-id="d272c-126">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="d272c-127">Quorumverlust auf Poolebene, der verursacht wird, wenn nicht genügend Seedserver im Pool aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="d272c-127">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="d272c-128">Quorumverlust auf Routinggruppenebene</span><span class="sxs-lookup"><span data-stu-id="d272c-128">Routing Group Level quorum loss</span></span>

<span data-ttu-id="d272c-p107">Wenn Sie einen neuen Front-End-Pool zum ersten Mal starten, ist es wichtig, dass wie in der folgenden Tabelle gezeigt 85 % der Server aktiv sind. Wenn weniger Server aktiv sind, bleiben die Dienste möglicherweise im Startstatus hängen und der Pool wird nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="d272c-p107">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table. If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d272c-131">Gesamtzahl der Server im Pool</span><span class="sxs-lookup"><span data-stu-id="d272c-131">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="d272c-132">Anzahl der Server, die aktiv sein müssen, damit der Pool zum ersten Mal gestartet wird</span><span class="sxs-lookup"><span data-stu-id="d272c-132">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d272c-133">2</span><span class="sxs-lookup"><span data-stu-id="d272c-133">2</span></span></p></td>
<td><p><span data-ttu-id="d272c-134">1</span><span class="sxs-lookup"><span data-stu-id="d272c-134">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d272c-135">3</span><span class="sxs-lookup"><span data-stu-id="d272c-135">3</span></span></p></td>
<td><p><span data-ttu-id="d272c-136">3</span><span class="sxs-lookup"><span data-stu-id="d272c-136">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d272c-137">4</span><span class="sxs-lookup"><span data-stu-id="d272c-137">4</span></span></p></td>
<td><p><span data-ttu-id="d272c-138">3</span><span class="sxs-lookup"><span data-stu-id="d272c-138">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d272c-139">5</span><span class="sxs-lookup"><span data-stu-id="d272c-139">5</span></span></p></td>
<td><p><span data-ttu-id="d272c-140">4</span><span class="sxs-lookup"><span data-stu-id="d272c-140">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d272c-141">6</span><span class="sxs-lookup"><span data-stu-id="d272c-141">6</span></span></p></td>
<td><p><span data-ttu-id="d272c-142">5</span><span class="sxs-lookup"><span data-stu-id="d272c-142">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d272c-143">7</span><span class="sxs-lookup"><span data-stu-id="d272c-143">7</span></span></p></td>
<td><p><span data-ttu-id="d272c-144">5</span><span class="sxs-lookup"><span data-stu-id="d272c-144">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d272c-145">8</span><span class="sxs-lookup"><span data-stu-id="d272c-145">8</span></span></p></td>
<td><p><span data-ttu-id="d272c-146">6</span><span class="sxs-lookup"><span data-stu-id="d272c-146">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d272c-147">9</span><span class="sxs-lookup"><span data-stu-id="d272c-147">9</span></span></p></td>
<td><p><span data-ttu-id="d272c-148">7</span><span class="sxs-lookup"><span data-stu-id="d272c-148">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d272c-149">10</span><span class="sxs-lookup"><span data-stu-id="d272c-149">10</span></span></p></td>
<td><p><span data-ttu-id="d272c-150">8</span><span class="sxs-lookup"><span data-stu-id="d272c-150">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d272c-151">11</span><span class="sxs-lookup"><span data-stu-id="d272c-151">11</span></span></p></td>
<td><p><span data-ttu-id="d272c-152">9</span><span class="sxs-lookup"><span data-stu-id="d272c-152">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d272c-153">12</span><span class="sxs-lookup"><span data-stu-id="d272c-153">12</span></span></p></td>
<td><p><span data-ttu-id="d272c-154">10</span><span class="sxs-lookup"><span data-stu-id="d272c-154">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d272c-155">Bei jedem nachfolgenden Start des Pools sollten 85 % der Server gestartet werden (wie in der vorstehenden Tabelle gezeigt).</span><span class="sxs-lookup"><span data-stu-id="d272c-155">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="d272c-156">Wenn diese Anzahl von Servern nicht gestartet werden kann (aber ausreichend Server gestartet werden können, damit kein Quorumverlust auf Poolebene auftritt), können Sie das Cmdlet **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** verwenden, damit der Pool aus diesem Quorumverlust auf Routinggruppenebene wiederhergestellt werden und sich aufbauen kann.</span><span class="sxs-lookup"><span data-stu-id="d272c-156">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="d272c-157">Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span><span class="sxs-lookup"><span data-stu-id="d272c-157">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d272c-158">Da lync Server die primäre SQL-Datenbank als Zeuge verwendet, wenn Sie die primäre Datenbank Herunterfahren und zur Spiegelungskopie wechseln und genügend Front-End-Server herunterfahren, sodass nicht genügend entsprechend der vorhergehenden Tabelle ausgeführt wird, wird der gesamte Pool heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="d272c-158">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="d272c-159">Weitere Informationen finden Sie unter <A href="https://go.microsoft.com/fwlink/?linkid=393672">Daten Bank Spiegelungs Zeuge</A>.</span><span class="sxs-lookup"><span data-stu-id="d272c-159">For more information, see <A href="https://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="d272c-160">Quorumverlust auf Poolebene</span><span class="sxs-lookup"><span data-stu-id="d272c-160">Pool-level quorum loss</span></span>

<span data-ttu-id="d272c-161">Damit ein Front-End-Pool überhaupt funktioniert, kann er keinen Quorum Verlust auf Poolebene aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d272c-161">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="d272c-162">Wenn die Anzahl der ausgeführten Server unter die Funktionsebene fällt, wie in der folgenden Tabelle dargestellt, beenden die restlichen Server im Pool alle lync Server-Dienste.</span><span class="sxs-lookup"><span data-stu-id="d272c-162">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="d272c-163">Beachten Sie, dass die Zahlen in der folgenden Tabelle davon ausgehen, dass die Back-End-Server im Pool ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d272c-163">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d272c-164">Gesamtzahl der Front-End-Server im Pool</span><span class="sxs-lookup"><span data-stu-id="d272c-164">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="d272c-165">Anzahl der Server, die aktiv sein müssen, damit der Pool funktioniert</span><span class="sxs-lookup"><span data-stu-id="d272c-165">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d272c-166">2</span><span class="sxs-lookup"><span data-stu-id="d272c-166">2</span></span></p></td>
<td><p><span data-ttu-id="d272c-167">1</span><span class="sxs-lookup"><span data-stu-id="d272c-167">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d272c-168">3-4</span><span class="sxs-lookup"><span data-stu-id="d272c-168">3-4</span></span></p></td>
<td><p><span data-ttu-id="d272c-169">Beliebige 2</span><span class="sxs-lookup"><span data-stu-id="d272c-169">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d272c-170">5-6</span><span class="sxs-lookup"><span data-stu-id="d272c-170">5-6</span></span></p></td>
<td><p><span data-ttu-id="d272c-171">Beliebige 3</span><span class="sxs-lookup"><span data-stu-id="d272c-171">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d272c-172">7</span><span class="sxs-lookup"><span data-stu-id="d272c-172">7</span></span></p></td>
<td><p><span data-ttu-id="d272c-173">Beliebige 4</span><span class="sxs-lookup"><span data-stu-id="d272c-173">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d272c-174">8-9</span><span class="sxs-lookup"><span data-stu-id="d272c-174">8-9</span></span></p></td>
<td><p><span data-ttu-id="d272c-175">Beliebige 4 der ersten 7 Server</span><span class="sxs-lookup"><span data-stu-id="d272c-175">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d272c-176">10-12</span><span class="sxs-lookup"><span data-stu-id="d272c-176">10-12</span></span></p></td>
<td><p><span data-ttu-id="d272c-177">Beliebige 5 der ersten 9 Server</span><span class="sxs-lookup"><span data-stu-id="d272c-177">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d272c-178">In der vorstehenden Tabelle sind die "ersten Server" die Server, die in chronologischer Reihenfolge beim ersten Start des Pools aufgeholt wurden.</span><span class="sxs-lookup"><span data-stu-id="d272c-178">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="d272c-179">Um diese Server zu ermitteln, können Sie das Cmdlet " **Get-CsComputer** " mit der Option " **– PoolFqdn** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="d272c-179">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="d272c-180">Dieses Cmdlet zeigt die Server in der Reihenfolge an, in der Sie in der Topologie angezeigt werden, und die oben in der Liste sind die ersten Server.</span><span class="sxs-lookup"><span data-stu-id="d272c-180">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="d272c-181">Front-End-Pools mit zwei Front-End-Servern</span><span class="sxs-lookup"><span data-stu-id="d272c-181">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="d272c-182">Wir empfehlen nicht die Bereitstellungeines Front-End-Pools, in dem nur zwei Front-End-Server enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d272c-182">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="d272c-183">Wenn Sie einen solchen Pool überhaupt bereitstellen müssen, befolgen Sie diese Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="d272c-183">If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="d272c-184">Wenn einer der beiden Front-End-Server ausfällt, sollten Sie versuchen, den fehlerhaften Server so schnell wie möglich wieder aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d272c-184">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="d272c-185">Entsprechend sollten Sie, wenn Sie einen der beiden Server upgraden müssen, diesen Server so bald wie möglich nach Abschluss des Upgrades wieder online schalten.</span><span class="sxs-lookup"><span data-stu-id="d272c-185">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="d272c-186">Falls Sie aus irgendeinem Grund beide Server gleichzeitig herunterfahren müssen, führen Sie nach Beendigung der Downtime für den Pool folgende Schritte durch:</span><span class="sxs-lookup"><span data-stu-id="d272c-186">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="d272c-187">Die bewährte Vorgehensweise besteht darin, beide Front-End-Server gleichzeitig neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="d272c-187">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="d272c-188">Ist dies nicht möglich, sollten Sie sie in der umgekehrten Reihenfolge wieder hochfahren, in der sie heruntergefahren wurden.</span><span class="sxs-lookup"><span data-stu-id="d272c-188">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="d272c-189">Wenn Sie Sie nicht in dieser Reihenfolge sichern können, verwenden Sie das folgende Cmdlet, bevor Sie den Pool sichern:.</span><span class="sxs-lookup"><span data-stu-id="d272c-189">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="d272c-190">Zusätzliche Schritte, um sicherzustellen, dass Pools funktionsfähig sind</span><span class="sxs-lookup"><span data-stu-id="d272c-190">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="d272c-191">Sie sollten auf eine Reihe anderer Faktoren achten, um sicherzustellen, dass Ihre Front-End-Pools funktionsbereit bleiben.</span><span class="sxs-lookup"><span data-stu-id="d272c-191">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="d272c-192">Wenn Sie Benutzer zum ersten Mal in den Pool verschieben, stellen Sie sicher, dass mindestens drei der Front-End-Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d272c-192">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="d272c-193">Wenn Sie eine Kopplungs Beziehung zwischen diesem Pool und einem anderen Pool für Disaster Recovery-Zwecke einrichten, müssen Sie nach dem Einrichten dieser Beziehung sicherstellen, dass dieser Pool über drei Front-End-Server verfügt, die gleichzeitig ausgeführt werden, um Daten ordnungsgemäß mit dem Sicherungspool zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="d272c-193">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="d272c-194">Weitere Informationen zu Pool-Kopplungs-und Disaster Recovery-Features finden Sie unter [Planen von Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="d272c-194">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="d272c-195">Verbessern der Zuverlässigkeit von Pool-Upgrades</span><span class="sxs-lookup"><span data-stu-id="d272c-195">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="d272c-196">Wenn Sie die Server in einem Front-End-Pool aktualisieren oder patchen müssen, folgen Sie dem Workflow, der unter [Upgrade-oder Update-Front-End-Server in lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)angezeigt wird, und den folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="d272c-196">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="d272c-197">Wenn Sie für Upgrades von einer Upgrade-Domäne zu einem anderen wechseln (nach dem Workflow bei der [Aktualisierung oder Aktualisierung der Front-End-Server in lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), verwenden Sie das Cmdlet **Get-CsPoolUpgradeReadinessState** , und überprüfen Sie den Status bereit.</span><span class="sxs-lookup"><span data-stu-id="d272c-197">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="d272c-198">Das Hinzufügen eines 20-minütigen Wartens zwischen jeder Upgrade-Domäne, nachdem es "Ready" erreicht hat, macht die Upgrades zuverlässiger.</span><span class="sxs-lookup"><span data-stu-id="d272c-198">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="d272c-199">Wenn es während dieser 20 Minuten **nicht bereit** ist, starten Sie den 20-minütigen Timer erneut.</span><span class="sxs-lookup"><span data-stu-id="d272c-199">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="d272c-200">Darüber hinaus können Sie das Cmdlet " **Get-CsPoolFabricState** " vor und nach dem Start des 20-minütigen Intervalls ausführen und sicherstellen, dass keine Änderungen an den Vorwahlen und Sekundär Personen von Routinggruppen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="d272c-200">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="d272c-201">Wechseln Sie nicht zur nächsten Upgrade-Domäne, wenn einer der Server in der letzten gepatchten Upgrade-Domäne hängen bleibt oder nicht neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="d272c-201">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="d272c-202">Dies gilt auch, wenn einer der Server in einem Upgrade nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d272c-202">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="d272c-203">Führen **Sie Get-CsPoolFabricState** aus, um sicherzustellen, dass alle Routinggruppen über eine primäre und mindestens eine sekundäre Gruppe verfügen. Dadurch wird bestätigt, ob alle Benutzer über einen Dienst verfügen.</span><span class="sxs-lookup"><span data-stu-id="d272c-203">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="d272c-204">Wenn einige Benutzer über einen Dienst verfügen und andere dies nicht tun, führen **Sie Get-CsPoolFabricState** mit der Option – verbose aus, um nach Routinggruppen zu suchen, die fehlende Replikate aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d272c-204">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="d272c-205">Starten Sie den gesamten Pool nicht als ersten Schritt zur Problembehandlung neu.</span><span class="sxs-lookup"><span data-stu-id="d272c-205">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="d272c-206">Weitere Informationen zu diesem Cmdlet finden Sie unter [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span><span class="sxs-lookup"><span data-stu-id="d272c-206">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="d272c-207">Stellen Sie sicher, dass alle Instanzen der Ereignisanzeige oder des Leistungsmonitors für Windows Fabric-Installationen/-Deinstallationen geschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="d272c-207">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="d272c-208">Ändern der Konfiguration eines Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="d272c-208">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="d272c-209">Wenn Sie einem Pool Front-End-Server hinzufügen oder aus dem Pool entfernen und dann die neue Topologie veröffentlichen, befolgen Sie diese Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="d272c-209">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="d272c-210">Nachdem die neue Topologie veröffentlicht wurde, müssen Sie jeden Front-End-Server im Pool neu starten.</span><span class="sxs-lookup"><span data-stu-id="d272c-210">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="d272c-211">Starten Sie die Server einen nach dem anderen neu.</span><span class="sxs-lookup"><span data-stu-id="d272c-211">Restart them one at a time.</span></span>

  - <span data-ttu-id="d272c-212">Wenn der gesamte Pool während der Konfigurationsänderung inaktiv war, führen Sie nach der Veröffentlichung der neuen Topologie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="d272c-212">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="d272c-213">Wenn ein Front-End-Server ausfällt und für ein paar Tage oder mehr wahrscheinlich nicht ersetzt wird, entfernen Sie den Server aus der Topologie.</span><span class="sxs-lookup"><span data-stu-id="d272c-213">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="d272c-214">Fügen Sie den neuen Front-End-Server zur Topologie hinzu, wenn er wieder verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d272c-214">Add the new Front End Server to the topology when it is available again.</span></span>

<span data-ttu-id="d272c-215"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="d272c-215"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

