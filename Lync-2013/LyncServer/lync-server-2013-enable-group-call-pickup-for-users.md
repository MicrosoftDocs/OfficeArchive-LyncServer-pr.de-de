---
title: 'Lync Server 2013: Aktivieren der Gruppenanruf Abholung für Benutzer'
description: 'Lync Server 2013: Aktivieren der Gruppenanruf Abholung für Benutzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27951e9000fd17aac90339cf2a507757ae96a397
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437595"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Aktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Verwenden Sie das SEFAUtil Resource Kit-Tool, um die Gruppenanruf Abholung für Benutzer zu aktivieren. Benutzern muss eine Gruppennummer mit dem Typ GroupPickup in der Orbit-Tabelle des Anruf Parks zugewiesen werden, damit die Gruppenanruf Abholung aktiviert ist. Sie weisen eine Gruppennummer für die Anruf Abholung zu und aktivieren die Gruppenanruf Abholung gleichzeitig mithilfe des/enablegrouppickup-Parameters, wenn Sie SEFAUtil.exe ausführen.

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>So aktivieren Sie die Gruppenanruf Abholung für einen Benutzer

1.  Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.

2.  Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Beispiel:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zuweisen von Gruppenanruf-Abhol Nummern zu Benutzern in lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Deaktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

