---
title: 'Lync Server 2013: Richtlinien für die Enterprise-VoIP-Bereitstellung'
description: 'Lync Server 2013: Bereitstellungsrichtlinien für Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cd847f674ad4b04698be0f54f8fbd490b13d689
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49429692"
---
# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="5558c-103">Richtlinien für die Enterprise-VoIP-Bereitstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5558c-103">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="5558c-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="5558c-104">

<span> </span></span></span>

<span data-ttu-id="5558c-105">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5558c-105">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5558c-106">In diesem Thema werden die Voraussetzungen und anderen Richtlinien beschrieben, die bei der Bereitstellung von lync Server 2013 und der Enterprise-VoIP-Arbeitsauslastung zu beachten sind.</span><span class="sxs-lookup"><span data-stu-id="5558c-106">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="5558c-107">Voraussetzungen für die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="5558c-107">Deployment Prerequisites</span></span>

<span data-ttu-id="5558c-108">Für eine optimale Benutzerfreundlichkeit bei der Bereitstellung von Enterprise-VoIP stellen Sie sicher, dass Ihre IT-Infrastruktur, Ihr Netzwerk und ihre Systeme die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="5558c-108">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="5558c-109">Lync Server 2013 Standard Edition oder Enterprise Edition ist in Ihrem Netzwerk installiert und betriebsbereit.</span><span class="sxs-lookup"><span data-stu-id="5558c-109">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="5558c-110">Alle Edgeserver werden in Ihrem Umkreisnetzwerk bereitgestellt und in Betrieb genommen, einschließlich Edgeserver mit Access Edge Service, a/V Edge Service, Web Conferencing Edge Service und einem Reverse Proxy.</span><span class="sxs-lookup"><span data-stu-id="5558c-110">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="5558c-111">Mindestens ein Benutzer wurde für lync Server erstellt und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5558c-111">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="5558c-112">Microsoft Exchange Server 2007 Service Pack 1 (SP1) oder neuestes Service Pack oder Microsoft Exchange Server 2010 ist installiert.</span><span class="sxs-lookup"><span data-stu-id="5558c-112">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="5558c-113">Eine dieser Funktionen ist für die Integration von Exchange Unified Messaging (um) in lync Server und für die Bereitstellung umfassender Benachrichtigungen und Anrufprotokoll Informationen für Clientendpunkte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5558c-113">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="5558c-114">Für jeden Benutzer, der für Enterprise-VoIP aktiviert werden soll, wurde eine eindeutige primäre Telefonnummer festgelegt, normalisiert und in das **Attribut msRTCSIP-** Attribut kopiert.</span><span class="sxs-lookup"><span data-stu-id="5558c-114">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5558c-115">Lync Server unterstützt E. 164-Nummern und nicht Direkteinwahl Nummern (DID).</span><span class="sxs-lookup"><span data-stu-id="5558c-115">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="5558c-116">Nicht-did-Zahlen können im Format <STRONG> &lt; E. 164 &gt; ; Ext = &lt; Extension &gt; </STRONG> oder als Zeichenfolge von Ziffern dargestellt werden, mit der Voraussetzung, dass die private Erweiterung im gesamten Unternehmen eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="5558c-116">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="5558c-117">Beispielsweise kann eine private Zahl von 1001 als <STRONG>+ 1425550100; ext = 1001</STRONG>oder als <STRONG>1001</STRONG>dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5558c-117">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="5558c-118">Wenn Sie als <STRONG>1001</STRONG>dargestellt wird, wird davon ausgegangen, dass diese private Nummer im gesamten Unternehmen eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="5558c-118">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="5558c-119">Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglieder der RTCUniversalServerAdmins-Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="5558c-119">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="5558c-120">Office Communicator 2007 wird mindestens erfolgreich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5558c-120">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="5558c-121">Um Features zu verwenden, die in dieser Version neu sind, wird lync 2013 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5558c-121">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="5558c-122">Die Managed Key-Infrastruktur (MkII) wird mithilfe einer Microsoft-oder einer Drittanbieter-Infrastruktur (Certification Authority, ca) bereitgestellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5558c-122">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="5558c-123">Jeder Computer, auf dem Sie den Vermittlungs Server installieren, muss wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="5558c-123">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="5558c-124">Einen Mitgliedsserver einer Domäne und für die Active Directory-Domänendienste vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="5558c-124">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="5558c-125">Informationen zur Vorbereitung der Active Directory-Domänendienste finden Sie unter [Vorbereiten der Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="5558c-125">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="5558c-126">Führen Sie eines der folgenden Betriebssysteme aus:</span><span class="sxs-lookup"><span data-stu-id="5558c-126">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="5558c-127">Die 64-Bit-Version des Windows Server 2008-Standard Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="5558c-127">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="5558c-128">Die 64-Bit-Version des Windows Server 2008 Enterprise-Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="5558c-128">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="5558c-129">Wenn die Verbindung mit dem PSTN (Public Switched Telephone Network) oder der PBX (Private Branch Exchange) über eine Time Division Multiplexing (TDM)-Verbindung erfolgt, stehen mindestens ein PSTN-Gateway für die Bereitstellung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5558c-129">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment.</span></span> <span data-ttu-id="5558c-130">(Wenn die Verbindung über einen SIP-Stamm erfolgt, ist kein PSTN-Gateway erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="5558c-130">(If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="5558c-131">Strom-, Netzwerk-oder Telefondienst Ausfälle</span><span class="sxs-lookup"><span data-stu-id="5558c-131">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="5558c-132">Wenn es zu einem Ausfall, zu einer Unterbrechung oder zu einer anderen Verschlechterung der Strom-, Netzwerk-oder Telefondienste an Ihrem Standort kommt, funktionieren die sprach-, Chat-, Anwesenheits-und anderen Funktionen von lync Server und jedes mit lync Server verbundene Gerät möglicherweise nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="5558c-132">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="5558c-133">Enterprise-VoIP hängt von der Server Verfügbarkeit und der Funktionsfähigkeit des sprach Clients und der Hardware ab</span><span class="sxs-lookup"><span data-stu-id="5558c-133">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="5558c-134">Die Sprachkommunikation mit lync Server hängt von der Verfügbarkeit der Server Software und der ordnungsgemäßen Funktion der VoIP-Clients oder der Hardware-Telefongeräte ab, die mit der Server Software verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="5558c-134">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="5558c-135">Alternative Möglichkeiten für den Zugriff auf Notfalldienste</span><span class="sxs-lookup"><span data-stu-id="5558c-135">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="5558c-136">Für die Speicherorte, an denen Sie einen VoIP-Client installieren (beispielsweise einen PC mit lync-Client oder ein lync Phone Edition-Gerät), empfehlen wir, dass Sie eine Sicherungsoption für Benutzer zum Aufrufen von Notfalldiensten (beispielsweise 911 oder 999) im Fall eines Stromausfalls, einer Verschlechterung der Netzwerkverbindung, eines Telefondienst Ausfalls oder eines anderen Problems verwalten, das , Lync oder lync Phone Edition-Geräten.</span><span class="sxs-lookup"><span data-stu-id="5558c-136">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="5558c-137">Solche Alternativen können auch ein Telefon sein, das an eine standardmäßige öffentlich geschaltete Telefonnetz Leitung oder ein Mobiltelefon angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5558c-137">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="5558c-138">Notrufe und mehrzeilige Telefonanlagen</span><span class="sxs-lookup"><span data-stu-id="5558c-138">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="5558c-139">Die Verwendung eines mehrzeiligen Telefonsystems (MLTS) unterliegt möglicherweise den US-bundesstaatlichen oder bundesstaatlichen Gesetzen oder den Gesetzen anderer Länder/Regionen, in denen die MLTS die Telefonnummer, die Durchwahl und/oder den physischen Standort eines Anrufers für die entsprechenden Notfalldienste zur Verfügung stellen muss, wenn ein Anrufer in die Notfalldienste gestellt wird (beispielsweise bei der Wahl einer 999 911 Notruf</span><span class="sxs-lookup"><span data-stu-id="5558c-139">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="5558c-140">In dieser Version kann lync Server so konfiguriert werden, dass der physikalische Standort eines Anrufers einem Notrufdienst Anbieter bereitgestellt wird, wie unter [Planen von Notfalldiensten (E9-1-1) in lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5558c-140">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="5558c-141">Die Einhaltung der MLTS-Gesetze obliegt der alleinigen Verantwortung des Käufers von lync Server-, lync-Client-und lync Phone Edition-Geräten.</span><span class="sxs-lookup"><span data-stu-id="5558c-141">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

<span data-ttu-id="5558c-142"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="5558c-142"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

