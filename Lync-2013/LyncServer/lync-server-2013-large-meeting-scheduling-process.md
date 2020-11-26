---
title: 'Lync Server 2013: Planungsprozess für große Besprechungen'
description: 'Lync Server 2013: Planungsprozess für große Besprechungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96d383b6da96fb7d36e031485feac2ff927df347
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49426707"
---
# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="f00a8-103">Planungsprozess für große Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f00a8-103">Large-meeting scheduling process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="f00a8-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="f00a8-104">

<span> </span></span></span>

<span data-ttu-id="f00a8-105">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f00a8-105">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f00a8-106">Da im dedizierten, umfangreichen Besprechungs Pool nur jeweils eine große Besprechung unterstützt wird, empfehlen wir die Implementierung eines umfangreichen Besprechungs Planungsprozesses, um große Besprechungs Konflikte zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f00a8-106">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="f00a8-107">Der Zweck dieses Planungsprozesses besteht darin, das Einrichten großer Besprechungen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="f00a8-107">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="f00a8-108">Diese Funktion wird nicht direkt von lync Server-oder lync Server-Clients bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f00a8-108">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="f00a8-109">Eine Möglichkeit zur Implementierung eines solchen Prozesses besteht darin, das Ticketing-System Ihres Unternehmens zu verwenden, sofern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f00a8-109">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="f00a8-110">Für Organisatoren von umfangreichen Besprechungen müssen Sie die folgenden Schritte ausführen, um eine große Besprechung zu planen:</span><span class="sxs-lookup"><span data-stu-id="f00a8-110">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="f00a8-p102">Der Besprechungsorganisator oder die delegierte Person bestimmt den Zeitpunkt, die Dauer und den Umfang einer anstehenden Besprechung sowie die Liste der Referenten. Falls der erwartete Besprechungsumfang 250 Benutzer überschreitet, oder um die optimale Funktionalität für eine Besprechung mit weniger als 250 Benutzern sicherzustellen, reicht der Organisator oder die delegierte Person einen Antrag für eine große Besprechung ein.</span><span class="sxs-lookup"><span data-stu-id="f00a8-p102">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="f00a8-p103">Die Planungsmitarbeiter überprüfen, ob der angeforderte Termin verfügbar ist. Da jeweils immer nur eine einzige große Besprechung im Pool unterstützt wird, müssen die Planungsmitarbeiter anhand des Kalenders für große Besprechungen feststellen, ob für den angeforderten Termin bereits eine andere Besprechung geplant ist. Falls der angeforderte Termin verfügbar ist, wird die Besprechungsanfrage genehmigt.</span><span class="sxs-lookup"><span data-stu-id="f00a8-p103">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="f00a8-116">Wenn die Anforderung genehmigt wurde, verwendet das Planungs Personal (mithilfe von Anmeldeinformationen im dedizierten Pool) das Online Besprechungs-Add-in für lync 2013 mit Outlook, um eine Besprechung im dedizierten groß Besprechungs Pool einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f00a8-116">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="f00a8-117">Die URL für die Teilnahme an der Besprechung wird dem Antragsteller im Rahmen des Genehmigungshinweises bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f00a8-117">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="f00a8-p105">Der Besprechungsorganisator oder die delegierte Person plant mithilfe von Outlook die anstehende Besprechung und fügt die URL für die Teilnahme an der Besprechung der Besprechungseinladung hinzu. Der Besprechungsorganisator oder die delegierte Person legt dann die Benutzer fest, die eingeladen werden sollen, und versendet die Besprechungseinladung.</span><span class="sxs-lookup"><span data-stu-id="f00a8-p105">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation. The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="f00a8-120">Die folgende Abbildung zeigt einen typischen Anforderungs-und Genehmigungsworkflow für das Planen großer Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="f00a8-120">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="f00a8-121">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="f00a8-121">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

<span data-ttu-id="f00a8-122"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="f00a8-122"></div>

<span> </span>

</div>

</div>

</span></span></div>

