---
title: 'Lync Server 2013: Importieren von Geräte Update Regeln'
description: 'Lync Server 2013: Importieren von geräteaktualisierungsregeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a7b936a4b7be96332343e8f96134d5ba1b879be
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394899"
---
# <a name="import-device-update-rules-in-lync-server-2013"></a>Importieren von geräteaktualisierungsregeln in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Geräteaktualisierungsregeln können nur mithilfe von Windows PowerShell und dem Cmdlet " **Import-CsDeviceUpdate** " importiert werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a>So importieren Sie geräteaktualisierungsregeln auf einen einzelnen Webserver

  - Mit dem folgenden Befehl werden geräteaktualisierungsregeln auf den Webserver ATL-CS-001.litwareinc.com importiert:
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a>So importieren Sie geräteaktualisierungsregeln auf alle Ihre Webserver

  - In diesem Beispiel werden geräteaktualisierungsregeln in alle Webserver importiert, die in Ihrer Organisation bereitgestellt werden. Damit dieser Befehl funktioniert, müssen die Ordner- \\ \\ ATL-FS-001.litwareinc.com- \\ Updates freigegeben und allen Webservern zur Verfügung stehen.
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) ".

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Anzeigen von Informationen zu Geräte Update Regeln in lync Server 2013](lync-server-2013-view-information-about-device-update-rules.md)  
[Genehmigen einer geräteaktualisierungsregel in lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

