---
title: Migrieren eines XMPP-Partnerverbunds
description: Migrieren von XMPP-Föderation
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e63c9f6fd3f1c1d45de77c27417987505678f74b
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49440360"
---
# <a name="migrating-xmpp-federation"></a>Migrieren eines XMPP-Partnerverbunds

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

In früheren Versionen von lync Server und Office Communications Server wurde ein Extensible Messaging and Presence Protocol (XMPP)-Gateway bereitgestellt, das als separate Server Rolle bereitgestellt werden kann, um die Föderation mit XMPP-Bereitstellungen zu ermöglichen. In lync Server 2013 kann die XMPP-Funktion als Feature bereitgestellt werden. Die XMPP-Funktionalität ist in zwei Teilen installiert: als XMPP-Proxy, der auf dem lync Server 2013-Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem lync Server 2013-Front-End-Server ausgeführt wird.

Aus Sicht der Migration kann ein lync Server-Benutzerkonto in einen lync Server 2013-Pool verschoben und weiterhin das Legacy-XMPP-Gateway verwendet werden. Dies ist nur möglich, wenn der XMPP-Verbundpartner nicht in lync Server 2013 konfiguriert ist.

Zusammenfassung: Wenn lync Server 2010 mit dem Office Communications Server 2007 R2 XMPP-Gateway bereitgestellt wurde und die XMPP-Föderation für Legacy-lync Server 2010-Benutzer aktiviert wurde, können Sie die XMPP-Föderation zu lync Server 2013 migrieren:

1.  Bereitstellen eines lync Server 2013-Pools

2.  Bereitstellen eines lync Server 2013-Edgeserver

3.  Verschieben aller Benutzer in den lync Server 2013-Pool

4.  Erstellen Sie XMPP-Zugriffsrichtlinien und-Zertifikate für den Edgeserver.

5.  Aktivieren Sie die XMPP-Föderation in lync Server 2013. 

6.  Aktualisieren Sie die DNS-Einträge so, dass Sie auf das lync Server 2013 XMPP-Gateway verweisen.

</div>

<span> </span>

</div>

</div>

</div>

