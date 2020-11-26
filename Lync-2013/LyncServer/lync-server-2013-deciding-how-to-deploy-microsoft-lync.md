---
title: 'Lync Server 2013: Entscheiden, wie Microsoft Lync bereitgestellt werden soll'
description: 'Lync Server 2013: entscheiden, wie Microsoft lync bereitgestellt wird.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a800b51dfddc6f2c99e42c8f117056ed4091b6a5
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431232"
---
# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="6c8ec-103">Entscheiden, wie Lync Server 2013 bereitgestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="6c8ec-103">Deciding how to deploy Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="6c8ec-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="6c8ec-104">

<span> </span></span></span>

<span data-ttu-id="6c8ec-105">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="6c8ec-105">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="6c8ec-106">Bei der Planung für lync ist die erste wichtige Entscheidung, wie Microsoft lync bereitgestellt wird: als lync Server 2013 lokal oder lync online mit Microsoft 365 oder Office 365 in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-106">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft 365 or Office 365 in the cloud.</span></span>

  - <span data-ttu-id="6c8ec-107">**Lync Server 2013 lokal** : Diese Auswahl bietet den vollständigen lync-Funktionssatz und bietet höchste Flexibilität bei der Konfiguration, dem anpassen und dem Betrieb Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-107">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="6c8ec-108">Alle Server werden vor Ort installiert und von Ihrer Organisation verwaltet.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-108">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="6c8ec-109">Eine lokale Bereitstellung bietet die gesamte Palette der lync Server-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-109">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="6c8ec-110">**Lync Online in der Cloud** Lync Online ist für Organisationen konzipiert, die den Kosten-und Agilitäts Vorteil von Cloud-basiertem Instant Messaging, Anwesenheitsinformationen und Besprechungen benötigen, ohne die Business-Class-Funktionen von lync Server zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-110">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="6c8ec-111">Mit lync Online stellt Microsoft die erforderliche Serverinfrastruktur bereit und verwaltet Sie und verarbeitet laufende Wartung, Patches und Upgrades.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-111">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="6c8ec-112">Einige Features, die in einer lokalen Bereitstellung verfügbar sind, stehen in lync Online nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-112">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="6c8ec-113">Welche Art der Bereitstellung für Sie am besten geeignet ist, hängt von den Arbeitsauslastungen, die Sie bereitstellen möchten, und dem geografischen und geschäftlichen Status Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-113">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="6c8ec-114">Lync Server</span><span class="sxs-lookup"><span data-stu-id="6c8ec-114">Lync Server</span></span>

<span data-ttu-id="6c8ec-115">Eine lokale lync Server-Bereitstellung eignet sich am besten für die folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="6c8ec-115">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="6c8ec-116">**Vollständige Enterprise-VoIP-Funktionen**   Wenn Sie beabsichtigen, eine vollständige Enterprise-VoIP-Lösung bereitzustellen, um Ihre Telefonanlage zu ersetzen oder erweiterte Anruffunktionen verwendet, ist eine lokale lync Server-Bereitstellung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-116">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="6c8ec-117">Lokale Unterstützung bietet direkte Konnektivität mit PBX-Systemen und-Stämmen sowie erweiterte Telefonfunktionen wie Reaktionsgruppen und Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-117">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="6c8ec-118">Lync Online unterstützt diese Features zurzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-118">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="6c8ec-119">**Media Quality-Steuerelemente**   Wenn Sie die gesamte Bandbreite der Medien Qualitätssicherungs-Features wie Anrufannahme Steuerung (CAC) und QoS-Features (Quality of Service) nutzen möchten, benötigen Sie eine lokale Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-119">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="6c8ec-120">**Beständiger Chat**   Wenn Sie den beständigen Chat für Ihre Organisation bereitstellen müssen, müssen Sie eine lokale Bereitstellung auswählen.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-120">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="6c8ec-121">**Server Anwendungen von Drittanbietern**   Nur lokale Bereitstellungen können mit vertrauenswürdigen Drittanbieteranwendungen funktionieren, die die Microsoft Unified Communications Managed API (UCMA) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-121">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="6c8ec-122">**Multi-National/Multi-Regional-Unternehmen, die regionale Unterstützung benötigen**   Wenn Sie über Rechenzentren in mehreren Ländern oder Regionen verfügen und Server auf regionaler Basis bereitgestellt und verwaltet werden müssen, ist eine lokale Bereitstellung am besten geeignet, da diese Art von regionalen Verwaltungsfunktionen zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-122">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="6c8ec-123">**Vollständige Kontrolle über Richtlinien, Berichte und Upgrades**   Mit einer lokalen lync Server-Bereitstellung haben Sie Zugriff auf den vollständigen Satz von Server-und Clientrichtlinien, Überwachungs-und anderen Berichten sowie die Anzeigedauer von Upgrades.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-123">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="6c8ec-124">Lync Online bietet eine Teilmenge der Richtlinieneinstellungen und-Berichte und bietet ein limitiertes, wenn auch erhebliches Fenster für das akzeptieren von Upgrades.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-124">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="6c8ec-125">Lync Online</span><span class="sxs-lookup"><span data-stu-id="6c8ec-125">Lync Online</span></span>

<span data-ttu-id="6c8ec-126">Wenn keiner der Faktoren in der vorstehenden Liste für Sie von entscheidender Bedeutung ist, sollten Sie lync online zur einfacheren Bereitstellung und Verwaltbarkeit auswählen.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-126">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="6c8ec-127">Lync Online bietet eine robuste Chat-, Anwesenheits-und Konferenz Funktionsgruppe und ermöglicht auch sprach-und Videoanrufe über IP zwischen Benutzern in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="6c8ec-127">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

<span data-ttu-id="6c8ec-128"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="6c8ec-128"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>
