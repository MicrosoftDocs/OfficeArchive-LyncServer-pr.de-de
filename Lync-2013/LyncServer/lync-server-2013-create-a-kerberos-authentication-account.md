---
title: 'Lync Server 2013: Erstellen eines Kerberos-Authentifizierungskontos'
description: 'Lync Server 2013: Erstellen eines Kerberos-Authentifizierungs Kontos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f8e87a8ffcc95af4a44e516ac4e1f4d635d737
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432177"
---
# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Erstellen eines Kerberos-Authentifizierungskontos in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-01-02_

Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie am Server oder in der Domäne minimal als Mitglied der Gruppe "Domänen-Admins" angemeldet sein.

Sie können für jede Website Kerberos-Authentifizierungs Konten erstellen, oder Sie können ein einzelnes Kerberos-Authentifizierungs Konto erstellen und für alle Websites verwenden. Sie verwenden Windows PowerShell-Cmdlets zum Erstellen und Verwalten der Konten, einschließlich der Ermittlung der Konten, die den einzelnen Websites zugewiesen sind. Der Topologie-Generator und die lync Server 2013-Systemsteuerung zeigen keine Kerberos-Authentifizierungs Konten an. Gehen Sie wie folgt vor, um ein oder mehrere Benutzerkonten zu erstellen, die für die Kerberos-Authentifizierung verwendet werden sollen.

<div>

## <a name="to-create-a-kerberos-account"></a>So erstellen Sie ein Kerberos-Konto

1.  Melden Sie sich als Mitglied der Gruppe Domänenadministratoren bei einem Computer in der Domäne mit lync Server 2013 oder auf einem Computer an, auf dem die Verwaltungstools installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie in der Befehlszeile den folgenden Befehl aus:
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Beispiel:
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Vergewissern Sie sich, dass das Computerobjekt erstellt wurde, indem Sie Active Directory-Benutzer und-Computer öffnen, den Container **Benutzer** erweitern und dann bestätigen, dass sich das Computerobjekt für das Benutzerkonto im Container befindet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

