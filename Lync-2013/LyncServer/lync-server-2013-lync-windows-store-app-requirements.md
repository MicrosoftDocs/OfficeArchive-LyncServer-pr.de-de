---
title: 'Lync Server 2013: Anforderungen der lync Windows Store-App'
description: 'Lync Server 2013: lync Windows Store-App-Anforderungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17e8705a55625bcf0ad099ead1000a82c994d867
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49426167"
---
# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="f9477-103">Lync Windows Store-App-Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9477-103">Lync Windows Store app requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="f9477-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="f9477-104">

<span> </span></span></span>

<span data-ttu-id="f9477-105">_**Letztes Änderungsdatum des Themas:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="f9477-105">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="f9477-106">Organisationen mit einer lokalen Bereitstellung von lync Server müssen die folgenden Anforderungen erfüllen, um die lync Windows Store-App zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f9477-106">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9477-107">Führen Sie für lync Server 2010 das kumulative Update für lync Server 2010: Februar 2012 (verfügbar unter <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2670352</A>) oder höher auf allen Servern aus.</span><span class="sxs-lookup"><span data-stu-id="f9477-107">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="f9477-108">Damit Benutzer an Besprechungen teilnehmen können, führen Sie das kumulative Update für lync Server 2010: Oktober 2012 (verfügbar unter <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2737915</A>) auf den Servern aus.</span><span class="sxs-lookup"><span data-stu-id="f9477-108">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="f9477-109">Aktivieren Sie die AutoErmittlung, lync Web App und Web Ticket-Dienste auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="f9477-109">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="f9477-110">Aktivieren Sie die Zertifikatauthentifizierung auf dem Front-End-Server oder im Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="f9477-110">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="f9477-111">(Der Benutzerregistrierungsprozess auf dem Front-End-Server oder im Front-End-Pool wird häufig als Registrar bezeichnet.) Ausführliche Informationen finden Sie unter Erstellen von Registrierungsstellen- [Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f9477-111">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="f9477-112">Veröffentlichen Sie die DNS-Aliasressourceneinträge (CNAME) für den AutoErmittlungsdienst.</span><span class="sxs-lookup"><span data-stu-id="f9477-112">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="f9477-113">Es ist nicht mehr erforderlich, sicherzustellen, dass der CRL-Verteilungspunkt (Certificate Revocation List, CRL) für die für lync Server ausgestellten Zertifikate auf eine HTTP-Ressource anstatt auf eine LDAP-Ressource verweist.</span><span class="sxs-lookup"><span data-stu-id="f9477-113">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="f9477-114">Stellen Sie jedoch sicher, dass auf den Clientcomputern die neuesten Windows-Updates installiert sind.</span><span class="sxs-lookup"><span data-stu-id="f9477-114">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="f9477-115">Konfigurieren Sie HTTP-Proxys im Unternehmen, um den lync Server-bezogenen HTTP-Datenverkehr zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f9477-115">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span>  <span data-ttu-id="f9477-116">Fügen Sie bei Bedarf Ausnahmen für die AutoErmittlung, lync Web App und WebTICKET-Dienste hinzu.</span><span class="sxs-lookup"><span data-stu-id="f9477-116">Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="f9477-117">Installieren Sie auf Clients Windows 8,1 und die neueste Version der lync Windows Store-App, um ein Anmeldeproblem zu beheben, das im Allgemeinen bei der Verwendung mehrerer Domänen auftritt (beispielsweise, wenn der SIP-URI **UserA@domainZ.com** ist, der Edgeserver aber **SIP.domainX.com** ist).</span><span class="sxs-lookup"><span data-stu-id="f9477-117">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="f9477-118">Wenn Ihre Organisation lync Online oder Microsoft 365 abonniert und Sie Ihren eigenen Domänennamen verwenden, müssen Sie einige zusätzliche Schritte ausführen, um Ihr Netzwerk für die AutoDiscovery der lync-Server einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f9477-118">If your organization subscribes to Lync Online or Microsoft 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="f9477-119">Die Anforderungen an die Netzwerkkonfiguration sind für die lync Windows Store-App und lync auf mobilen Geräten identisch.</span><span class="sxs-lookup"><span data-stu-id="f9477-119">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f9477-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9477-120">See Also</span></span>


[<span data-ttu-id="f9477-121">Bereitstellen der lync Windows Store-App in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9477-121">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

<span data-ttu-id="f9477-122"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="f9477-122"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>
