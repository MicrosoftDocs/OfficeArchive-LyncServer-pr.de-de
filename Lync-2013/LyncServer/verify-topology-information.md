---
title: Überprüfen von Topologieinformationen
description: Überprüfen der Topologieinformationen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ed41cd95fffdca629e710dcf443631d0c74c69e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49440118"
---
# <a name="verify-topology-information"></a>Überprüfen von Topologieinformationen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-26_

Der erste Schritt beim erfolgreichen Überprüfen des Seriendrucks besteht darin, die Office Communications Server 2007 R2-Topologieinformationen anzuzeigen, die Sie mit lync Server 2013 zusammengeführt haben. Im Topologie-Generator zeigt der **BackCompatSite** -Knoten den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) jedes Office Communications Server 2007 R2-Pools und-Servers an, den Sie zusammengeführt haben.

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>So zeigen Sie BackCompatSite im Topologie-Generator an

1.  Öffnen Sie in Ihrer Office Communications Server 2007 R2-Umgebung das Office Communications Server 2007 R2-Verwaltungstool, und notieren Sie sich die FQDNs der Legacy Pools und-Server.

2.  Öffnen Sie in ihrer lync Server 2013-Umgebung den Topologie-Generator, und erweitern Sie dann den **BackCompatSite** -Knoten.

3.  Überprüfen Sie, ob die FQDNs für die Pools und Server, die Sie zusammenführen, angezeigt werden.
    
    <div>
    

    > [!NOTE]  
    > Es werden keine Informationen in <STRONG>BackCompatSite</STRONG> für Serverrollen angezeigt, die sich auf einem Front-End-Server oder einem Standard Edition-Server befinden. Es werden nur Serverrollen angezeigt, die für die Interoperabilität zwischen Office Communications Server 2007 R2 und lync Server 2013 erforderlich sind.

    
    </div>

![Dialogfeld ' BackCompatSite '](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Dialogfeld ' BackCompatSite '")

Sie können auch die lync Server 2013-Systemsteuerung verwenden, um Ihre zusammengeführte Topologie anzuzeigen. In der lync Server 2013-Systemsteuerung können Sie jeden Server-FQDN, Pool-FQDN und Websitenamen für Ihre zusammengeführte Topologie sehen. Verbundene Server verfügen über den **Website** Namen **BackCompatSite**.

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>So zeigen Sie die zusammengeführte Topologie in der lync Server 2013-Systemsteuerung an

1.  Öffnen Sie die lync Server 2013-Systemsteuerung.

2.  Klicken Sie auf **Topologie**.

3.  Überprüfen Sie auf der Registerkarte **Status** , ob die zusammengeführten Server und Pools angezeigt werden, indem Sie in der Spalte **Websites** nach **BackCompatSite** suchen.

![Lync Server-Systemsteuerung mit zusammengeführter Topologie](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server-Systemsteuerung mit zusammengeführter Topologie")

Wenn Sie weitere Details zu einem zusammengeführten Pool anzeigen möchten, verwenden Sie das Cmdlet **Get-CsPool** . Zusätzlich zu den Informationen, die im Topologie-Generator und in der lync Server 2013-Systemsteuerung zur Verfügung stehen, zeigt dieses Cmdlet die Dienste an, die im lync Server 2013-Pool ausgeführt werden.

<div>


> [!NOTE]  
> Wenn Sie die Topologie nach dem Ausführen des Zusammenführungs-Assistenten im Topologie-Generator veröffentlichen, werden Konferenzverzeichnisse mit lync Server 2013 zusammengeführt. Konferenzverzeichnisse können überprüft werden, indem Sie das Cmdlet " <STRONG>Get-CsConferenceDirectory</STRONG> " ausführen.



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>So zeigen Sie Dienste in einem zusammengeführten Pool an

1.  Öffnen Sie die lync Server 2013-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Beispiel:
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>So überprüfen Sie die Zusammenführung von Konferenz Verzeichnissen

1.  Öffnen Sie die lync Server 2013-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsConferenceDirectory

3.  Stellen Sie sicher, dass sich alle Konferenzverzeichnisse für den Pool oder Server, den Sie zusammenführen, jetzt in lync Server 2013 befinden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

