---
title: 'Lync Server 2013: Integration in Microsoft Exchange Server 2013'
description: 'Lync Server 2013: Integration in Microsoft Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54ab4a81e5455bc0a44677b1509876f39ff4d985
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49426879"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="e9227-103">Integration von Microsoft lync Server 2013 und Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9227-103">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="e9227-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="e9227-104">

<span> </span></span></span>

<span data-ttu-id="e9227-105">_**Letztes Änderungsdatum des Themas:** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="e9227-105">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="e9227-106">Exchange und lync Server verfügen über ein langes Integrations-und Kompatibilitäts Protokoll.</span><span class="sxs-lookup"><span data-stu-id="e9227-106">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="e9227-107">Diese Integration ist in der jeweiligen Clientanwendung besonders auffällig.</span><span class="sxs-lookup"><span data-stu-id="e9227-107">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="e9227-108">Lync-Anwesenheitsinformationen können beispielsweise in Microsoft Outlook gemeldet werden. Lync kann auch Outlook-Kalender verwenden, um diese Anwesenheitsinformationen automatisch zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e9227-108">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="e9227-109">(Beispielsweise kann lync ihren Status in "beschäftigt" ändern, wenn Ihr Kalender zeigt, dass eine Besprechung geplant ist.) Obwohl Sie Exchange nicht ausführen müssen, um lync Server auszuführen (oder umgekehrt), besteht kaum Zweifel daran, dass die Verwendung der beiden Produkte zusammen die Definition des Ausdrucks "besser zusammen" verkörpert.</span><span class="sxs-lookup"><span data-stu-id="e9227-109">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="e9227-110">Dies gilt insbesondere für die Veröffentlichung von Microsoft lync Server 2013 und Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9227-110">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="e9227-111">Neben Features wie Unified Messaging und Chat und Anwesenheit, die in Microsoft Exchange Server 2010 und Microsoft lync Server 2010 zu finden sind, enthalten die 2013-Versionen der Server Produkte eine Reihe neuer Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e9227-111">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="e9227-112">Zu diesen Funktionen gehören unter anderem:</span><span class="sxs-lookup"><span data-stu-id="e9227-112">These capabilities include such things as:</span></span>

  - <span data-ttu-id="e9227-113">**Integration der lync-Archivierung**</span><span class="sxs-lookup"><span data-stu-id="e9227-113">**Lync Archiving Integration**.</span></span> <span data-ttu-id="e9227-114">In lync Server 2013 können Administratoren weiterhin Instant Messaging-und Webkonferenz Protokolle in SQL Server archivieren (auf die gleiche Weise, wie diese Transkripte in lync Server 2010 archiviert wurden).</span><span class="sxs-lookup"><span data-stu-id="e9227-114">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="e9227-115">Sie können aber auch festlegen, dass die Protokolle in Exchange 2013 archiviert werden sollen, wobei die Protokolle in den einzelnen Benutzerpostfächern auf die gleiche Weise gespeichert werden, in der die Kommunikation in Exchange archiviert wird.</span><span class="sxs-lookup"><span data-stu-id="e9227-115">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="e9227-116">Das bedeutet ein einzelnes Repository für alle Ihre elektronischen Kommunikationen (sowohl von Exchange als auch von lync Server), wodurch es viel einfacher ist, diese archivierten Kommunikationen zu suchen und abzurufen, falls dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e9227-116">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="e9227-117">**Einheitlicher Kontaktspeicher**</span><span class="sxs-lookup"><span data-stu-id="e9227-117">**Unified Contact Store**.</span></span> <span data-ttu-id="e9227-118">In lync Server 2010 mussten Benutzer getrennte Kontaktlisten in Outlook und lync verwalten. um sicherzustellen, dass Sie über dieselben Kontakte in beiden Produkten verfügen, mussten Sie doppelte Kontaktlisten verwalten, eine für Outlook und eine für lync.</span><span class="sxs-lookup"><span data-stu-id="e9227-118">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="e9227-119">Bei lync Server 2013 können Benutzer Kontakte jedoch in Exchange 2013 und im Unified Contact Store gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e9227-119">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="e9227-120">Mit einem einzelnen Kontaktspeicher können Benutzer nur einen Satz Kontakte verwalten, wobei die gleichen Kontakte in lync 2013, Outlook 2013 und Outlook Web Access 2013 zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="e9227-120">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="e9227-121">**Lync-Besprechungsplanung von OWA**.</span><span class="sxs-lookup"><span data-stu-id="e9227-121">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="e9227-122">Mit lync Server 2013 und Exchange 2013-Integration können Benutzer lync-Besprechungen aus Outlook Web Access 2013 planen.</span><span class="sxs-lookup"><span data-stu-id="e9227-122">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="e9227-123">**Fotos mit höherer Auflösung**.</span><span class="sxs-lookup"><span data-stu-id="e9227-123">**High resolution photos**.</span></span> <span data-ttu-id="e9227-124">Lync 2010 konnte nur kleine Fotos Ihrer Kontakte anzeigen. Das liegt daran, dass diese Fotos in Active Directory gespeichert wurden und Active Directory eine 48 Pixelgröße von 48 Pixeln für gespeicherte Fotos vorschreibt.</span><span class="sxs-lookup"><span data-stu-id="e9227-124">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="e9227-125">Mit lync Server 2013 können Fotos jedoch in Microsoft Exchange gespeichert werden. Damit können Fotos mit hoher Auflösung so groß wie 648 Pixel von 648 Pixeln sein.</span><span class="sxs-lookup"><span data-stu-id="e9227-125">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="e9227-126">Wie Sie vielleicht erwarten, wurde lync 2013 aktualisiert, um die Anzeige dieser Fotos mit hoher Auflösung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e9227-126">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="e9227-127">Beachten Sie, dass diese neuen Features die Verwendung von lync Server 2013 und Exchange 2013 erfordern.</span><span class="sxs-lookup"><span data-stu-id="e9227-127">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="e9227-128">Darüber hinaus müssen Benutzer, die diese neuen Funktionen in vollem Umfang nutzen möchten, über Konten in lync Server 2013 und Exchange 2013 verfügen und die neuesten Versionen der Client Software verwenden (beispielsweise lync 2013).</span><span class="sxs-lookup"><span data-stu-id="e9227-128">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="e9227-129">Beispielsweise steht der Unified Contact Store nicht für Benutzer zur Verfügung, die sich in lync Server 2010 befanden. Ebenso können Fotos mit hoher Auflösung in lync 2010 nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e9227-129">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="e9227-130">Diese Dokumentation enthält Informationen zur Integration von lync Server 2013 und Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e9227-130">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="e9227-131">einschließlich Schritt-für-Schritt-Informationen zur Aktivierung neuer Funktionen wie Archivierungs Integration und einheitlicher Kontaktspeicher.</span><span class="sxs-lookup"><span data-stu-id="e9227-131">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="e9227-132">In dieser Dokumentation wird die Ersteinrichtung und Konfiguration dieser beiden Produkte erläutert.</span><span class="sxs-lookup"><span data-stu-id="e9227-132">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="e9227-133">Details zum Bereitstellen von lync Server 2013 finden Sie im lync Server 2013 Tech Center unter [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127) .</span><span class="sxs-lookup"><span data-stu-id="e9227-133">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="e9227-134">Details zum Bereitstellen von Exchange 2013 finden Sie im Exchange 2013 Tech Center unter [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528) .</span><span class="sxs-lookup"><span data-stu-id="e9227-134">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9227-135">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e9227-135">In This Section</span></span>

