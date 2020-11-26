---
title: 'Lync Server 2013: Sichern und Schützen der Datenbanken'
description: 'Lync Server 2013: Härten und schützen von Datenbanken.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af1ed8f54384e8ecac3b1e4ce6a4253a10bcc2c6
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49427761"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>Sichern und Schützen der Datenbanken von Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-12-05_

Microsoft lync Server 2013 hängt auch von SQL Server-Datenbanken zum Speichern von Benutzerinformationen, Konferenzstatus, Archivierungsdaten und Anruf Detail Datensätzen (CDRs) ab. Sie können die Verfügbarkeit von lync Server 2013-Daten in lync Server-Back-End-Datenbanken maximieren, indem Sie die Anwendungsdaten auf eine Weise partitionieren, die die Fehlertoleranz verbessert und die Problembehandlung vereinfacht. Um diese Ziele zu erreichen, partitionieren Sie die Anwendungsdaten nach folgendem:

  - **Verwenden von bewährten Methoden für die Server Partitionierung**   Trennen Sie das Betriebssystem, die Anwendung und die Programmdateien von den Datendateien.

  - **Speichern von Transaktionsprotokolldateien und Datenbankdateien**   Speichern Sie diese Dateien separat, um die Fehlertoleranz zu erhöhen und die Wiederherstellung zu optimieren, und speichern Sie Sie auf einem verschlüsselten Datenträger oder Volume.

  - **Verwenden von Serverclustern**   Clustern Sie die Back-End-Server, um die Systemverfügbarkeit von lync Server 2013 zu optimieren.

  - **Sicherstellen, dass alle Datensicherungen verschlüsselt und ordnungsgemäß verarbeitet werden**   Verloren gegangene, verworfene oder verlegte Sicherungsmedien können eine erhebliche Gefährdung der Datensicherheit für lync Server 2013-Bereitstellungen darstellen.

Auf einem lync Server 2013-Server mit Ausnahme des Standard Edition-Servers ist die SQL Server Express-Instanz (RTCLOCAL-Instanz) nicht Remote verfügbar, und es werden keine lokalen Firewall-Ausnahmen erstellt, mit Ausnahme von SQL Server Express auf einem Standard Edition-Server. Auf einem Standard Edition-Server sind sowohl die Back-End-Datenbank als auch der zentrale Verwaltungsspeicher (CMS) so eingerichtet, dass ein Remotezugriff möglich ist. Zum Härten von SQL Server-Datenbankenkönnen Sie die folgenden Aktionen ausführen:

  - Passen Sie die SQL Server Express-Firewall auf Standard Edition-Servern an, um den Umfang der Server zu begrenzen, die Remote auf die Datenbank zugreifen können. Standardmäßig kann eine beliebige IP-Adresse Remote auf die Datenbank zugreifen.

  - Verwenden Sie den SQL Server-Konfigurations-Manager, um die Protokolle, IP-Adressen und Ports für den SQL Server-Remotezugriff anzugeben:
    
      - Lync Server 2013 verwendet das TCP/IP-Protokoll. Sie unterstützt IP Version 4 (IPv4), aber nicht IP Version 6 (IPv6).
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013 kann in einem Netzwerk mit aktiviertem Dual IP Stack funktionieren.

        
        </div>
    
      - Lync Server 2013 unterstützt mehrere IP-Adressen (mehrfach vernetzte Netzwerk Adresskarten). Sie können angeben, dass SQL Server nur bestimmte IP-Adressen (einzelne Adresse oder Subnetz) abhören und nur bestimmte Protokolle verwenden soll.
    
      - Lync Server 2013 unterstützt statische und dynamische SQL Server-Ports.

  - Führen Sie SQL Server auf einem statischen (nicht standardmäßigen) Port aus, und führen Sie keinen SQL Server-Browser aus (damit der Abhör-Port nicht an den Client gemeldet werden kann). Dies erfordert eine benutzerdefinierte Konfiguration für jeden SQL Server-Client, einschließlich Front-End-Server, Überwachungsserver, Archivierungsserver und Verwaltungskonsolen (mit lync Server-Verwaltungsshell, lync Server Control Panel oder Topology Builder) und allen anderen Servern, auf denen lync Server-Datenbanken ausgeführt werden).

<div>


> [!NOTE]  
> Der Zugriff auf Datenbanken muss auf vertrauenswürdige Datenbankadministratoren limitiert sein. Ein böswilliger Datenbankadministrator kann Daten in die Datenbanken einfügen oder ändern, um Berechtigungen über die lync Server 2013-Server zu erwerben oder vertrauliche Informationen von den Diensten abzurufen, auch wenn dem Datenbankadministrator kein direkter Zugriff oder keine Kontrolle über die lync Server 2013-Server gewährt wurde.



</div>

Details zu benutzerdefinierten Konfigurationen und zum Härten von SQL Server-Datenbanken finden Sie im NextHop-Blog Artikel "Verwenden von lync Server 2010 mit einer benutzerdefinierten SQL Server-Netzwerkkonfiguration" unter [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) .

<div>


> [!NOTE]  
> Sie können auch Betriebssysteme und Anwendungsserver verhärten, und Sie können mithilfe von Gruppenrichtlinien Sicherheits Sperrungen in ihrer lync Server-Bereitstellung implementieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Härten und schützen von Servern und Anwendungen für lync Server 2013</A>.



</div>

</div>

<span> </span>

</div>

</div>

</div>

