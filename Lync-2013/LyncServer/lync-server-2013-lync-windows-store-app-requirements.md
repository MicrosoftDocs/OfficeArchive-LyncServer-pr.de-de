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
# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Lync Windows Store-App-Anforderungen für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-12-03_

Organisationen mit einer lokalen Bereitstellung von lync Server müssen die folgenden Anforderungen erfüllen, um die lync Windows Store-App zu unterstützen.

<div>


> [!NOTE]  
> Führen Sie für lync Server 2010 das kumulative Update für lync Server 2010: Februar 2012 (verfügbar unter <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2670352</A>) oder höher auf allen Servern aus. Damit Benutzer an Besprechungen teilnehmen können, führen Sie das kumulative Update für lync Server 2010: Oktober 2012 (verfügbar unter <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2737915</A>) auf den Servern aus.



</div>

  - Aktivieren Sie die AutoErmittlung, lync Web App und Web Ticket-Dienste auf dem Server.

  - Aktivieren Sie die Zertifikatauthentifizierung auf dem Front-End-Server oder im Front-End-Pool. (Der Benutzerregistrierungsprozess auf dem Front-End-Server oder im Front-End-Pool wird häufig als Registrar bezeichnet.) Ausführliche Informationen finden Sie unter Erstellen von Registrierungsstellen- [Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

  - Veröffentlichen Sie die DNS-Aliasressourceneinträge (CNAME) für den AutoErmittlungsdienst.

  - Es ist nicht mehr erforderlich, sicherzustellen, dass der CRL-Verteilungspunkt (Certificate Revocation List, CRL) für die für lync Server ausgestellten Zertifikate auf eine HTTP-Ressource anstatt auf eine LDAP-Ressource verweist. Stellen Sie jedoch sicher, dass auf den Clientcomputern die neuesten Windows-Updates installiert sind.

  - Konfigurieren Sie HTTP-Proxys im Unternehmen, um den lync Server-bezogenen HTTP-Datenverkehr zu ermöglichen.  Fügen Sie bei Bedarf Ausnahmen für die AutoErmittlung, lync Web App und WebTICKET-Dienste hinzu.

  - Installieren Sie auf Clients Windows 8,1 und die neueste Version der lync Windows Store-App, um ein Anmeldeproblem zu beheben, das im Allgemeinen bei der Verwendung mehrerer Domänen auftritt (beispielsweise, wenn der SIP-URI **UserA@domainZ.com** ist, der Edgeserver aber **SIP.domainX.com** ist).

Wenn Ihre Organisation lync Online oder Microsoft 365 abonniert und Sie Ihren eigenen Domänennamen verwenden, müssen Sie einige zusätzliche Schritte ausführen, um Ihr Netzwerk für die AutoDiscovery der lync-Server einzurichten. Die Anforderungen an die Netzwerkkonfiguration sind für die lync Windows Store-App und lync auf mobilen Geräten identisch.

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen der lync Windows Store-App in lync Server 2013](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
