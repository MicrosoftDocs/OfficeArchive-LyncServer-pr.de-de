---
title: 'Lync Server 2013: VoIP-Komponenten des Front-End-Servers'
description: 'Lync Server 2013: VoIP-Komponenten des Front-End-Servers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9390d06cf6277ef79ec2ec785bad4b497bc04a7
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428041"
---
# <a name="front-end-server-voip-components-for-lync-server-2013"></a><span data-ttu-id="a9342-103">Front-End-Server-VoIP-Komponenten für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9342-103">Front End Server VoIP components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="a9342-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="a9342-104">

<span> </span></span></span>

<span data-ttu-id="a9342-105">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a9342-105">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a9342-106">Die VoIP-Komponenten, die sich auf Front-End-Servern befinden, sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a9342-106">The VoIP components located on Front End Servers are as follows:</span></span>

  - <span data-ttu-id="a9342-107">Übersetzungsdienst</span><span class="sxs-lookup"><span data-stu-id="a9342-107">Translation Service</span></span>

  - <span data-ttu-id="a9342-108">Eingangsroutingkomponente</span><span class="sxs-lookup"><span data-stu-id="a9342-108">Inbound Routing component</span></span>

  - <span data-ttu-id="a9342-109">Ausgangsroutingkomponente</span><span class="sxs-lookup"><span data-stu-id="a9342-109">Outbound Routing component</span></span>

  - <span data-ttu-id="a9342-110">Routingkomponente für Exchange UM</span><span class="sxs-lookup"><span data-stu-id="a9342-110">Exchange UM Routing component</span></span>

  - <span data-ttu-id="a9342-111">Komponente für das clusterübergreifende Routing</span><span class="sxs-lookup"><span data-stu-id="a9342-111">Intercluster Routing component</span></span>

  - [<span data-ttu-id="a9342-112">Vermittlungsserver Komponente in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9342-112">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a><span data-ttu-id="a9342-113">Übersetzungsdienst</span><span class="sxs-lookup"><span data-stu-id="a9342-113">Translation Service</span></span>

<span data-ttu-id="a9342-p101">Der Übersetzungsdienst ist die Serverkomponente, die eine gewählte Nummer gemäß den vom Administrator definierten Normalisierungsregeln in das E.164-Format oder ein anderes Format übersetzt. Der Übersetzungsdienst kann in andere Formate als E.164 übersetzen, wenn in Ihrer Organisation ein privates Nummernsystem oder ein Gateway bzw. eine Nebenstellenanlage verwendet wird, das bzw. die E.164 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9342-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

</div>

<div>

## <a name="inbound-routing-component"></a><span data-ttu-id="a9342-116">Eingangsroutingkomponente</span><span class="sxs-lookup"><span data-stu-id="a9342-116">Inbound Routing Component</span></span>

<span data-ttu-id="a9342-117">Die eingehende Routing Komponente verarbeitet eingehende Anrufe weitgehend gemäß den Einstellungen, die von Benutzern auf Ihren Enterprise-VoIP-Clients angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a9342-117">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="a9342-118">Diese Komponente unterstützt außerdem das Delegieren von Anrufen und das gleichzeitige Klingeln, sofern dies vom Benutzer konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="a9342-118">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="a9342-119">Beispielsweise geben Benutzer an, ob unbeantwortete Anrufe weitergeleitet oder lediglich zur Benachrichtigung protokolliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a9342-119">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="a9342-120">Wenn die Anrufweiterleitung aktiviert ist, können Benutzer angeben, ob nicht angenommene Anrufe an eine andere Nummer oder an einen Exchange um-Server weitergeleitet werden sollen, der für die Anrufannahme konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="a9342-120">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="a9342-121">Die eingehende Routing Komponente wird standardmäßig auf allen Standard Edition-Server-und-Front-End-Servern installiert.</span><span class="sxs-lookup"><span data-stu-id="a9342-121">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

</div>

<div>

## <a name="outbound-routing-component"></a><span data-ttu-id="a9342-122">Ausgangsroutingkomponente</span><span class="sxs-lookup"><span data-stu-id="a9342-122">Outbound Routing Component</span></span>

<span data-ttu-id="a9342-123">Die Ausgangsroutingkomponente leitet Anrufe an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weiter.</span><span class="sxs-lookup"><span data-stu-id="a9342-123">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="a9342-124">Sie wendet (gemäß Definition in der VoIP-Richtlinie für den Benutzer) Anrufautorisierungsregeln auf Anrufer an und ermittelt das optimale PSTN-Gateway für das Routing der einzelnen Anrufe.</span><span class="sxs-lookup"><span data-stu-id="a9342-124">It applies call authorization rules, as defined by the user’s voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="a9342-125">Die ausgehende Routing Komponente wird standardmäßig auf allen Standard Edition-Server-und-Front-End-Servern installiert.</span><span class="sxs-lookup"><span data-stu-id="a9342-125">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="a9342-126">Die Ausgangsroutingkomponente verwendet eine Routinglogik, die größtenteils von Netzwerk- oder Telefonieadministratoren gemäß den Anforderungen ihrer Organisationen konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="a9342-126">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

</div>

<div>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="a9342-127">Routingkomponente für Exchange UM</span><span class="sxs-lookup"><span data-stu-id="a9342-127">Exchange UM Routing Component</span></span>

<span data-ttu-id="a9342-128">Die Exchange um-Routingkomponente verarbeitet das Routing zwischen lync Server und Servern, auf denen Exchange Unified Messaging (um) ausgeführt wird, um lync Server mit Unified Messaging-Features zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="a9342-128">The Exchange UM routing component handles routing between Lync Server and servers running Exchange Unified Messaging (UM), to integrate Lync Server with Unified Messaging features.</span></span>

<span data-ttu-id="a9342-129">Die Exchange um-Routingkomponente behandelt auch das Umleiten von Voicemail über das PSTN, wenn Exchange um-Server nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a9342-129">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="a9342-130">Wenn Sie über Enterprise-VoIP-Benutzer an Zweigstellen verfügen, die nicht über eine stabile WAN-Verbindung zu einem zentralen Standort verfügen, bietet die Survivable Branch-Appliance, die Sie auf der Zweigstelle bereitstellen, die Voicemail-Überlebensfähigkeit von Zweig Benutzern während eines WAN-Ausfalls.</span><span class="sxs-lookup"><span data-stu-id="a9342-130">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="a9342-131">Wenn die WAN-Verbindung nicht verfügbar ist, führt die Survivable Branch-Appliance die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a9342-131">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

  - <span data-ttu-id="a9342-132">Nicht beantwortete Anrufe werden über das Telefonfestnetz an den Exchange Unified Messaging-Server am zentralen Standort weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="a9342-132">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

  - <span data-ttu-id="a9342-133">Benutzer haben die Möglichkeit, Voicemailnachrichten über das Telefonfestnetz abzurufen</span><span class="sxs-lookup"><span data-stu-id="a9342-133">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

  - <span data-ttu-id="a9342-134">Benachrichtigungen zu verpassten Anrufen werden in einer Warteschlange platziert und auf den Exchange UM-Server hochgeladen, wenn die WAN-Verbindung wieder verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a9342-134">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="a9342-135">Zum Aktivieren des Umleitens von Voicemail empfehlen wir, dass Ihr Exchange-Administrator die automatische Exchange UM-Telefonzentrale (AA) so konfiguriert, dass nur Nachrichten akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="a9342-135">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="a9342-136">Details zu diesen Features finden Sie unter [Planen der Exchange Unified Messaging-Integration in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) und [Planen der Stabilität von Enterprise-VoIP in lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="a9342-136">For details about these features, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectively.</span></span>

</div>

<div>

## <a name="intercluster-routing-component"></a><span data-ttu-id="a9342-137">Komponente für das clusterübergreifende Routing</span><span class="sxs-lookup"><span data-stu-id="a9342-137">Intercluster Routing Component</span></span>

<span data-ttu-id="a9342-p105">Diese Komponente sorgt für das Routing von Anrufen beim primären Registrierungsstellenpool des Anrufempfängers. Wenn dieser Pool nicht verfügbar ist, leitet die Komponente den Anruf an den Backup-Registrierungsstellenpool des Anrufempfängers weiter. Wenn keiner der beiden Pools über das IP-Netzwerk erreicht werden kann, leitet die Komponente für das clusterübergreifende Routing den Anruf über das Telefonfestnetz an die Rufnummer des Benutzers um.</span><span class="sxs-lookup"><span data-stu-id="a9342-p105">The Intercluster routing component is responsible for routing calls to the callee’s primary Registrar pool. If that is unavailable, the component routes the call to the callee’s backup Registrar pool. If the callee’s primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user’s telephone number.</span></span>

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="a9342-141">Andere für VoIP erforderliche Front-End-Serverkomponenten</span><span class="sxs-lookup"><span data-stu-id="a9342-141">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="a9342-142">Andere Komponenten, die sich auf dem Front-End-Server oder Director befinden und die grundlegende Unterstützung für VoIP bieten, aber nicht selbst VoIP-Komponenten sind, umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a9342-142">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

  - <span data-ttu-id="a9342-143">**Benutzerdienste.**</span><span class="sxs-lookup"><span data-stu-id="a9342-143">**User Services.**</span></span> <span data-ttu-id="a9342-144">Die Benutzerdienste führen eine umgekehrte Nummernsuche für die Zielrufnummer jedes eingehenden Anrufs durch und ordnen diese Nummer dem SIP-URI des Zielbenutzers zu.</span><span class="sxs-lookup"><span data-stu-id="a9342-144">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="a9342-145">Mithilfe dieser Informationen verteilt die Eingangsroutingkomponente den Anruf an die registrierten SIP-Endpunkte dieses Benutzers.</span><span class="sxs-lookup"><span data-stu-id="a9342-145">Using this information, the Inbound Routing component distributes the call to that user’s registered SIP endpoints.</span></span> <span data-ttu-id="a9342-146">Benutzer Dienste ist eine Hauptkomponente auf allen Front-End-Servern und-Directors.</span><span class="sxs-lookup"><span data-stu-id="a9342-146">User Services is a core component on all Front End Servers and Directors.</span></span>

  - <span data-ttu-id="a9342-147">**Benutzerreplikationsdienst**</span><span class="sxs-lookup"><span data-stu-id="a9342-147">**User Replicator.**</span></span> <span data-ttu-id="a9342-148">Extrahiert Benutzer Telefonnummern aus Active Directory-Domänendiensten und schreibt Sie in Tabellen in der RTC-Datenbank, wo Sie für Benutzer Dienste und den Adressbuch Server verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a9342-148">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="a9342-149">Der Benutzerreplikationsdienst ist eine Hauptkomponente auf allen Front-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="a9342-149">User Replicator is a core component on all Front End Servers.</span></span>

  - <span data-ttu-id="a9342-150">**Adressbuchserver.**</span><span class="sxs-lookup"><span data-stu-id="a9342-150">**Address Book Server.**</span></span> <span data-ttu-id="a9342-151">Enthält Informationen zur globalen Adressliste aus Active Directory-Domänendiensten für lync Server-Clients.</span><span class="sxs-lookup"><span data-stu-id="a9342-151">Provides global address list information from Active Directory Domain Services to Lync Server clients.</span></span> <span data-ttu-id="a9342-152">Sie ruft auch Benutzer-und Kontaktinformationen aus der RTC-Datenbank ab, schreibt die Informationen in die Adressbuchdateien und speichert die Dateien dann in einem freigegebenen Ordner, in dem Sie von lync-Clients heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="a9342-152">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Lync clients.</span></span> <span data-ttu-id="a9342-153">Der Adressbuch Server schreibt die Informationen in die RTCAb-Datenbank, die vom Adressbuch-Webabfrage Dienst verwendet wird, um auf Benutzer Suchabfragen von Microsoft lync 2010 Mobile zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="a9342-153">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="a9342-154">Optional werden Unternehmensbenutzer-Telefonnummern, die in die RTC-Datenbank geschrieben wurden, zum Zweck der Bereitstellung von Benutzerkontakten in lync normalisiert.</span><span class="sxs-lookup"><span data-stu-id="a9342-154">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Lync.</span></span> <span data-ttu-id="a9342-155">Der Adressbuchdienst wird standardmäßig auf allen Front-End-Servern installiert.</span><span class="sxs-lookup"><span data-stu-id="a9342-155">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="a9342-156">Der Adressbuch-Webabfrage Dienst wird standardmäßig mit den Webdiensten auf den einzelnen Front-End-Servern installiert.</span><span class="sxs-lookup"><span data-stu-id="a9342-156">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>

<span data-ttu-id="a9342-157"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="a9342-157"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

