---
title: 'Lync Server 2013: Vorbereiten des Active Directory-Schemas'
description: 'Lync Server 2013: Vorbereiten des Active Directory-Schemas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df7533dcbabe278fd366b441cfd8daa83f54b23
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49424114"
---
# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Vorbereiten des Active Directory-Schemas in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-08-27_

Bevor Sie mit dem Vorbereiten der Active Directory-Domänendienste beginnen, können Sie die Schemadateien mit einem Text-Editor wie Windows Notepad öffnen oder die [Active Directory-Schemaerweiterungen,-Klassen und-Attribute anzeigen, die von lync Server 2013 verwendet](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) werden, um alle Active Directory-Domänendienste-Schemaerweiterungen zu überprüfen, die für lync Server 2013 geändert werden. Lync Server verwendet vier Schemadateien:

  - ExternalSchema. ldf, das für die Interoperabilität mit Microsoft Exchange Server verwendet wird

  - ServerSchema. ldf, die primäre lync Server 2013-Schemadatei

  - BackCompatSchema. ldf, das für die Interoperabilität mit Komponenten aus früheren Versionen verwendet wird

  - VersionSchema. ldf, das für Versionsinformationen des vorbereiteten Schemas verwendet wird

Alle LDF-Dateien werden während der Schemavorbereitung installiert, unabhängig davon, ob Sie von einer früheren Version migrieren oder eine Neuinstallation durchführen. Diese Schemadateien werden in der in der obigen Liste aufgeführten Reihenfolge installiert und befinden sich im \\ \\ Ordner "Support Schema" auf dem Installationsmedium.

Die lync Server-Schemaerweiterungen werden über alle Domänen repliziert, was Auswirkungen auf den Netzwerkverkehr hat. Führen Sie die Schemavorbereitung zu einem Zeitpunkt aus, an dem die Netzwerkauslastung gering ist.

<div>


> [!NOTE]  
> Wenn Sie Unterstützung für Microsoft® Office Communicator Mobile 2007 R2 für Java und Microsoft® Office Communicator Mobile für Nokia 1,0 für mobile Clients zu ihrer lync Server 2013-Bereitstellung hinzufügen müssen, müssen Sie das Active Directory-Schema für Microsoft Office Communications Server 2007 R2 während der Installation von lync Server 2013 vorbereiten. Die erforderlichen Software-und Dokumentationsinformationen finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A> .



</div>

<div>

## <a name="adsi-edit"></a>ADSI-Bearbeitung

Der Active Directory Service Interfaces-Editor (ADSI-Bearbeitung) ist ein AD DS-Verwaltungstool, mit dem Sie die Schemavorbereitung und-Replikation überprüfen können.

Die ADSI-Bearbeitung wird standardmäßig installiert, wenn Sie die AD DS-Rolle installieren, um einen Server zu einem Domänencontroller zu machen. Für Windows Server 2008 und Windows Server 2008 R2 ist die ADSI-Bearbeitung (AdsiEdit. msc) in den Remote Server-Verwaltungs Tools enthalten. Sie können die Remoteserver-Server auch auf Domänenmitgliedsservern oder eigenständigen Servern installieren. Wenn Sie Windows installieren, wird das Remoteserver-Paket standardmäßig auf diese Server kopiert, aber nicht standardmäßig installiert. Sie installieren einzelne Tools mithilfe des Server-Managers. Die ADSI-Bearbeitung ist unter **Rollenverwaltungstools**, **Active Directory-Domänendienst Tools**, **Active Directory-Domänen Controller Tools** enthalten.

Für Windows Server 2003 ist die ADSI-Bearbeitung in den Support Tools enthalten. Die Support Tools stehen auf der Windows Server 2003-CD im \\ Ordner Support Tools zur Verfügung \\ , oder Sie können Sie unter "Windows Server 2003 Service Pack 2 32-Bit-Support Tools" herunterladen [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770) . Anweisungen zum Installieren der Support Tools auf der Produkt-CD finden Sie unter "Installieren von Windows-Support Tools" unter [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771) . Adsiedit.dll wird automatisch registriert, wenn Sie die Support Tools installieren. Wenn Sie die Dateien jedoch auf Ihren Computer kopiert haben, müssen Sie den Befehl **regsvr32** ausführen, um die adsiedit.dll Datei zu registrieren, bevor Sie das Tool ausführen können.

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Ausführen der Active Directory-Schemavorbereitung in Lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Überprüfen der Active Directory-Schemareplikation in Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Vorbereiten der Gesamtstruktur für Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Vorbereiten von Domänen für Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

