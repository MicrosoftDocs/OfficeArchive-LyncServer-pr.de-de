---
title: 'Lync Server 2013: Entfernen der Kerberos-Authentifizierung aus einem Standort'
description: 'Lync Server 2013: Entfernen der Kerberos-Authentifizierung von einer Website.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a3d9100d07d37e98800cfce106bc75fcfaeaa59
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49436384"
---
# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>Entfernen der Kerberos-Authentifizierung aus einem Standort in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-01-16_

Um dieses Verfahren erfolgreich abzuschließen, sollten Sie als Benutzer angemeldet sein, der Mitglied der RTCUniversalServerAdmins-Gruppe ist.

Wenn Sie die Kerberos-Authentifizierung von einer Website entfernen oder eine Website zurückziehen müssen, müssen Sie die Kerberos-Authentifizierungs Konto Zuweisung von der Website mithilfe des Cmdlets **Remove-CsKerberosAccountAssignment** entfernen. Gehen Sie wie folgt vor, um die Kerberos-Authentifizierungs Kontozuordnung zu entfernen, wodurch die Zuordnung von allen Computern auf der Website entfernt wird.

<div class=" ">


> [!WARNING]  
> Wenn Sie das Kerberos-fähige Konto endgültig zurückziehen, sollten Sie Active Directory-Benutzer und-Computer verwenden, um es aus Active Directory-Domänendiensten zu löschen, nachdem Sie die Aufgabe entfernt haben. Wenn Sie beabsichtigen, das Objekt in Zukunft zu verwenden, sollten Sie das Active Directory-Objekt behalten.



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>So entfernen Sie die Kerberos-Authentifizierung von einer Website

1.  Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe an einem Computer in der Domäne mit lync Server 2013 oder auf einem Computer an, auf dem die Verwaltungstools installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie in der Befehlszeile die beiden folgenden Befehle aus:
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    Beispiel:
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Nachdem Sie die Kerberos-Authentifizierung geändert haben, beispielsweise ein Konto hinzugefügt oder ein Konto entfernt haben, müssen Sie <STRONG>enable-CsTopology</STRONG> über die Eingabeaufforderung der lync Server-Verwaltungsshell ausführen.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

