---
title: 'Lync Server 2013: Features von integriertem Unified Messaging'
description: 'Lync Server 2013: Features von Integrated Unified Messaging.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e2caa75504c0468293ced8f20946500fad7cf54
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428202"
---
# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="24bc5-103">Features von integriertem Unified Messaging und Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24bc5-103">Features of integrated Unified Messaging and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="24bc5-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="24bc5-104">

<span> </span></span></span>

<span data-ttu-id="24bc5-105">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="24bc5-105">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="24bc5-106">Lync Server 2013, Enterprise-VoIP verwendet die Exchange Unified Messaging (um)-Infrastruktur für die Bereitstellung von Anrufannahme, Anrufbenachrichtigung, Sprachzugriff (einschließlich Voicemail) und automatischen Telefonzentralen.</span><span class="sxs-lookup"><span data-stu-id="24bc5-106">Lync Server 2013, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

<div>

## <a name="call-answering"></a><span data-ttu-id="24bc5-107">Anrufbeantwortung</span><span class="sxs-lookup"><span data-stu-id="24bc5-107">Call Answering</span></span>

<span data-ttu-id="24bc5-108">Bei der Anrufbeantwortung werden Sprachnachrichten für Benutzer entgegengenommen, die gerade nicht an ihrem Platz sind oder sich bereits in einem Gespräch befinden.</span><span class="sxs-lookup"><span data-stu-id="24bc5-108">Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="24bc5-109">Hierzu gehören die Wiedergabe einer persönlichen Begrüßung, die Aufzeichnung einer Nachricht sowie die Übermittlung der Nachricht, um sie in die Warteschlange für eine Übermittlung an das auf dem Exchange-Postfachserver gespeicherte Postfach des Benutzers einzureihen.</span><span class="sxs-lookup"><span data-stu-id="24bc5-109">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

<span data-ttu-id="24bc5-p102">Wenn ein Anrufer eine Nachricht hinterlässt, wird diese an den Posteingang des Benutzers übermittelt. Wenn ein Anrufer keine Nachricht hinterlässt, wird eine Benachrichtigung über einen entgangenen Anruf im Posteingang des Benutzers gespeichert. Benutzer können folgendermaßen auf ihren Posteingang zugreifen: über einen Microsoft Office Outlook-Client für Messaging und Zusammenarbeit, über Outlook Web Access, die Exchange ActiveSync-Technologie oder Outlook Voice Access. Betreff und Priorität von Anrufen können auf ähnliche Weise angezeigt werden wie für E-Mails.</span><span class="sxs-lookup"><span data-stu-id="24bc5-p102">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

</div>

<div>

## <a name="outlook-voice-access"></a><span data-ttu-id="24bc5-114">Outlook Voice Access</span><span class="sxs-lookup"><span data-stu-id="24bc5-114">Outlook Voice Access</span></span>

<span data-ttu-id="24bc5-115">Outlook Voice Access ermöglicht einem Enterprise-VoIP-Benutzer den Zugriff auf nicht nur Voicemail, sondern auch den Exchange-Posteingang, einschließlich e-Mail, Kalender und Kontakte über eine Telefonschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="24bc5-115">Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="24bc5-116">Die Teilnehmerzugriffsnummer wird von einem Exchange um-Administrator zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="24bc5-116">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

</div>

<div>

## <a name="auto-attendant"></a><span data-ttu-id="24bc5-117">Automatische Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="24bc5-117">Auto Attendant</span></span>

<span data-ttu-id="24bc5-118">Bei der automatischen Telefonzentrale handelt es sich um ein Exchange um-Feature, das verwendet werden kann, um eine Telefonnummer zu konfigurieren, die externe Benutzer anrufen können, um Unternehmensvertreter zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="24bc5-118">Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="24bc5-119">Diese Funktion stellt ferner verschiedene Ansagen bereit, die einem externen Anrufer die Navigation in einem Menüsystem ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="24bc5-119">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="24bc5-120">Die Liste der verfügbaren Optionen wird vom Exchange um-Administrator auf dem Exchange um-Server konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="24bc5-120">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

</div>

<div>

## <a name="fax-services"></a><span data-ttu-id="24bc5-121">Fax-Dienste</span><span class="sxs-lookup"><span data-stu-id="24bc5-121">Fax Services</span></span>

<span data-ttu-id="24bc5-122">Exchange um umfasst Fax-Features, mit denen Benutzer eingehende Faxe in Ihren Exchange-Postfächern empfangen können.</span><span class="sxs-lookup"><span data-stu-id="24bc5-122">Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="24bc5-123">Ausführliche Informationen finden Sie unter "Unified Messaging" in der Microsoft Exchange Server-Dokumentation unter [https://go.microsoft.com/fwlink/p/?linkId=135652](https://go.microsoft.com/fwlink/p/?linkid=135652) .</span><span class="sxs-lookup"><span data-stu-id="24bc5-123">For details, see "Unified Messaging" in the Microsoft Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?linkId=135652](https://go.microsoft.com/fwlink/p/?linkid=135652).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24bc5-124">Die vom Exchange um-Server bereitgestellten Faxdienst sind in lync Server-Bereitstellungen, die in Microsoft Exchange Server 2010, Exchange 2010 mit dem neuesten Service Pack oder Exchange 2013 integriert sind, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="24bc5-124">Fax services provided by the Exchange UM server are not available in Lync Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span>



<span data-ttu-id="24bc5-125"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="24bc5-125"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

