---
title: Überprüfen der Office Communications Server 2007 R2-Umgebung
description: Überprüfen Sie die Office Communications Server 2007 R2-Umgebung.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb200941b3a35ece2b587bcfc89be743c9960d1f
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49443639"
---
# <a name="verify-office-communications-server-2007-r2-environment"></a>Überprüfen der Office Communications Server 2007 R2-Umgebung

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-16_

Bevor Sie lync Server 2013 in einem koexistenzstatus mit Office Communications Server 2007 R2 bereitstellen, müssen Sie überprüfen, ob die Office Communications Server 2007 R2-Dienste konfiguriert und gestartet sind.

**Überprüfen, ob der Pool mit dem Office Communications Server 2007 R2-Verwaltungs Tool gestartet wurde**

1.  Öffnen Sie das Office Communications Server 2007 R2-Verwaltungstool.

2.  Erweitern Sie den Knoten **Gesamtstruktur** , erweitern Sie den Knoten **Standard Edition-Server** oder **Enterprise-Pools** , und erweitern Sie dann den Pool-oder Servernamen.

3.  Stellen Sie sicher, dass die Dienste auf dem Standard Edition-Server oder Enterprise-Pool ausgeführt werden.
    
    ![Office Communications Server 2007 R2-Verwaltungskonsole](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2-Verwaltungskonsole")

**Überprüfen der Benutzer, die für Office Communications Server 2007 R2 konfiguriert sind**

1.  Öffnen Sie das Office Communications Server 2007 R2-Verwaltungstool.

2.  Erweitern Sie den Knoten **Gesamtstruktur** , erweitern Sie den Knoten **Standard Edition-Server** oder **Enterprise-Pools** , und erweitern Sie dann den Pool-oder Servernamen.

3.  Klicken Sie auf **Benutzer**.

4.  Überprüfen Sie die Liste der Benutzer von Office Communications Server 2007 R2.
    
    ![Liste FO-Benutzer im OCS-Administrator Tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Liste FO-Benutzer im OCS-Administrator Tool")

**Überprüfen der Konfiguration von Legacy-XMPP-Verbundpartnern**

1.  Navigieren Sie vom Legacy-XMPP-Server zum Applet Dienste für Verwaltungs Tools \\ .

2.  Überprüfen Sie, ob der Office Communications Server-XMPP-Gatewayserver gestartet wurde.
    
    ![Office Communications Server-XMPP-Gatewaydienst](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server-XMPP-Gatewaydienst")

</div>

<span> </span>

</div>

</div>

</div>

