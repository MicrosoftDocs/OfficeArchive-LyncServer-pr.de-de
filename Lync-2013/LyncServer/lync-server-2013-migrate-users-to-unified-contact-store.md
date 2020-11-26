---
title: 'Lync Server 2013: Migrieren von Benutzern zum einheitlichen Kontaktspeicher'
description: 'Lync Server 2013: Migrieren von Benutzern zu einem einheitlichen Kontaktspeicher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e9ee9850cc723ae132f15d7c0c6b3769e1240ba
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425591"
---
# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>Migrieren von Benutzern zum einheitlichen Kontaktspeicher in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-15_

Die Kontakte eines Benutzers werden automatisch auf den Exchange 2013-Server migriert, wenn der Benutzer:

  - Dem Benutzer muss eine Benutzerdienstrichtlinie zugewiesen worden sein, für die die Option „UcsAllowed“ auf „True“ gesetzt ist.

  - Wurde mit einem Exchange 2013-Postfach bereitgestellt und hat sich mindestens einmal beim Postfach angemeldet.

  - Meldet sich mit einem Rich-Client mit lync 2013 an.

Wenn sich der Benutzer mit einem lync 2010-oder früheren Client anmeldet oder wenn der Benutzer nicht mit einem Exchange 2013-Server verbunden ist, wird die Richtlinie für Benutzer Dienste ignoriert, und die Kontakte des Benutzers verbleiben in lync Server.

Verwenden Sie eine der folgenden Methoden, um zu ermitteln, ob die Kontakte eines Benutzers migriert wurden:

  - Überprüfen Sie den folgenden Registrierungsschlüssel auf dem Clientcomputer:
    
    HKEY- \_ aktuelle \_ Benutzer \\ Software \\ Microsoft \\ Office \\ 15,0 \\ lync \\ \<SIP URL\> \\ UCS
    
    Wenn die Kontakte des Benutzers in Exchange 2013 gespeichert sind, enthält dieser Schlüssel den Wert InUCSMode mit dem Wert 2165.

  - Führen Sie das Cmdlet **Test-CsUnifiedContactStore** aus. Geben Sie in der Befehlszeile der lync Server-Verwaltungsshell Folgendes ein:
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    Wenn **Test-CsUnifiedContactStore** erfolgreich ist, wurden die Kontakte des Benutzers zum einheitlichen Kontaktspeicher migriert.

</div>

<span> </span>

</div>

</div>

</div>

