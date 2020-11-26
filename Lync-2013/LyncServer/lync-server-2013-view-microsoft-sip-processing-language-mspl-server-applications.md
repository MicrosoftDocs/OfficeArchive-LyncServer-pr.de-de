---
title: Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language)
description: Anzeigen von Microsoft SIP Processing Language (MSPL)-Serveranwendungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d844acf542546a668c4fc086a07cd6a7bb4a8f5a
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49446290"
---
# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="7e3bb-103">Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e3bb-103">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="7e3bb-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="7e3bb-104">

<span> </span></span></span>

<span data-ttu-id="7e3bb-105">_**Letztes Änderungsdatum des Themas:** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="7e3bb-105">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="7e3bb-106">Eine Microsoft SIP Processing Language (MSPL)-Serveranwendung ist eine skriptbasierte Anwendung, die eine Skriptsprache anstelle der Microsoft lync 2010-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-106">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="7e3bb-107">MSPL bietet eine genauere Steuerung des Filter-und Proxy Verhaltens sowie eine Möglichkeit zum Verteilen bestimmter Nachrichten an transaktionsbasierte SIP-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-107">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="7e3bb-108">MSPL wird speziell zum Filtern und Weiterleiten von SIP-Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-108">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="7e3bb-109">MSPL-Anwendungen werden im gleichen Prozess wie das userservices-Modul ausgeführt, während ein Programm, das auf der lync 2010-API basiert, in einem separaten Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-109">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="7e3bb-110">Sie können die Seite **Serveranwendung** in der Gruppe **Topologie** der lync Server-Systemsteuerung verwenden, um eine Liste der MSPL-Server Anwendungen anzuzeigen, die auf Front-End-Servern in ihrer lync Server 2013-Umgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-110">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="7e3bb-111">In der Liste werden die für die einzelnen Pools verfügbaren Skripts sowie deren Aktivierung oder kritische Anzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-111">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="7e3bb-112">Die Skripts werden in der Reihenfolge ausgeführt, in der Sie aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-112">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="7e3bb-113">Zu diesen Skripts gehören die folgenden:</span><span class="sxs-lookup"><span data-stu-id="7e3bb-113">These scripts include the following:</span></span>

  - <span data-ttu-id="7e3bb-114">ClientVersionFilter bietet dem Administrator die Möglichkeit, die Version der Clients anzugeben, die von einem Pool unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-114">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool.</span></span> <span data-ttu-id="7e3bb-115">Der Clientversionsfilter überprüft die Client Version und kann entweder verhindern, dass der Client sich anmeldet oder den Benutzer mit einer Meldung zeigt, die angibt, dass er einen Client verwendet, der nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-115">The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported.</span></span> <span data-ttu-id="7e3bb-116">Der Clientversionsfilter kann auch so konfiguriert werden, dass dem Benutzer eine Meldung angezeigt wird, die die URL der neuesten herunterladbaren Version des Clients enthält.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-116">The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="7e3bb-117">TranslationService übersetzt eine Zahl, die ein Benutzer entsprechend den vom Administrator definierten Normalisierungsregeln zu einer E. 164-Nummer wählt.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-117">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="7e3bb-118">Ausführliche Informationen finden Sie unter [Übersetzungsregeln in lync Server 2013](lync-server-2013-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="7e3bb-118">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="7e3bb-119">IncomingFederation erzwingt die Föderations Überprüfung auf Mandantenebene für Mandantenübergreifende und eingehende Nachrichten von externen Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-119">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="7e3bb-120">UserServices ist die SIP-Registrierungsstelle, Anwesenheits-und Konferenz Komponente eines Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-120">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server.</span></span> <span data-ttu-id="7e3bb-121">Es bietet eng integrierte Chat-, Anwesenheits-und Konferenzfeatures, die auf dem SIP-Proxy aufgebaut sind.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-121">It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="7e3bb-122">InterClusterRouting ist für das Weiterleiten von Anrufen an den primären Registrierungspool des anrufenden verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-122">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="7e3bb-123">Ausführliche Informationen finden Sie unter [Front-End-Server-VoIP-Komponenten für lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span><span class="sxs-lookup"><span data-stu-id="7e3bb-123">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="7e3bb-124">IIMFilter (intelligenter Chat Filter) blockiert Nachrichten, die klickable-URLs enthalten, oder die versuchen, Dateiübertragungen zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-124">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="7e3bb-125">IIMFilter überprüft auch die Client Version im Namen des Servers.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-125">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="7e3bb-126">IIMFilter wirkt sich auf Dateiübertragungen aus, die entweder mit lync Server oder Communicator initiiert werden.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-126">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="7e3bb-127">Standardmäßig sind klickable-Links deaktiviert, indem Sie vor dem ersten Zeichen des Links einen Unterstrich hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-127">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="7e3bb-128">Ein Administrator kann dieses Verhalten so ändern, dass der Link blockiert wird, wobei Nachrichten, die Klick Bare URLs enthalten oder die versuchen, eine Dateiübertragung zu initiieren, vom Server blockiert werden, um die beabsichtigten Ziele zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-128">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="7e3bb-129">IIMFilter ist auf allen Servern mit lync Server mit Ausnahme von Proxy Servern und Archivierungsservern installiert.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-129">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="7e3bb-130">UserPinService wird verwendet, um persönliche Identifikationsnummern (Pins) des Benutzers für Einwahlkonferenzen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-130">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="7e3bb-131">DefaultRouting ist die Standardrouting Anwendung für Server, auf denen lync Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-131">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="7e3bb-132">Sie ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-132">It is enabled by default.</span></span> <span data-ttu-id="7e3bb-133">Die Routing Anwendung ist auf allen Standard Edition-und Enterprise Edition-Servern installiert.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-133">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="7e3bb-134">ExumRouting leitet Anrufe an Exchange Server Unified Messaging (um) weiter.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-134">ExumRouting routes calls to Exchange Server Unified Messaging (UM).</span></span> <span data-ttu-id="7e3bb-135">ExumRouting bestimmt den entsprechenden Exchange um-Server zum Weiterleiten des Anrufs an die Stelle, an der eine neue Voicemail-Nachricht hinterlegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-135">ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit.</span></span> <span data-ttu-id="7e3bb-136">ExumRouting behandelt auch einige andere Exchange um-Integrationsaspekte, einschließlich Routing an automatische Telefonzentrale und Teilnehmerzugriff.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-136">ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="7e3bb-137">OutboundRouting bestimmt das Gateway, das einen Anruf an eine Telefonnummer weiterleitet, entsprechend der gewählten Nummer und der Wähl Berechtigung des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-137">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization.</span></span> <span data-ttu-id="7e3bb-138">OutboundRouting behandelt auch das Umleiten von anrufen, wenn ein Gateway keinen Anruf verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-138">OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="7e3bb-139">QoEAgent erhält QoE-Daten Berichte (Quality of Experience) von Endpunkten über SIP-Dienstanforderungen und sendet die Daten mithilfe von HTTP Post an die Zielwarteschlange auf dem Überwachungs Server oder an Drittanbieter.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-139">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="7e3bb-140">Ausführliche Informationen finden Sie unter [Bereitstellen der Überwachung in lync Server 2013](lync-server-2013-deploying-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="7e3bb-140">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="7e3bb-141">OutgoingFederation erzwingt die Föderations Überprüfung auf Mandantenebene für Nachrichten, die an eine Ziel externe Bereitstellung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-141">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="7e3bb-142">AcpRouting-Proxys laden Anforderungen, die für den Audiokonferenz-Anbieter bestimmt sind, an das Audiokonferenz-Anbieter Gateway ein.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-142">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="7e3bb-143">Zu den Skripts, die auf Edgeserver ausgeführt werden, gehören die folgenden:</span><span class="sxs-lookup"><span data-stu-id="7e3bb-143">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="7e3bb-144">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="7e3bb-144">IIMFilter</span></span>

  - <span data-ttu-id="7e3bb-145">OptionsHandler reagiert auf eingehende Options Anforderungen mit **200 OK** , wenn die Anforderung für den aktuellen Server bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-145">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="7e3bb-146">Diese wird für die Topologie-Validierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7e3bb-146">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="7e3bb-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e3bb-147">See Also</span></span>


[<span data-ttu-id="7e3bb-148">Aktivieren oder Deaktivieren einer Microsoft SIP Processing Language (MSPL)-Serveranwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e3bb-148">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="7e3bb-149">Kennzeichnen einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e3bb-149">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

<span data-ttu-id="7e3bb-150"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="7e3bb-150"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

