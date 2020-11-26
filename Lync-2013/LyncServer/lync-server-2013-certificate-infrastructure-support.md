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
# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Unterstützung der Zertifikatinfrastruktur in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

Lync Server 2013 erfordert eine Public Key-Infrastruktur (PKI) zur Unterstützung von Transport Layer Security (TLS)-und MTLS-Verbindungen (Mutual TLS). Standardmäßig ist lync Server 2013 für die Verwendung von TLS für Client-zu-Server-Verbindungen konfiguriert. MTLS wird für Verbindungen zwischen Servern verwendet.

MTLS-Zertifikate müssen von vertrauenswürdigen Zertifizierungsstellen (CAS) für lync Server 2013 ausgestellt werden. Lync Server unterstützt Zertifikate, die von den folgenden CAS ausgestellt werden:

  - Zertifikate, die von einer internen Zertifizierungsstelle ausgestellt wurden:
    
      - Die Windows Server 2003-Betriebssystem Zertifizierungsstelle
    
      - Die Windows Server 2008-Betriebssystem Zertifizierungsstelle
    
      - Die Windows Server 2008 R2-Betriebssystem Zertifizierungsstelle
    
      - Die Windows Server 2012-Betriebssystem Zertifizierungsstelle
    
      - Die Windows Server 2012 R2-Betriebssystem Zertifizierungsstelle

  - Zertifikate, die von einer öffentlichen Zertifizierungsstelle ausgestellt wurden

Die Kommunikation mit anderen Anwendungen und Servern, wie etwa Exchange 2013, erfordert ein Zertifikat, das von den anderen Anwendungen und Produkten unterstützt wird. Für die 2013-Version unterstützen lync Server 2013 und andere Microsoft-Serverprodukte, einschließlich Exchange 2013 und SharePoint Server, das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung. Ausführliche Informationen finden Sie unter [Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

Für Verbindungen von Clients unter dem BetriebssystemWindows 7, Windows Server 2008 R2 und Microsoft Office Communicator 2007 Phone Edition umfasst lync Server 2013 Unterstützung für (aber nicht erforderlich) Zertifikate, die mit der SHA-256-kryptografischen Hashfunktion signiert wurden. Um den externen Zugriff mithilfe von SHA-256 zu unterstützen, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle mithilfe von SHA-256 ausgestellt.

Details zu den Zertifikatanforderungen finden Sie unter [Zertifikatsinfrastruktur Anforderungen für lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Platzhaltern mit Zertifikaten finden Sie unter Unterstützung für [Platzhalterzertifikate in lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in der Dokumentation zur Unterstützung.

</div>

<span> </span>

</div>

</div>

</div>

