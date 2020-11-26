---
title: 'Lync Server 2013: Unterstützung der Zertifikatinfrastruktur'
description: Unterstützung für die lync Server 2013-Zertifikatinfrastruktur.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc08719e5b1c58a4dc3c1cab07db5e9842d46d5c
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49435404"
---
# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="2e097-103">Unterstützung der Zertifikatinfrastruktur in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e097-103">Certificate infrastructure support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="2e097-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="2e097-104">

<span> </span></span></span>

<span data-ttu-id="2e097-105">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="2e097-105">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="2e097-106">Lync Server 2013 erfordert eine Public Key-Infrastruktur (PKI) zur Unterstützung von Transport Layer Security (TLS)-und MTLS-Verbindungen (Mutual TLS).</span><span class="sxs-lookup"><span data-stu-id="2e097-106">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="2e097-107">Standardmäßig ist lync Server 2013 für die Verwendung von TLS für Client-zu-Server-Verbindungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2e097-107">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="2e097-108">MTLS wird für Verbindungen zwischen Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e097-108">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="2e097-109">MTLS-Zertifikate müssen von vertrauenswürdigen Zertifizierungsstellen (CAS) für lync Server 2013 ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2e097-109">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="2e097-110">Lync Server unterstützt Zertifikate, die von den folgenden CAS ausgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="2e097-110">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="2e097-111">Zertifikate, die von einer internen Zertifizierungsstelle ausgestellt wurden:</span><span class="sxs-lookup"><span data-stu-id="2e097-111">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="2e097-112">Die Windows Server 2003-Betriebssystem Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="2e097-112">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="2e097-113">Die Windows Server 2008-Betriebssystem Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="2e097-113">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="2e097-114">Die Windows Server 2008 R2-Betriebssystem Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="2e097-114">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="2e097-115">Die Windows Server 2012-Betriebssystem Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="2e097-115">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="2e097-116">Die Windows Server 2012 R2-Betriebssystem Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="2e097-116">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="2e097-117">Zertifikate, die von einer öffentlichen Zertifizierungsstelle ausgestellt wurden</span><span class="sxs-lookup"><span data-stu-id="2e097-117">Certificates issued from a public CA</span></span>

<span data-ttu-id="2e097-118">Die Kommunikation mit anderen Anwendungen und Servern, wie etwa Exchange 2013, erfordert ein Zertifikat, das von den anderen Anwendungen und Produkten unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="2e097-118">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="2e097-119">Für die 2013-Version unterstützen lync Server 2013 und andere Microsoft-Serverprodukte, einschließlich Exchange 2013 und SharePoint Server, das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="2e097-119">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="2e097-120">Ausführliche Informationen finden Sie unter [Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2e097-120">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="2e097-121">Für Verbindungen von Clients unter dem BetriebssystemWindows 7, Windows Server 2008 R2 und Microsoft Office Communicator 2007 Phone Edition umfasst lync Server 2013 Unterstützung für (aber nicht erforderlich) Zertifikate, die mit der SHA-256-kryptografischen Hashfunktion signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2e097-121">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="2e097-122">Um den externen Zugriff mithilfe von SHA-256 zu unterstützen, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle mithilfe von SHA-256 ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="2e097-122">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="2e097-123">Details zu den Zertifikatanforderungen finden Sie unter [Zertifikatsinfrastruktur Anforderungen für lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2e097-123">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="2e097-124">Ausführliche Informationen zur Verwendung von Platzhaltern mit Zertifikaten finden Sie unter Unterstützung für [Platzhalterzertifikate in lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="2e097-124">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="2e097-125"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="2e097-125"></div>

<span> </span>

</div>

</div>

</span></span></div>

