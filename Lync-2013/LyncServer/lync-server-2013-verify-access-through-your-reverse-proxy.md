---
title: 'Lync Server 2013: Überprüfen des Zugriffs über den Reverseproxy'
description: 'Lync Server 2013: Überprüfen des Zugriffs über den Reverse-Proxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 593aac5574f0dcf683351f12a6392f6116480ac5
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49443475"
---
# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>Überprüfen des Zugriffs über den Reverseproxy in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-29_

Gehen Sie wie folgt vor, um zu überprüfen, ob Ihre Benutzer auf Informationen auf dem Reverse-Proxy zugreifen können. Möglicherweise müssen Sie die Firewall-Konfiguration und DNS-Konfiguration (Domain Name System) durchführen, bevor Access ordnungsgemäß funktioniert.

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>So überprüfen Sie, ob Sie über das Internet auf die Website zugreifen können

  - Öffnen Sie einen Webbrowser, und geben Sie die URLs in der **Adress** Leiste ein, die Clients für den Zugriff auf die Adressbuchdateien und die Website für Konferenzen wie folgt verwenden:
    
      - Geben Sie für den Adressbuch Server eine URL ein, die der folgenden ähnelt: **https://externalwebfarmFQDN/abs** wobei externalwebfarmFQDN der externe FQDN der externen Webdienste ist, der Adressbuchdienste hostet. Der Benutzer sollte eine HTTP-Abfrage erhalten, da die Verzeichnissicherheit im Ordner "Adressbuch Server" standardmäßig für die Windows-Authentifizierung konfiguriert ist.
    
      - Geben Sie für Konferenzen eine URL ein, die der folgenden ähnelt: **https://externalwebfarmFQDN/meet** wobei externalwebfarmFQDN der externe FQDN der Webfarm ist, die Besprechungsinhalte hostet. Diese URL sollte die Seite zur Problembehandlung für Konferenzen anzeigen. Sie können aber auch sicherstellen, dass Ihre einfache URL für Konferenzfunktionen ordnungsgemäß funktioniert. Eine einfache URL für die Konferenzteilnahme ist möglicherweise https://meet.contoso.com
    
      - Geben Sie für die Erweiterung der Verteilergruppe eine URL ein, die der folgenden **https://externalwebfarmFQDN/GroupExpansion/service.svc** ähnelt: Der Benutzer sollte eine HTTP-Challenge erhalten, da die Verzeichnissicherheit des Verteilergruppen-Erweiterungs Diensts standardmäßig für die Windows-Authentifizierung konfiguriert ist.
    
      - Geben Sie für Einwahl die einfache URL ein, die der folgenden ähnelt, **https://externalwebfarmFQDN/dialin** wobei externalwebfarmFQDN der externe FQDN der Webfarm ist, die die Einwahlseite für Einwahlkonferenzen hostet. Der Benutzer sollte an die Einwahlseite weitergeleitet werden. Sie können aber auch sicherstellen, dass Ihre einfache URL-Einwahlfunktion ordnungsgemäß funktioniert. Ein Beispiel für eine einfache URL für die Einwahl ist möglicherweise https://dialin.contoso.com
    
      - Um zu bestätigen, dass die Auto Ermittlungs-URL funktioniert, geben Sie https://lyncdiscover . externaldomainFQDN. Der Browser sollte Sie dazu auffordern, eine Datei zu öffnen. Wählen Sie Editor aus, um ihn zu öffnen. Eine typische Antwort wäre ähnlich wie bei:
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

