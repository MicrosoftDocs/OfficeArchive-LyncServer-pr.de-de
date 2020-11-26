---
title: Aktualisieren von DNS SRV-Einträgen
description: Aktualisieren von DNS-SRV-Einträgen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24161074e8f3bcf7e296a957588eeb59d5f2ad1b
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49446549"
---
# <a name="update-dns-srv-records"></a>Aktualisieren von DNS SRV-Einträgen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie als Mitglied der Gruppe Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe am Server oder in der Domäne angemeldet sein.

In diesem Thema wird beschrieben, wie Sie die DNS-Einträge (Domain Name System) nach der Migration zu lync Server 2013 aktualisieren. Nachdem alle Benutzer nach lync Server 2013 verschoben wurden, aber bevor der Legacy lync Server 2010-Pool oder-Director außer Betrieb genommen wird, müssen Sie die DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne aktualisieren. Bei diesem Verfahren wird davon ausgegangen, dass Ihr interner DNS Zonen für Ihre SIP-Benutzerdomänen aufweist.

**So konfigurieren Sie einen DNS-SRV-Eintrag**

1.  Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.

2.  Erweitern Sie in der Konsolenstruktur ihrer SIP-Domäne **Forward-Lookupzonen**, erweitern Sie die SIP-Domäne, in der lync Server 2013 installiert ist, und navigieren Sie zur **\_ TCP** -Einstellung.

3.  Klicken Sie im rechten Bereich mit der rechten Maustaste auf **\_ sipinternaltls** , und wählen Sie **Eigenschaften** aus.

4.  Aktualisieren Sie im Host, der **diesen Dienst anbietet**, den FQDN des Hosts so, dass er auf den lync Server 2013-Pool verweist.

5.  Klicken Sie auf **OK**.

**So überprüfen Sie, ob der FQDN des Front-End-Pools oder des Standard Edition-Servers aufgelöst werden kann**

1.  Melden Sie sich bei einem Clientcomputer in der Domäne an.

2.  Klicken Sie auf  **Start** und dann auf  **Ausführen**.

3.  Geben Sie im Feld **Öffnen** den **Befehl cmd** ein, und klicken Sie dann auf **OK**.

4.  Geben Sie an der Eingabeaufforderung **nslookup** \<FQDN of the Front End pool\> oder \<FQDN of the Standard Edition server\> ein, und drücken Sie dann die EINGABETASTE.

5.  Überprüfen Sie, ob Sie eine Antwort erhalten, die in die entsprechende IP-Adresse für den FQDN aufgelöst wird.

</div>

<span> </span>

</div>

</div>

</div>

