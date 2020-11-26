---
title: 'Lync Server 2013: IP- und Netzwerkprotokollunterstützung'
description: 'Lync Server 2013: Unterstützung für IP-und Netzwerkprotokoll.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbd8022dd7197524334e0c70ea0ad875a30446de
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49426746"
---
# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>IP- und Netzwerkprotokollunterstützung in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Lync Server 2013 unterstützt die folgenden IP-und Netzwerkprotokolle:

  - **IP-Protokolle.**   Lync Server 2013 unterstützt entweder IP Version 4 (IPv4) oder IP Version 6 (IPv6) für das Server Netzwerk.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 kann in einem Netzwerk mit aktiviertem Dual IP Stack funktionieren.

    
    </div>

  - **SIP-Transport Protokolle.**   Im Allgemeinen kann SIP mindestens drei Transporttypen verwenden: User Datagram Protocol (UDP), Transmission Control Protocol (TCP) und Transport Layer Security (TLS). In der standardmäßigen SIP-Transportkonfiguration wird TLS über TCP ausgeführt. TLS wird im lync Server 2013-Netzwerk verwendet. Am Rand des Netzwerks kann lync Server 2013 über TCP interagieren. Lync Server 2013 unterstützt UDP für den SIP-Transport nicht, da es die Mindestanforderungen für die Sicherheit, Zuverlässigkeit und Skalierbarkeit von Unternehmenskommunikation nicht erfüllt. Ausführliche Informationen finden Sie im NextHop-Blog Artikel "zu UDP oder nicht zu UDP, das ist die Frage" [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369) .
    
    <div>
    

    > [!NOTE]  
    > Die Inhalte der Blogs und die zugehörige URL können ohne vorherige Ankündigung geändert werden.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

