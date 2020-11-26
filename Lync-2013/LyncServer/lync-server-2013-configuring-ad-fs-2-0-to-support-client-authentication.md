---
title: 'Lync Server 2013: Konfigurieren von AD FS 2,0 zur Unterstützung der Clientauthentifizierung'
description: 'Lync Server 2013: Konfigurieren von AD FS 2,0 zur Unterstützung der Clientauthentifizierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156eb6d7e8af85dec04601ab8f88c55181db20d5
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433395"
---
# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Konfigurieren von AD FS 2,0 zur Unterstützung der Clientauthentifizierung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-03_

Es gibt zwei mögliche Authentifizierungstypen, die so konfiguriert werden können, dass AD FS 2.0 Authentifizierung über Smartcards unterstützen kann:

  - Formularbasierte Authentifizierung (FBA)

  - Transport Layer Security-Clientauthentifizierung

Wenn Sie formularbasierte Authentifizierung verwenden, können Sie eine Webseite entwickeln, die es Benutzern ermöglicht, sich entweder mit der Kombination aus Benutzername und Kennwort oder mit Smartcard und PIN zu authentifizieren. Im vorliegenden Thema wird beschrieben, wie Transport Layer Security-Clientauthentifizierung mit AD FS 2.0 implementiert wird. Weitere Informationen zu den AD FS 2,0-Authentifizierungstypen finden Sie unter AD FS 2,0: Ändern des lokalen Authentifizierungstyps unter [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384) .

<div>


**So konfigurieren Sie AD FS 2.0, sodass Clientauthentifizierung unterstützt wird**

1.  Melden Sie sich beim AD FS 2.0-Computer über ein Domänenadministratorkonto an.

2.  Starten Sie Windows-Explorer.

3.  Navigieren Sie zu C: \\ Inetpub \\ ADFS \\ ls

4.  Erstellen Sie eine Sicherungskopie von der vorhandenen Datei „web.config“.

5.  Öffnen Sie die vorhandene Datei „web.config“ im Editor.

6.  Wählen Sie in der Menüleiste das Menü **Bearbeiten** und anschließend **Suchen** aus.

7.  Suchen nach **\<localAuthenticationTypes\>** .
    
    Es werden vier Authentifizierungstypen aufgelistet (je ein Typ pro Zeile).

8.  Verschieben Sie die Zeile, die den Authentifizierungstyp „TLSClient“ enthält, an den Anfang der Liste im Abschnitt.

9.  Speichern Sie die Datei „web.config“ und beenden Sie den Editor.

10. Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.

11. Starten Sie IIS neu, indem Sie folgenden Befehl ausführen:
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

