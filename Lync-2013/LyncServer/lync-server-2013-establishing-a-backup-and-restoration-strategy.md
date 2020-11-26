---
title: 'Lync Server 2013: Einrichten einer Sicherungs-und Wiederherstellungsstrategie'
description: 'Lync Server 2013: Einrichten einer Sicherungs-und Wiederherstellungsstrategie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fdefed873d1fd69d82f8ecebceeb92f06f65f7
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428468"
---
# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="b2420-103">Einrichten einer Sicherungs-und Wiederherstellungsstrategie für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2420-103">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="b2420-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="b2420-104">

<span> </span></span></span>

<span data-ttu-id="b2420-105">_**Letztes Änderungsdatum des Themas:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="b2420-105">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="b2420-106">Bevor Sie einen Sicherungs-und Wiederherstellungsplan für lync Server entwickeln können, müssen Sie eine Strategie entwickeln, die den Zielen Ihrer Organisation entspricht.</span><span class="sxs-lookup"><span data-stu-id="b2420-106">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="b2420-107">Zur Entwicklung einer effektiven Sicherungs-und Wiederherstellungsstrategie müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="b2420-107">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="b2420-108">Unternehmensprioritäten festlegen</span><span class="sxs-lookup"><span data-stu-id="b2420-108">Establish business priorities.</span></span>

  - <span data-ttu-id="b2420-109">Ermitteln von Sicherungs-und Wiederherstellungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="b2420-109">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="b2420-110">Einrichten von Unternehmensprioritäten</span><span class="sxs-lookup"><span data-stu-id="b2420-110">Establishing Business Priorities</span></span>

<span data-ttu-id="b2420-111">Bewerten Sie die geschäftlichen Prioritäten Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="b2420-111">Evaluate the business priorities of your organization.</span></span> <span data-ttu-id="b2420-112">In der Regel sind die primären Unternehmensprioritäten, die sich auf Ihre Sicherungs-und Wiederherstellungsstrategie auswirken, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b2420-112">Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="b2420-113">Business Continuity-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b2420-113">Business continuity requirements</span></span>

  - <span data-ttu-id="b2420-114">Datenvollständigkeit</span><span class="sxs-lookup"><span data-stu-id="b2420-114">Data completeness</span></span>

  - <span data-ttu-id="b2420-115">Daten kritisch</span><span class="sxs-lookup"><span data-stu-id="b2420-115">Data criticality</span></span>

  - <span data-ttu-id="b2420-116">Portabilitäts Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b2420-116">Portability requirements</span></span>

  - <span data-ttu-id="b2420-117">Kosteneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="b2420-117">Cost constraints</span></span>

<span data-ttu-id="b2420-118">Geschäftliche Anforderungen wie diese helfen bei der Bestimmung der Service Level Agreements (SLAs), die Sie mit ihren Kunden entwickeln.</span><span class="sxs-lookup"><span data-stu-id="b2420-118">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="b2420-119">Service Level Agreements beeinflussen Ihre Sicherungs-und Wiederherstellungsstrategie erheblich.</span><span class="sxs-lookup"><span data-stu-id="b2420-119">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="b2420-120">Identifizieren von Sicherungs-und Wiederherstellungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="b2420-120">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="b2420-121">Ihre Geschäftsprioritäten und Service Level Agreements dienen dazu, die Anforderungen Ihrer Organisationen für das Sichern und Wiederherstellen von lync Server zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="b2420-121">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="b2420-122">Ermitteln und dokumentieren Sie Ihre Anforderungen für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b2420-122">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="b2420-123">**Häufigkeit von Sicherungen**   Ausführliche Informationen zu bewährten Methoden für die Sicherungshäufigkeit finden Sie unter [bewährte Methoden für die Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span><span class="sxs-lookup"><span data-stu-id="b2420-123">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="b2420-124">**Sicherungs-und Wiederherstellungstools**   Fügen Sie die Personen hinzu, die die Tools verwenden sollen, und auf welchen Computern.</span><span class="sxs-lookup"><span data-stu-id="b2420-124">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="b2420-125">Details zu den in diesem Thema und den erforderlichen Berechtigungen besprochenen Tools finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Tools und Berechtigungen](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b2420-125">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="b2420-126">**Sicherungsspeicherort**   Ermitteln Sie, ob die Sicherungen lokal oder Remote aufbewahrt werden, wobei Sicherheit und Barrierefreiheit berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="b2420-126">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="b2420-127">Geben Sie das für die Sicherungen zu verwendende Medium an.</span><span class="sxs-lookup"><span data-stu-id="b2420-127">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="b2420-128">**Hardware-und Softwareanforderungen**   Ermitteln und dokumentieren Sie Ihre spezifischen Hardware-und Softwareanforderungen, einschließlich Hardware für den Sicherungsspeicher und die Wiederherstellung bestimmter Komponenten sowie alle Software-und Netzwerkverbindungen, die für die Unterstützung von Backup und Wiederherstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b2420-128">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="b2420-129">Berücksichtigen Sie bei der Entwicklung Ihrer Hardware-und Softwareanforderungen die verschiedenen Wiederherstellungsszenarien, die Folgen.</span><span class="sxs-lookup"><span data-stu-id="b2420-129">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="b2420-130">**Wiederherstellungsszenarien**   Nachfolgend finden Sie die Wiederherstellungsprozesse für die folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="b2420-130">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="b2420-131">Ein lync Server-Pool schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="b2420-131">A Lync Server pool fails.</span></span> <span data-ttu-id="b2420-132">Für dieses Szenario muss jeder Server im Pool neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b2420-132">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="b2420-133">Ein Standard Edition-Server schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="b2420-133">A Standard Edition server fails.</span></span> <span data-ttu-id="b2420-134">Für dieses Szenario muss der Server auf einem neuen oder sauberen Computer neu erstellt und Datenbanken wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b2420-134">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="b2420-135">Verlust des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="b2420-135">Loss of the Central Management store.</span></span> <span data-ttu-id="b2420-136">Dieses Szenario erfordert mindestens das Wiederherstellen und Veröffentlichen des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="b2420-136">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="b2420-137">Verlust eines Back-End-Servers, wenn der zentrale Verwaltungsspeicher weiterhin normal funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b2420-137">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="b2420-138">Für dieses Szenario muss der Server auf einem neuen oder sauberen Computer neu erstellt und Datenbanken wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b2420-138">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="b2420-139">Ein Server, der Mitglied eines lync Server-Pools ist, schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="b2420-139">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="b2420-140">Für dieses Szenario muss der Server auf einem neuen oder sauberen Computer neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b2420-140">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="b2420-141">Ein Dateispeicher schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="b2420-141">A File Store fails.</span></span> <span data-ttu-id="b2420-142">Für dieses Szenario muss der Dateiserver oder der Dateicluster wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b2420-142">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="b2420-143">Eine Datenbank zum Archivieren, überwachen oder beständigen Chat schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="b2420-143">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="b2420-144">Für dieses Szenario müssen die Datenbanken neu erstellt werden, und wenn die Daten für Ihre Organisation wichtig sind, müssen Sie die Daten wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="b2420-144">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="b2420-145">Archivierungs-, Überwachungs-und beständige Chat Daten sind nicht erforderlich, um lync Server wieder in Betrieb zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="b2420-145">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

<span data-ttu-id="b2420-146"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="b2420-146"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

