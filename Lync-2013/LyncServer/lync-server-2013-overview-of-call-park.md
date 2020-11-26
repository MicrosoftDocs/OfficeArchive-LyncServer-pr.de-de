---
title: 'Lync Server 2013: Übersicht über den Parken von Anrufen'
description: 'Lync Server 2013: Übersicht über den Parken von anrufen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 373a758dcc64dc390255239c0d1fb628308080a7
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49445141"
---
# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="dda1f-103">Übersicht über den Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dda1f-103">Overview of Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="dda1f-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="dda1f-104">

<span> </span></span></span>

<span data-ttu-id="dda1f-105">_**Letztes Änderungsdatum des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="dda1f-105">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="dda1f-106">Mit der lync Server 2013-Anwendung Parken können Enterprise-VoIP-Benutzer eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="dda1f-106">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="dda1f-107">Halten eines Anrufs und anschließendes Entgegennehmen des Anrufs am selben oder an einem anderen Telefon.</span><span class="sxs-lookup"><span data-stu-id="dda1f-107">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="dda1f-108">Halten eines Anrufs, um ihn an eine Abteilung oder einen allgemeinen Bereich zu übergeben (z. B. die Vertriebsabteilung oder ein Lagerort mit einem Telefon im öffentlichen Bereich).</span><span class="sxs-lookup"><span data-stu-id="dda1f-108">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="dda1f-109">Halten eines Anrufs, um weitere Anrufe an einem Telefon entgegennehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="dda1f-109">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="dda1f-110">Wenn ein Benutzer einen Anruf parkt, übergibt lync Server den Anruf an eine temporäre Nummer, die so genannte *Orbit*, in der der Anruf gehalten wird, bis er abgerufen wird, oder es wird ein Timeout festgestellt. Lync Server sendet die Umlaufbahn an den Benutzer, der den Anruf abgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="dda1f-110">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="dda1f-111">Zum Wiederaufnehmen des geparkten Anrufs kann der Benutzer die Orbitnummer wählen oder auf den Orbitlink oder die Schaltfläche im Fenster „Unterhaltung“ klicken.</span><span class="sxs-lookup"><span data-stu-id="dda1f-111">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="dda1f-p102">Der Benutzer, der einen Anruf geparkt hat, kann einen anderen Benutzer mithilfe eines externen Mechanismus (beispielsweise über eine Sofortnachricht oder ein Paging-System) über die Orbitnummer informieren, damit dieser Benutzer den Anruf entgegennehmen kann. Der Benutzer, der den Anruf geparkt hat, kann das Fenster „Unterhaltung“ geöffnet lassen, um eine Benachrichtigung zu erhalten, sobald der Anruf entgegengenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="dda1f-p102">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="dda1f-114">Da Umlaufbahn Bereiche global eindeutig sind, ist es möglich, Anrufe von jeder lync Server-Website oder einem PBX-Telefon abzurufen, wenn Routing entsprechend konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="dda1f-114">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="dda1f-115">Wenn der Anruf innerhalb einer konfigurierbaren Zeitdauer nicht wiederaufgenommen wird, wird er erneut an den Benutzer zurückgegeben, der den Anruf geparkt hat.</span><span class="sxs-lookup"><span data-stu-id="dda1f-115">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="dda1f-116">Wenn dieser Benutzer den Anruf nicht beantwortet, wird er an ein Fallbackziel übergeben (z. B. einen Agent), sofern dies konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="dda1f-116">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="dda1f-117">Sie können konfigurieren, wie oft das Telefon erneut läutet (ein- bis zehnmal), bevor der Anruf weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="dda1f-117">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="dda1f-118">Wenn ein weitergeleiteter Anruf nicht entgegengenommen wird, wird die Verbindung unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="dda1f-118">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="dda1f-119">Wenn der Anruf entgegengenommen oder die Verbindung unterbrochen wird, wird der Orbit erneut freigegeben.</span><span class="sxs-lookup"><span data-stu-id="dda1f-119">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="dda1f-120">Wenn Sie die Funktion zum Parken von Anrufen bereitstellen, müssen Sie Durchwahlnummernbereiche zum Parken von Anrufen reservieren.</span><span class="sxs-lookup"><span data-stu-id="dda1f-120">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="dda1f-121">Bei diesen Durchwahlnummern muss es sich um virtuelle Durchwahlnummern handeln, also solche, denen kein Benutzer oder Telefon zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="dda1f-121">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="dda1f-122">Anschließend konfigurieren Sie die Orbittabelle für das Parken von Anrufen mit den Durchwahlnummernbereichen und geben an, welcher Anwendungsdienst die Anwendung zum Parken von Anrufen hostet, die die einzelnen Bereiche verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="dda1f-122">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="dda1f-123">Jeder Front-End-Pool verfügt über eine Anruf Park Tabelle auf dem entsprechenden Back-End-Server, der zum Verwalten von Anrufen dient, die auf dem Pool abgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="dda1f-123">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="dda1f-124">Die Liste der Umlaufbahn Bereiche wird im zentralen Verwaltungsspeicher gespeichert und zum Weiterleiten von Umlaufbahnen an den Ziel Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="dda1f-124">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="dda1f-125">Jeder lync-Server Pool, in dem die Anwendung für das Parken von Anrufen bereitgestellt und konfiguriert ist, kann einen oder mehrere Umlaufbahn Bereiche aufweisen.</span><span class="sxs-lookup"><span data-stu-id="dda1f-125">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="dda1f-126">Umlaufbahn Bereiche müssen in der lync Server-Bereitstellung global eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="dda1f-126">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="dda1f-p105">Sie können darüber hinaus weitere Einstellungen für das Parken von Anrufen konfigurieren, wie z. B., an welches Ziel Anrufe bei einem Timeout umgeleitet werden und ob für den Anrufer Musik wiedergegeben wird, während der Anruf geparkt ist. Außerdem können Sie die Musikdatei angeben, die beim Parken des Anrufs wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="dda1f-p105">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dda1f-129">Angepasste Musik-in-situ-Dateien für den Parken von Anrufen werden nicht im Rahmen des lync Server 2013-Wiederherstellungsprozesses gesichert und gehen verloren, wenn die Dateien, die in den Pool hochgeladen wurden, beschädigt, beschädigt oder gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="dda1f-129">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="dda1f-130">Bewahren Sie stets eine separate Sicherungskopie der für geparkte Anrufe hochgeladenen angepassten Musikdateien auf.</span><span class="sxs-lookup"><span data-stu-id="dda1f-130">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="dda1f-131">Die Anwendung zum Parken von Anrufen ist eine Enterprise-VoIP-Komponente.</span><span class="sxs-lookup"><span data-stu-id="dda1f-131">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="dda1f-132">Wenn Sie Enterprise-VoIP bereitstellen, wird die Anwendung für den Anruf Park automatisch installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="dda1f-132">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="dda1f-133">Bevor Sie den Anruf Park verwenden können, muss der Enterprise Voice-Administrator ihn aber über die VoIP-Richtlinie konfigurieren und für die Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="dda1f-133">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

<span data-ttu-id="dda1f-134"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="dda1f-134"></div>

<span> </span>

</div>

</div>

</span></span></div>

