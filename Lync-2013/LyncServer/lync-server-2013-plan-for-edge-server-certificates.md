---
title: 'Lync Server 2013: Planen von Edgeserver-Zertifikaten'
description: 'Lync Server 2013: Planen von Edgeserver-Zertifikaten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22ec3743256fe3e4c55dba0f6357a85b1ad81cd0
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437136"
---
# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="69551-103">Planen von Edgeserver-Zertifikaten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69551-103">Plan for Edge Server certificates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="69551-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="69551-104">

<span> </span></span></span>

<span data-ttu-id="69551-105">_**Letztes Änderungsdatum des Themas:** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="69551-105">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="69551-106">Die Zertifikaterstellung für Edge wird in lync Server 2013 vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="69551-106">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="69551-107">**Flussdiagramm für Zertifikate für Edgeserver**</span><span class="sxs-lookup"><span data-stu-id="69551-107">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="69551-108">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="69551-108">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="69551-109">Erstellen Sie ein einzelnes öffentliches Zertifikat, stellen Sie sicher, dass für das Zertifikat ein exportierbarer privater Schlüssel definiert ist, und weisen Sie ihn mithilfe des Zertifikat-Assistenten den folgenden Edge-Server-externen Schnittstellen zu:</span><span class="sxs-lookup"><span data-stu-id="69551-109">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="69551-110">Platzhalterzertifikate werden in lync Server nicht unterstützt, es sei denn, es wird verwendet, um die einfachen URLs über den Reverse-Proxy zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="69551-110">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="69551-111">Sie müssen für jeden SIP-Domänennamen, Webkonferenz-Edgedienst, A/V-Edgedienst und die von Ihrer Bereitstellung angebotene XMPP-Domäne eindeutige Subject Alternate Names (SANs) definieren.</span><span class="sxs-lookup"><span data-stu-id="69551-111">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="69551-112">In lync Server 2013 eingeführt, erfordert das Staging von Audio/Video-Authentifizierungszertifikaten im Vorfeld der Ablaufzeit des aktuellen Zertifikats einige zusätzliche Planungsschritte.</span><span class="sxs-lookup"><span data-stu-id="69551-112">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="69551-113">Anstelle eines Zertifikats mit mehreren Zwecken für die externe Edge-Schnittstelle benötigen Sie zwei Zertifikate, eine dem Access Edge-Dienst und dem Webkonferenz-Edgedienst zugewiesene Zertifikate sowie ein Zertifikat für den A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="69551-113">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="69551-114">Weitere Informationen finden Sie unter <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging von AV-und OAuth-Zertifikaten in lync Server 2013 using-Rolle in der Gruppe-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="69551-114">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="69551-115">Im Fall eines Pools von Edgeserver exportieren Sie das Zertifikat mit dem privaten Schlüssel zu jedem Edgeserver, und weisen Sie das Zertifikat jedem Edgeserver-Dienst zu.</span><span class="sxs-lookup"><span data-stu-id="69551-115">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="69551-116">Führen Sie dasselbe für das interne Edgeserver-Zertifikat aus, exportieren Sie das Zertifikat mit dem privaten Schlüssel, und weisen Sie jeder internen Schnittstelleeine Zuordnung zu.</span><span class="sxs-lookup"><span data-stu-id="69551-116">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="69551-117">Stellen Sie sicher, dass für das Zertifikat ein exportierbarer privater Schlüssel zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="69551-117">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="69551-118">Access-Edgedienst (als **SIP-Access-Edge extern** im Zertifikat-Assistenten bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="69551-118">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="69551-119">Webkonferenz-Edgedienst (wird als **Webkonferenz Edge extern** im Zertifikat-Assistenten bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="69551-119">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="69551-120">A/v-Authentifizierungsdienst (im Zertifikat-Assistenten als **extern** bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="69551-120">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="69551-121">Erstellen Sie ein einzelnes internes Zertifikat mit exportier barem privaten Schlüssel, kopieren Sie es, und weisen Sie es jeder der Edge-Server-internen Schnittstellen zu:</span><span class="sxs-lookup"><span data-stu-id="69551-121">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="69551-122">Edgeserver (im Zertifikat-Assistenten als " **Edge-intern** " bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="69551-122">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="69551-123">Es ist möglich, getrennte und unterschiedliche Zertifikate für jeden Edgeserver-Dienst zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="69551-123">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="69551-124">Ein guter Grund, getrennte Zertifikate zu wählen, ist, wenn Sie das neue Feature für das parallele Zertifikat für das A/V-Edgedienst Zertifikat verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="69551-124">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="69551-125">Im Fall dieser Funktion empfiehlt es sich, das A/V-Edgedienst-Zertifikat vom Edgedienst für den Access-Edgedienst und dem Webkonferenz-Edgedienst zu entkoppeln.</span><span class="sxs-lookup"><span data-stu-id="69551-125">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="69551-126">Wenn Sie sich entscheiden, für jeden Dienst separate Zertifikate anzufordern, zu erwerben und zuzuweisen, müssen Sie anfordern, dass der private Schlüssel für den a/v-Edgedienst exportierbar ist (Dies ist wiederum der a/v-Authentifizierungsdienst), und weisen Sie dem a/v-Edge-externen Interface auf jedem Edgeserver dasselbe Zertifikat zu.</span><span class="sxs-lookup"><span data-stu-id="69551-126">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="69551-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69551-127">See Also</span></span>


[<span data-ttu-id="69551-128">Staging von AV-und OAuth-Zertifikaten in lync Server 2013 using-Rolle in der Gruppe-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="69551-128">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="69551-129">Änderungen in Lync Server 2013, die die Planung für Edgeserver betreffen</span><span class="sxs-lookup"><span data-stu-id="69551-129">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

<span data-ttu-id="69551-130"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="69551-130"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

