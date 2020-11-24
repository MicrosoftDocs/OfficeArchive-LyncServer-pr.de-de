---
title: 'Lync Server 2013: Anforderungen für Webkonferenzen'
description: 'Lync Server 2013: Anforderungen für Webkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1fce932d3cc02ac29364d53d04ec336693e43b
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394294"
---
# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Webkonferenz Anforderungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Wenn Sie sich für die Bereitstellung von Webkonferenzfunktionen entschieden haben, müssen Sie Folgendes planen:

  - <span></span>  
    Zugriff auf den Dateispeicher, der zum Speichern von Webkonferenzinhalten verwendet wird.

  - <span></span>  
    Integration mit dem Office Web App-Server. Dies ist für die Freigabe von PowerPoint-Dateien während einer Konferenz erforderlich.

<div>

## <a name="file-store"></a>Dateispeicher

Der lync Server 2013-Webkonferenzdienst speichert während Besprechungen im Dateispeicher freigegebene Inhalte. Als Teil der Bereitstellung müssen Sie eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder den Enterprise Edition-Front-End-Pool verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.  Weitere Informationen finden Sie unter Topologie-Generator – definieren Sie den Dateispeicher für das Front-End. Der Webkonferenzdienst verschlüsselt die Inhalte vor dem Speichern im Dateispeicher.

Lync Server 2013 unterstützt die Verwendung von Dateifreigaben entweder in Direct Attached Storage (das) oder in einem SAN (Storage Area Network), einschließlich DFS (Distributed File System) und auf einem redundanten Array von unabhängigen Datenträgern (RAID) für Dateispeicher. Nachdem der lync Server-Bereitstellungs-Assistent den Speicherort der Dateifreigabe definiert hat, erstellt lync Server eine Ordnerstruktur innerhalb der Dateifreigabe ähnlich wie:

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

Der Webkonferenzdienst speichert dann Inhalte wie z. B. PowerPoint-Folien, Whiteboards, Umfragen und Anhänge in den Ordnern „CollabContent“ und „CollabMetadata“, die sich wiederum im Ordner „WebServices“ befinden.

Der Administrator muss Berechtigungen für die Dateifreigabe einrichten, damit RTC-Gruppen über den erforderlichen Lese-und Schreibzugriff verfügen.

<div>


> [!WARNING]  
> Wenn Fehler mit den Berechtigungen auftreten, öffnen Sie den Topologie-Generator, laden Sie die vorhandene Topologie herunter, und veröffentlichen Sie Sie erneut. Beim Veröffentlichen der Topologie werden die Dateifreigabeberechtigungen überprüft und bei Bedarf zurückgesetzt.



</div>

Sie können die folgenden Einstellungen verwenden, um zu verwalten, wie Inhalte für eine Besprechung gespeichert werden:

  - In **ContentGracePeriod**, das sich in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)befindet, wird festgelegt, wie lange Webkonferenzinhalte auf dem Server verbleiben, nachdem die Besprechung beendet wurde.

  - **MaxContentStorageMb**, das sich in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)befindet, legt die maximale Menge an Dateispeicherplatz fest, die für die Speicherung von Inhalten während einer einzelnen Besprechung zulässig ist.

**MaxUploadFileSizeMb** schränkt die Einstellung für den Dateiupload für lync Web App nicht ein. Die maximale Upload-Grenze für die Dateigröße für lync Web App ist auf ungefähr 30 MB festgesetzt und wird durch die IIS web.config-Datei gesteuert:/DataCollabWeb/int \[ Ext \] /Handler/web.config. Zum Konfigurieren des Upload-Grenzwerts für die Dateigröße für lync Web App aktualisieren Sie `maxRequestLength` und `maxAllowedContentLength` in der web.config-Datei wie unten dargestellt.

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

Sie müssen die web.config-Datei für jeden Front-End-Server aktualisieren.

</div>

<div>

## <a name="office-web-apps-server"></a>Office Web Apps-Server

Um diese neuen Funktionen verwenden zu können, müssen Administratoren Office Web Apps Server installieren und lync Server 2013 für die Kommunikation mit Office Web Apps Server konfigurieren. Diese Dokumentation enthält Informationen zum Konfigurieren von lync Server 2013 für die Zusammenarbeit mit Office Web Apps Server. In dieser Dokumentation werden keine Informationen zur Installation von Office Web Apps Server bereitgestellt. Einzelheiten zur Installation finden Sie auf der Microsoft Office Web Apps-Bereitstellungswebsite unter <https://go.microsoft.com/fwlink/p/?linkid=257525> . Dieser Leitfaden enthält alle erforderlichen Informationen für Office Web Apps Server. Beachten Sie, dass der Office Web Apps-Server auf einem eigenständigen Computer installiert sein sollte, auf dem lync Server, SQL Server oder eine andere Serveranwendung nicht ausgeführt wird. (Auf diesem Computer darf keine Office-Version installiert sein.) Auf jedem Computer, auf dem Office Web Apps-Server ausgeführt wird, muss auch eine bestimmte Softwaregruppe installiert sein (einschließlich .NET Framework 4,5 und Windows PowerShell 3,0). Diese Anforderungen sowie Informationen zum Konfigurieren von Zertifikaten und Internet Informationsdienste (IIS) werden ausführlich auf der Microsoft Office Web Apps-Bereitstellungswebsite unter erläutert <https://go.microsoft.com/fwlink/p/?linkid=257525> .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Übersicht über Webkonferenzen in lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Bereitstellungscheckliste für Webkonferenzen in lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

