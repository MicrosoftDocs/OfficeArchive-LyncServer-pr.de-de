---
title: 'Lync Server 2013: Exportieren von archivierten Daten'
description: 'Lync Server 2013: Exportieren von archivierten Daten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656751f1a2d03b50f0c938a8501ba3e95e304cff
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49428335"
---
# <a name="exporting-archived-data-from-lync-server-2013"></a>Exportieren von archivierten Daten aus lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Die in Archivierungsdatenbanken archivierten Daten liegen nicht in durchsuchbarem oder lesbarem Format vor. Sie können jedoch mit dem Cmdlet Export-CsArchivingData Datensätze aus der Datenbank extrahieren und als EML (Outlook Electronic Mail)-Datei speichern.. Ausführliche Informationen zum Exportieren von archivierten Daten finden Sie unter [exportieren-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in der Betriebsdokumentation.

Wenn Sie die Microsoft Exchange-Integration aktivieren, werden die Daten in Exchange 2013-Stores archiviert. In Exchange 2013 archivierte Daten sind durchsuchbar und auffindbar. Details zur Unterstützung der integrierten Kommunikation für Exchange 2013 und lync Server 2013 finden Sie unter Unterstützung für [Exchange Server und SharePoint-Integration in lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in der Dokumentation zur Unterstützung. Details zum Zugriff auf Daten, die in Exchange archiviert werden, finden Sie in der Exchange 2013-Dokumentation.

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportieren von Archivierungsdaten mithilfe von Windows PowerShell-Cmdlets

Archivierungsdaten können mithilfe des Export-CSArchivingData-Cmdlets exportiert werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

**So exportieren Sie Archivierungsdaten**

  - Mit diesem Befehl werden alle Archivierungsdaten exportiert, die in die Archivierungsdatenbank ATL-SQL-001.litwareinc.com seit dem 1. Juni 2012 geschrieben wurden. Die resultierende Ausgabedatei wird im Ordner C: ArchivingExports gespeichert \\ .
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**So exportieren Sie Archivierungsdaten für einen einzelnen Benutzer**

  - Mit dem folgenden Befehl werden Archivierungsdaten für einen einzelnen Benutzer exportiert: kenmyer@litwareinc.com. Hierzu wird der Parameter „UserUri“, gefolgt von der SIP-Adresse des Benutzers, eingefügt. Beispiel:
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Unterstützung der Integration von Exchange Server und SharePoint in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[Verwalten der Lync Server 2013-Archivierung](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

