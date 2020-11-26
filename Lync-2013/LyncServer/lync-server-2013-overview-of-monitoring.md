---
title: 'Lync Server 2013: Übersicht über die Überwachung'
description: 'Lync Server 2013: Übersicht über die Überwachung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64f27d6aff71442c6193c220154af231481399ac
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49445106"
---
# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="21f21-103">Übersicht über die Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21f21-103">Overview of monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="21f21-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="21f21-104">

<span> </span></span></span>

<span data-ttu-id="21f21-105">_**Letztes Änderungsdatum des Themas:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="21f21-105">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="21f21-106">In Microsoft lync Server 2013 wird die Überwachung verwendet, um Nutzungsinformationen und QoE-Daten (Quality of Experience) zu den Kommunikationssitzungen zu sammeln, an denen Ihre Benutzer beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="21f21-106">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="21f21-107">Bei einer Sitzung handelt es sich um einen generischen Ausdruck, der die Verbindung eines Benutzers mit einer der folgenden Bereiche abdeckt:</span><span class="sxs-lookup"><span data-stu-id="21f21-107">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="21f21-108">Konferenz</span><span class="sxs-lookup"><span data-stu-id="21f21-108">Conference</span></span>

  - <span data-ttu-id="21f21-109">Konferenz Modalitäten (wie Audio/Video oder Anwendungsfreigabe)</span><span class="sxs-lookup"><span data-stu-id="21f21-109">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="21f21-110">Andere Benutzer über eine Peer-zu-Peer-Unterhaltung wie Sofortnachrichten oder Audioanruf</span><span class="sxs-lookup"><span data-stu-id="21f21-110">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="21f21-111">Lync Server 2013 verfolgt Informationen zu den einzelnen Sitzungen: Wer hat wen angerufen? welche Endpunkte in der Sitzung verwendet wurden; wie lange dauerte die Sitzung? Was war die wahrgenommene Qualität der Sitzung; Und so weiter.</span><span class="sxs-lookup"><span data-stu-id="21f21-111">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="21f21-112">Lync Server zeichnet aber den eigentlichen Anruf selbst nicht auf und speichert ihn.</span><span class="sxs-lookup"><span data-stu-id="21f21-112">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="21f21-113">Dazu gehören auch Instant Messaging-Sitzungen: Obwohl lync Server Informationen zu Instant Messaging-Sitzungen aufzeichnet, wird keine Aufzeichnung der einzelnen Sofortnachrichten verwaltet, die während der Sitzung gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="21f21-113">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="21f21-114">Die von lync Server gesammelten Anruf Detailinformationen können für eine beliebige Anzahl von Verwendungen eingesetzt werden, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="21f21-114">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="21f21-115">**Return on Investment (ROI)**.</span><span class="sxs-lookup"><span data-stu-id="21f21-115">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="21f21-116">Administratoren können die von Monitoring Server gesammelten Nutzungsdaten mit ähnlichen Daten vergleichen, die für Ihr vorheriges Telefoniesystem erfasst wurden, um Kosteneinsparungen anzuzeigen und die Bereitstellung von lync Server zu rechtfertigen.</span><span class="sxs-lookup"><span data-stu-id="21f21-116">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="21f21-117">**Verwalten des Gerätebestands**: Informationen zur Inventarverwaltung unterstützen Administratoren bei der Identifikation alter Geräte, die ersetzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="21f21-117">**Device Inventory Management**.</span></span> <span data-ttu-id="21f21-118">Informationen zur Vermögensverwaltung unterstützen Administratoren bei der Identifizierung veralteter Geräte, die noch verwendet werden müssen, sowie bei der Ermittlung teurer Geräte, die anscheinend überhaupt nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="21f21-118">Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="21f21-119">Helpdesk.</span><span class="sxs-lookup"><span data-stu-id="21f21-119">Help Desk.</span></span> <span data-ttu-id="21f21-120">Die Problembehandlung von Daten ermöglicht Supportingenieuren, zu ermitteln, warum der Anruf eines Benutzers fehlgeschlagen ist, und dies ohne Server-oder clientseitige Protokolle zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="21f21-120">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="21f21-121">Diese Informationen können von Supportmitarbeitern, die nicht über fundierte technische Kenntnisse in Microsoft lync 2013 und lync Server 2013 verfügen, problemlos abgerufen und verstanden werden.</span><span class="sxs-lookup"><span data-stu-id="21f21-121">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="21f21-p106">**Systemproblembehandlung**: Ermöglicht Administratoren das Erkennen grundlegender Probleme, die u. U. verhindern, dass Endbenutzer einfache Aufgaben wie das Beitreten zu einer Konferenz, das Durchführen eines Anrufs oder das Senden einer Chatnachricht ausführen können.</span><span class="sxs-lookup"><span data-stu-id="21f21-p106">**System Troubleshooting**. Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="21f21-124">Zusätzlich zu diesen grundlegenden Anrufinformationen bietet der Monitoring Server auch einen Mechanismus, der es SIP-Endpunkten (wie lync 2013) ermöglicht, Informationen zur Problembehandlung bereitzustellen, auf die der Server sonst nicht zugreifen kann:</span><span class="sxs-lookup"><span data-stu-id="21f21-124">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="21f21-125">**Medienmetriken mit Auswirkungen auf die Qualität**: Die Metriken beziehen sich auf die eigentliche Übertragung des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="21f21-125">**Media Metrics that Impact Quality**.</span></span> <span data-ttu-id="21f21-126">Diese Metriken befassen sich mit der eigentlichen Übertragung des Anrufs selbst; Das bedeutet, dass Sie eine Art Reiseprotokoll als Anruf Fahrten über das Netzwerk bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="21f21-126">These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network.</span></span> <span data-ttu-id="21f21-127">Diese Metriken (wie beispielsweise Paketverlust, Jitter und Roundtrip-Zeiten) geben Informationen dazu, was mit dem Anruf geschehen ist, wenn der Endpunkt den Endpunkt der anderen Person erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="21f21-127">These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="21f21-128">**Probleme, die dem Endbenutzer gemeldet** wurden.</span><span class="sxs-lookup"><span data-stu-id="21f21-128">**Issues Reported to the End User**.</span></span> <span data-ttu-id="21f21-129">Zu diesen Metriken gehören Benachrichtigungen über schlechte Qualität, die lync 2013 Endbenutzern in Fällen vorstellt, in denen Sie zu weit von einem Mikrofon entfernt sind, zu leise sprechen, eine schlechte Netzwerkverbindung aufweisen oder eine schlechte Qualität aufweisen, weil ein anderes Programm auf dem Computer die verfügbaren Ressourcen beansprucht.</span><span class="sxs-lookup"><span data-stu-id="21f21-129">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="21f21-p109">**Umgebungsinformationen**: Diese Metriken erfassen detaillierte Faktoren der Anrufqualität wie den Typ des verwendeten Mikrofons und Lautsprechers, Angaben darüber, ob eine VPN-Verbindung verwendet wurde, und darüber, ob eine WLAN-Verbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="21f21-p109">**Environment Information**. These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="21f21-132">Am Ende jedes Anrufs übertragen SIP-kompatible Endpunkte diese Informationen automatisch an den Front-End-Server, der den Anruf erleichtert hat.</span><span class="sxs-lookup"><span data-stu-id="21f21-132">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call.</span></span> <span data-ttu-id="21f21-133">Sie müssen nichts Unternehmen, um Endpunkte zur Übertragung dieser Informationen zu erhalten. Dieses Verhalten ist in das SIP-Protokoll integriert.</span><span class="sxs-lookup"><span data-stu-id="21f21-133">You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol.</span></span> <span data-ttu-id="21f21-134">Wenn Sie diese Informationen jedoch sammeln und speichern möchten, müssen Sie die Überwachung installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="21f21-134">However, if you want to collect and store that information, then you need to install and enable monitoring.</span></span> <span data-ttu-id="21f21-135">Wenn Sie die Überwachung installieren und aktivieren, werden die Anrufinformationen von Agents gesammelt, die auf dem Front-End-Server ausgeführt werden und an ein paar von SQL Server-Datenbanken weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="21f21-135">If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="21f21-136">Beachten Sie, dass der Vorgang zum Installieren und Konfigurieren der Überwachung in lync Server 2013 vereinfacht wurde.</span><span class="sxs-lookup"><span data-stu-id="21f21-136">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="21f21-137">In früheren Versionen der Software erforderte die Überwachung eine separate Überwachungsserver Rolle, was in der Regel einen separaten Computer für die Verwendung als Überwachungsserver bedeutete.</span><span class="sxs-lookup"><span data-stu-id="21f21-137">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="21f21-138">In lync Server 2013 wurde die Monitoring Server-Rolle jedoch eliminiert.</span><span class="sxs-lookup"><span data-stu-id="21f21-138">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="21f21-139">Stattdessen wurde der Überwachungsdienst (in Form von "Unified Data Collection Agents") in allen Front-End-Servern zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="21f21-139">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="21f21-140">Dies hat mindestens zwei Hauptvorteile.</span><span class="sxs-lookup"><span data-stu-id="21f21-140">This has at least two major benefits.</span></span> <span data-ttu-id="21f21-141">Überprüfung des Überwachungsdiensts:</span><span class="sxs-lookup"><span data-stu-id="21f21-141">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="21f21-142">Verringert die Anzahl der Serverrollen, die bei der Implementierung von lync Server 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="21f21-142">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="21f21-143">Durch die Dekrementierung der Monitoring Server-Rolle können Sie auch die Kosten reduzieren, indem Sie die Notwendigkeit, dedizierte Server für die Überwachung zu verwalten, eliminieren.</span><span class="sxs-lookup"><span data-stu-id="21f21-143">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="21f21-144">Verringert die Komplexität der Einrichtung und Verwaltung von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21f21-144">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="21f21-145">Durch abstimmen der Überwachungsdienste auf jedem Front-End-Server müssen Sie nicht mehr die Monitoring Server-Rolle installieren, konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="21f21-145">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="21f21-146">Weitere Informationen finden Sie im Thema [Bereitstellen der Überwachung in lync Server 2013](lync-server-2013-deploying-monitoring.md) im Bereitstellungshandbuch für lync Server 2013 2013.</span><span class="sxs-lookup"><span data-stu-id="21f21-146">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

<span data-ttu-id="21f21-147"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="21f21-147"></div>

<span> </span>

</div>

</div>

</span></span></div>

