---
title: 'Lync Server 2013: Definieren der Anforderungen Ihrer Organisation an den Server für beständigen Chat'
description: 'Lync Server 2013: Definieren Ihrer Anforderungen für den beständigen Chat Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af3fab1d91b78a5993f723b8fc6b375e4ab7cee
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49430784"
---
# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="e9ef3-103">Definieren der Anforderungen Ihrer Organisation an den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9ef3-103">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e9ef3-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e9ef3-104">

<span> </span></span></span>

<span data-ttu-id="e9ef3-105">_**Letztes Änderungsdatum des Themas:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="e9ef3-105">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="e9ef3-106">Bevor Sie den beständigen Chat Server für Ihre Organisation bereitstellen, müssen Sie unbedingt die folgenden wichtigen Fragen zur Optimierung Ihrer Bereitstellung in Frage stellen:</span><span class="sxs-lookup"><span data-stu-id="e9ef3-106">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="e9ef3-107">Wer (Benutzerprofil) sollte für beständigen Chat Server aktiviert sein?</span><span class="sxs-lookup"><span data-stu-id="e9ef3-107">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="e9ef3-108">Der Server für beständigen Chat wird durch eine Richtlinie aktiviert, die auf globaler, Website-, Pool-oder Benutzerebene festgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-108">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="e9ef3-109">Wie viele Benutzer (Skalierung) sollten für beständigen Chat Server aktiviert sein?</span><span class="sxs-lookup"><span data-stu-id="e9ef3-109">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="e9ef3-110">Der beständige Chat Server unterstützt 150.000 bereitgestellte Benutzer (aktiviert durch Richtlinie) und maximal 80.000 gleichzeitige Benutzer, die den beständigen Chat Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-110">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="e9ef3-111">Ein einzelner Server für beständigen Chat kann 20.000 verbundene Benutzer unterstützen und ein Serverpool für beständigen Chat kann bis zu 4 aktive Server für insgesamt 80.000 gleichzeitig verbundene Benutzer bedienen.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-111">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="e9ef3-112">Migrieren Sie von einer früheren Version des Gruppen-Chat Servers, oder stellen Sie zum ersten Mal einen beständigen Chat Server bereit?</span><span class="sxs-lookup"><span data-stu-id="e9ef3-112">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="e9ef3-113">Gibt es Compliance-Anforderungen?</span><span class="sxs-lookup"><span data-stu-id="e9ef3-113">Are there compliance requirements?</span></span> <span data-ttu-id="e9ef3-114">Der beständige Chat Server unterstützt Compliance.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-114">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="e9ef3-115">Der Kompatibilitätsdienst wird auf dem Front-End-Server für beständigen Chat Server ausgeführt, im Gegensatz zur Anforderung für einen separaten Computer in vorherigen Gruppen Chat Server Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-115">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="e9ef3-116">Compliance ist optional und erfordert bei Auswahl eine Kompatibilitätsdatenbank, die zum Speichern von Kompatibilitätsdaten und Ereignissen konfiguriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-116">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="e9ef3-117">Möglicherweise möchten Sie auch einen Adapter konfigurieren, um die Daten aus der Kompatibilitätsdatenbank zu übernehmen und in ein anderes Format (wie XML-Dateien oder Exchange-gehostete Archive) zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-117">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="e9ef3-118">Wie sollen Bereiche, ethische Grenzen und Zugriffsmöglichkeiten kontrolliert werden?</span><span class="sxs-lookup"><span data-stu-id="e9ef3-118">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="e9ef3-119">Sie können **Kategorien** definieren, um diese Grenzen zu trennen, und auswählen, wer in Räumen sein darf, die in jeder dieser Kategorien erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-119">You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="e9ef3-120">Wie soll kontrolliert werden, wer Räume erstellen kann?</span><span class="sxs-lookup"><span data-stu-id="e9ef3-120">How do you want to control who can create rooms?</span></span> <span data-ttu-id="e9ef3-121">Sie können für Ihre Kategorien geeignete **Creators** konfigurieren, die Räume erstellen können.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-121">You can configure **Creators**, appropriate to your categories, who can create rooms.</span></span> <span data-ttu-id="e9ef3-122">Autoren können anderen Mitgliedern als Chatroom- **Manager** für die laufende Verwaltung der Räume (hinzufügen oder Entfernen zusätzlicher Mitglieder) entsprechend dem von der Kategorie konfigurierten Bereich für **AllowedMembers/DeniedMembers** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-122">Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="e9ef3-123">Wie möchten Sie Räume erstellen?</span><span class="sxs-lookup"><span data-stu-id="e9ef3-123">How do you want to create rooms?</span></span> <span data-ttu-id="e9ef3-124">Der Server für beständigen Chat bietet ein webbasiertes Feature für die Erstellung und Verwaltung von Räumen.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-124">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="e9ef3-125">Dies kann über den lync 2013-Client gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-125">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="e9ef3-126">Sie können eine benutzerdefinierte Lösung (mit dem Server Software Development Kit (SDK) für beständigen Chat) definieren, die Ihre geschäftlichen Anforderungen und Workflows implementiert, und den beständigen Chat Server so konfigurieren, dass Benutzer an Ihre benutzerdefinierte Lösung weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-126">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="e9ef3-127">Welche Arten von Add-Ins möchten Sie bereitstellen?</span><span class="sxs-lookup"><span data-stu-id="e9ef3-127">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="e9ef3-128">**Add-ins** verbessern die in-Room-Umgebung, indem Sie den Bereich "Erweiterbarkeit" im lync 2013-Client nutzen, um Kontext bereitzustellen, der für den Raum relevant ist.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-128">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="e9ef3-129">Sie können die allgemeinen Add-Ins auswählen, die Ihnen (beispielsweise im Hinblick auf Ihre Unternehmenswebsite oder Dokumente für die interne Zusammenarbeit) am hilfreichsten erscheinen.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-129">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="e9ef3-130">Chatroom-Manager können bei Bedarf eines der registrierten Add-Ins auswählen und ihren Räumen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-130">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="e9ef3-131">Welche Vorkehrungen wurden bezüglich der Anforderungen an hohe Verfügbarkeit sowie der Notfallwiederherstellung getroffen?</span><span class="sxs-lookup"><span data-stu-id="e9ef3-131">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="e9ef3-132">Der beständige Chat Server unterstützt die SQL Server-Spiegelung und das SQL Server-Clustering für höchste Verfügbarkeit und unterstützt bis zu 8 Server (4 Active und 4 Standby) in einem gedehnten Pool mit SQL Server-Protokollversand für Disaster Recovery.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-132">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="e9ef3-133">Bestehen gesetzliche Vorschriften?</span><span class="sxs-lookup"><span data-stu-id="e9ef3-133">Are there regulatory requirements?</span></span> <span data-ttu-id="e9ef3-134">Wenn sich Ihr Unternehmen in einem Land/einer Region befindet, in dem Daten im Land aufbewahrt werden müssen, müssen Sie möglicherweise mehrere beständige Chat Server Pools bereitstellen, die jeweils lokal in einer bestimmten geografischen Umgebung gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-134">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="e9ef3-135">Ein Raum, eine Kategorie oder ein Add-in umfasst keine Pools, sondern gehört nur zu einem beständigen Chat Server Pool.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-135">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="e9ef3-136">Sie können die Gruppe von Kategorien, Add-Ins und Räumen für jeden beständigen Chat Server Pool verwalten.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-136">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="e9ef3-137">Je nachdem, wie Sie Ihre Kategorien entwerfen, können Benutzer so konfiguriert werden, dass Sie den Zugriff auf Räume in einem oder mehreren Pools unter Verwendung des Bereichs "Kategorie AllowedMembers" oder des Mitgliedschafts Bereichs des Raums haben.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-137">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e9ef3-138">Wenn Sie über mehrere Server Pools für beständigen Chat verfügen, können Sie nicht mehr skalieren (Sie können immer noch nur 80.000-gleichzeitig verbundene Benutzer über alle Ihre beständigen Chat Server Pools verfügen).</span><span class="sxs-lookup"><span data-stu-id="e9ef3-138">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="e9ef3-139">Der Hauptgrund für die Unterstützung mehrerer beständiger Chat Server Pools ist die Unterstützung behördlicher Bedenken.</span><span class="sxs-lookup"><span data-stu-id="e9ef3-139">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    <span data-ttu-id="e9ef3-140"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e9ef3-140"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

