---
title: Aktivieren von Exchange 2013 Outlook Web App und Chat Integration
description: Aktivieren von Exchange 2013 Outlook Web App und Chat Integration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7fd6e8600f255d6ac4dde52487776cdb5fe1a51
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394027"
---
# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Aktivieren von Exchange 2013 Outlook Web App und Chat Integration

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Wenn Sie die Integration von Exchange 2013 Outlook Web Access (OWA) und Instant Messaging (im) in lync Server 2013 aktivieren möchten, müssen Sie den Exchange 2013-Client Zugriffsserver (CAS) zur lync Server 2013-Topologie als vertrauenswürdigen Anwendungsserver hinzufügen.

<div>

## <a name="to-create-a-trusted-application-pool"></a>So erstellen Sie einen vertrauenswürdigen Anwendungspool

1.  Starten Sie die lync Server 2013-Verwaltungsshell.

2.  Führen Sie das folgende Cmdlet aus:
    
        Get-CsSite
    
    Dadurch wird die Website-Nr für den Sitename zurückgegeben, in dem Sie den Pool erstellen. Ausführliche Informationen finden Sie unter [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in der lync Server 2013-Verwaltungsshell.

3.  Führen Sie das folgende Cmdlet aus:
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Ausführliche Informationen finden Sie unter [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in der lync Server 2013-Verwaltungsshell.
    
    Der Exchange Server-FQDN sollte als Exchange-OWA-Zertifikatantragstellername (SN) oder als alternativer Name (Subject Alternate Name, San) konfiguriert sein.
    
    Überprüfen Sie in Exchange OWA, ob der FQDN des Pools ebenfalls vertrauenswürdig ist.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn sich der CAS-Server <EM>nicht</EM> auf demselben Server befindet, auf dem Exchange 2013 Unified Messaging (um) ausgeführt wird, überspringen Sie die verbleibenden Schritte in diesem Verfahren, und führen Sie das Verfahren "Erstellen einer vertrauenswürdigen Anwendung für den Exchange 2013-CAS-Server" weiter unten in diesem Thema aus. Wenn sich der CAS-Server auf demselben Server befindet, auf dem Exchange 2013 Unified Messaging (um) ausgeführt wird, führen Sie die Schritte in diesem Verfahren aus, und führen Sie das Verfahren zum Erstellen einer vertrauenswürdigen Anwendung für den Exchange 2013-CAS-Server weiter unten in diesem Thema aus.

    
    </div>

4.  Führen Sie **enable-CsTopology** aus.

5.  Öffnen Sie den Topologie-Generator, und laden Sie die vorhandene Topologie herunter.

6.  Erweitern Sie im linken Bereich die Struktur, bis Sie **Vertrauenswürdige Anwendungsserver** erreichen.

7.  Erweitern Sie den Knoten **Vertrauenswürdige Anwendungsserver** .

8.  Nun sollte der Exchange 2013-CAS-Server als vertrauenswürdiger Anwendungsserver aufgelistet sein.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>So erstellen Sie eine vertrauenswürdige Anwendung für den Exchange 2013 CAS-Server

1.  Starten Sie die lync Server 2013-Verwaltungsshell.

2.  Wenn sich der CAS-Server *nicht* auf demselben Server befindet, auf dem Exchange 2013 Unified Messaging (um) ausgeführt wird, führen Sie das folgende Cmdlet aus:
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Ausführliche Informationen finden Sie im Thema [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in der Dokumentation zur Verwaltungs-Shell für lync Server 2013.

3.  Führen Sie **enable-CsTopology** aus.

4.  Erweitern Sie im linken Bereich von Topology Builder die Struktur, bis Sie **Vertrauenswürdige Anwendungsserver** erreichen.

5.  Erweitern Sie den Knoten **Vertrauenswürdige Anwendungsserver** .

6.  Nun sollte der Exchange 2013-CAS-Server als vertrauenswürdiger Anwendungsserver aufgelistet sein.

</div>

</div>

<span> </span>

</div>

</div>

</div>

