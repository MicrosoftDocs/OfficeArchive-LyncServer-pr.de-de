---
title: Anforderungen an Sicherheit und Konfiguration für Enterprise-VoIP
description: Voraussetzungen für Sicherheit und Konfiguration für Enterprise-VoIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d0940450889c6bf26cb7761bebbce5e6c2d3f2
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49444898"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="2246d-103">Voraussetzungen für Sicherheit und Konfiguration für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2246d-103">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="2246d-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="2246d-104">

<span> </span></span></span>

<span data-ttu-id="2246d-105">_**Letztes Änderungsdatum des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="2246d-105">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="2246d-106">Überprüfen Sie, ob Ihre Infrastruktur die folgenden Sicherheits-, Benutzer Konfigurations-und Szenario-spezifischen Hardwarevoraussetzungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="2246d-106">Verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span>

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="2246d-107">Administratorrechte und Zertifikatinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="2246d-107">Administrative Rights and Certificate Infrastructure</span></span>

<span data-ttu-id="2246d-108">Stellen Sie sicher, dass Ihre Umgebung mit den folgenden administrativen Benutzergruppen und der Zertifikatinfrastruktur für die Verwendung während des Enterprise-VoIP-Bereitstellungsprozesses konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="2246d-108">Be sure that your environment is configured with the following administrative user groups and certificate infrastructure for use during the Enterprise Voice deployment process.</span></span>

  - <span data-ttu-id="2246d-109">Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglieder der RTCUniversalServerAdmins-Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="2246d-109">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="2246d-110">Administratoren, die die Konfigurationsaufgaben ausführen, müssen über geeignete Rechte verfügen:</span><span class="sxs-lookup"><span data-stu-id="2246d-110">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
      - <span data-ttu-id="2246d-111">**CsVoiceAdministrator:** Diese Administratorrolle kann VoIP-Konfigurationsaufgaben ausführen, VoIP-Anwendungen verwalten und Endbenutzern VoIP-Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2246d-111">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
      - <span data-ttu-id="2246d-p101">**CsUserAdministrator:** Diese Administratorrolle kann Benutzereigenschaften verwalten, z. B. die Aktivierung von Enterprise-VoIP für einen Benutzer. Diese Administratorrolle kann außerdem benutzerbasierte Richtlinien zuweisen. Hiervon ausgenommen sind die Archivierungsrichtlinie, das Verschieben von Benutzern, das Verwalten von Telefonen in öffentlichen Bereichen und das Verwalten von analogen Geräten.</span><span class="sxs-lookup"><span data-stu-id="2246d-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
      - <span data-ttu-id="2246d-114">**CsAdministrator:** Diese Administratorrolle kann sämtliche Aufgaben ausführen, die mit „CsVoiceAdministrator“ und „CsUserAdministrator“ ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="2246d-114">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="2246d-115">Mit der Delegierung können mehr Administratoren an ihrer lync Server-Bereitstellung teilnehmen, ohne unnötigen Zugriff auf Ressourcen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2246d-115">Delegation enables more administrators to participate in your Lync Server deployment without opening up unnecessary access to resources.</span></span>

    
    </div>

  - <span data-ttu-id="2246d-116">Eine Managed Key-Infrastruktur (MKI) wurde mithilfe einer Zertifizierungsstelleninfrastruktur von Microsoft oder einem Drittanbieter bereitgestellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2246d-116">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="2246d-117">Details zu den Zertifikatanforderungen in lync Server finden Sie unter <A href="lync-server-2013-certificate-infrastructure-requirements.md">Zertifikatsinfrastruktur Anforderungen für lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2246d-117">For details about certificate requirements in Lync Server, see <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="user-configuration"></a><span data-ttu-id="2246d-118">Benutzerkonfiguration</span><span class="sxs-lookup"><span data-stu-id="2246d-118">User Configuration</span></span>

<span data-ttu-id="2246d-119">Wenn Sie den Vermittlungsserver mit jedem Front-End-Pool oder Standard Edition-Server während der Front-End-Bereitstellung zusammengestellt haben, wurden die für Enterprise-VoIP erforderlichen Benutzereinstellungen während der Installation der Dateien für diese Server Rollen automatisch konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2246d-119">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>

<span data-ttu-id="2246d-120">Wenn Sie die Enterprise-VoIP-Arbeitsauslastung zu diesem Zeitpunkt neu bereitstellen, bevor Sie mit dem Bereitstellungsprozess beginnen, legen Sie für jeden Benutzer, den Sie für Enterprise-VoIP aktivieren möchten, eine primäre Telefonnummer fest.</span><span class="sxs-lookup"><span data-stu-id="2246d-120">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="2246d-121">Als Administrator sind Sie dafür verantwortlich, die Eindeutigkeit dieser Nummer sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="2246d-121">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="2246d-122">Vor der Implementierung müssen alle primären Telefonnummern normalisiert (korrekt formatiert) und mithilfe der lync Server-Systemsteuerung in die Eigenschaft des jeweiligen Benutzer- **URI** kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="2246d-122">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user’s **Line URI** property using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2246d-123">Beispiele für primäre Telefonnummern, die für die Bereitstellung von Enterprise-VoIP erforderlich sind, finden Sie im Abschnitt " <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Wählpläne und Normalisierungsregeln" 2013 im</A> Abschnitt " <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Wählpläne und Normalisierungsregeln</A> " in lync Server 2013 in der Planning-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="2246d-123">For examples of primary phone numbers required for Enterprise Voice deployment, see the <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> section of <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="2246d-124">Nächste Schritte: Installieren von Dateien oder Konfigurieren der PSTN-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="2246d-124">Next Steps: Install Files or Configure PSTN Connectivity</span></span>

<span data-ttu-id="2246d-125">Nachdem Sie die Voraussetzungen für Software und Umwelt für Enterprise-VoIP überprüft haben, können Sie die folgenden Inhalte für folgende Zwecke verwenden:</span><span class="sxs-lookup"><span data-stu-id="2246d-125">After verifying software and environmental prerequisites for Enterprise Voice, you can use the following content to either:</span></span>

  - <span data-ttu-id="2246d-126">Installieren Sie den Vermittlungsserver, wie unter [Installieren der Dateien für den Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)beschrieben, aber nur, wenn Sie einen eigenständigen Vermittlungsserver oder-Pool bereitstellen möchten, da Vermittlungsserver als Teil des Front-End-Pools oder des Standard Edition-Server Bereitstellungsprozesses installiert werden, wenn Sie zusammengestellt sind.</span><span class="sxs-lookup"><span data-stu-id="2246d-126">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

  - <span data-ttu-id="2246d-127">Oder beginnen Sie mit der Konfiguration von Einstellungen für die Weiterleitung von Anrufen für Enterprise-VoIP-Benutzer, wie unter [Konfigurieren von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2246d-127">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<span data-ttu-id="2246d-128"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="2246d-128"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