[<span data-ttu-id="e9227-136">Voraussetzungen für die Integration von Microsoft lync Server 2013 und Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9227-136">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="e9227-137">Konfigurieren von Partneranwendungen in Microsoft lync Server 2013 und Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9227-137">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="e9227-138">Konfigurieren von Microsoft lync Server 2013 für die Verwendung von Microsoft Exchange Server 2013-Archivierung</span><span class="sxs-lookup"><span data-stu-id="e9227-138">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="e9227-139">Konfigurieren von Microsoft SharePoint Server 2013 zum Suchen nach archivierten Microsoft lync Server 2013-Daten</span><span class="sxs-lookup"><span data-stu-id="e9227-139">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="e9227-140">Konfigurieren von Microsoft lync Server 2013 für die Verwendung des einheitlichen Kontaktspeichers</span><span class="sxs-lookup"><span data-stu-id="e9227-140">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="e9227-141">Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9227-141">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="e9227-142">Konfigurieren von Microsoft Exchange Server 2013 Unified Messaging für Microsoft lync Server 2013-Voicemail</span><span class="sxs-lookup"><span data-stu-id="e9227-142">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="e9227-143">Integrieren von Microsoft lync Server 2013 und Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="e9227-143">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

<span data-ttu-id="e9227-144"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="e9227-144"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

