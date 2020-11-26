---
title: 'Lync Server 2013: Ausfallsicherheitsfunktionen für Zweigstellenstandorte'
description: 'Lync Server 2013: Features für die Stabilität von Branch-Site.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a498751ce99d0e8e85d6cbe53915c864e64440bd
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49436020"
---
# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="706fd-103">Ausfallsicherheitsfunktionen für Zweigstellenstandorte in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="706fd-103">Branch-site resiliency features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="706fd-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="706fd-104">

<span> </span></span></span>

<span data-ttu-id="706fd-105">_**Letztes Änderungsdatum des Themas:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="706fd-105">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="706fd-106">Wenn Sie eine Ausfallsicherheit für Zweigstellen angeben, wenn die WAN-Verbindung einer Zweigstelle zu einem zentralen Standort fehlschlägt oder wenn der zentrale Standort nicht erreichbar ist, sollten die folgenden Sprachfeatures weiterhin zur Verfügung stehen:</span><span class="sxs-lookup"><span data-stu-id="706fd-106">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="706fd-107">Eingehende und ausgehende PSTN-Anrufe (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="706fd-107">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="706fd-108">Enterprise-Anrufe zwischen Benutzern am gleichen Standort und zwischen zwei unterschiedlichen Websites</span><span class="sxs-lookup"><span data-stu-id="706fd-108">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="706fd-109">Einfache Anrufbehandlung, einschließlich Anruf halten, abrufen und übertragen</span><span class="sxs-lookup"><span data-stu-id="706fd-109">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="706fd-110">Instant Messaging mit zwei Teilnehmern</span><span class="sxs-lookup"><span data-stu-id="706fd-110">Two-party instant messaging</span></span>

  - <span data-ttu-id="706fd-111">Anrufweiterleitung, gleichzeitiges Klingeln von Endpunkten, Anrufdelegierung und Team Anrufdienste, aber nur, wenn der delegator und Stellvertreter (beispielsweise ein Manager und der Administrator des Managers) oder alle Teammitglieder am gleichen Standort konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="706fd-111">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="706fd-112">Anruf Detaildatensätze (CDRs)</span><span class="sxs-lookup"><span data-stu-id="706fd-112">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="706fd-113">PSTN-Einwahlkonferenzen mit automatischer Konferenz Automatik</span><span class="sxs-lookup"><span data-stu-id="706fd-113">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="706fd-114">Voicemail-Funktionen, wenn Sie die Einstellungen für die Umleitung von Voicemail konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="706fd-114">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="706fd-115">(Ausführliche Informationen finden Sie unter Anforderungen an die [Stabilität der Zweigstelle für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span><span class="sxs-lookup"><span data-stu-id="706fd-115">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="706fd-116">Benutzerauthentifizierung und Autorisierung</span><span class="sxs-lookup"><span data-stu-id="706fd-116">User authentication and authorization</span></span>

<span data-ttu-id="706fd-117">Die folgenden Features stehen nur zur Verfügung, wenn Ihre Resilienz-Lösung eine vollständige lync Server-Bereitstellung auf der Zweigstelle ist:</span><span class="sxs-lookup"><span data-stu-id="706fd-117">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="706fd-118">Chat-, Web-und A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="706fd-118">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="706fd-119">Anwesenheits-und (nicht stören)-basiertes Routing (wenn Anrufe an Erweiterungen, die mit "nicht aktiviert" sind, verhindert werden)</span><span class="sxs-lookup"><span data-stu-id="706fd-119">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="706fd-120">Aktualisieren der Einstellungen für die Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="706fd-120">Updating call forwarding settings</span></span>

  - <span data-ttu-id="706fd-121">Anwendung für Reaktionsgruppen und Anruf parken</span><span class="sxs-lookup"><span data-stu-id="706fd-121">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="706fd-122">Bereitstellungneuer Telefone und Clients, jedoch nur, wenn die Active Directory-Domänendienste auf der Zweigstelle vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="706fd-122">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="706fd-123">Enhanced 9-1-1 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="706fd-123">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="706fd-124">Wenn E9-1-1 bereitgestellt wird und der SIP-Stamm am zentralen Standort nicht zur Verfügung steht, weil die WAN-Verbindung nicht verfügbar ist, leitet die Survivable Branch-Appliance E9-1-1-Anrufe an das lokale Verzweigung-Gateway weiter.</span><span class="sxs-lookup"><span data-stu-id="706fd-124">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="706fd-125">Um dieses Feature zu aktivieren, sollten die VoIP-Richtlinien für die Zweigstellenbenutzer im Fall eines WAN-Fehlers Anrufe an das lokale Gateway weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="706fd-125">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="706fd-126">SBA (Survivor Branch Office) wird für XMPP nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="706fd-126">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="706fd-127">Benutzer, die in einer SBA-Konfiguration verwaltet werden, können keine IMS senden oder Anwesenheitsinformationen mit XMPP-Kontakten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="706fd-127">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



<span data-ttu-id="706fd-128"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="706fd-128"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

