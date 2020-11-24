---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für die Überwachung'
description: 'Lync Server 2013: Bereitstellungscheckliste für die Überwachung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3d3293accf6e25c20ae8391f9107ae75fef338
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49394622"
---
# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Prüfliste zur Bereitstellung für die Überwachung in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-05_

Obwohl die Überwachung auf jedem Front-End-Server bereits installiert und aktiviert ist, müssen Sie noch einige Schritte Unternehmen, bevor Sie tatsächlich Überwachungsdaten für Microsoft lync Server 2013 erfassen können. Diese Schritte werden in der nachstehenden Prüfliste aufgeführt:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Phase</p></td>
<td><p>Schritte</p></td>
<td><p>Rolle und Gruppenmitgliedschaft</p></td>
<td><p>Dokumentation</p></td>
</tr>
<tr class="even">
<td><p><strong>Installieren der erforderlichen Hardware und Software</strong></p></td>
<td><p>Installieren einer unterstützten Version von Microsoft SQL Server auf dem Computer, der als Back-End-Datenspeicher für die Überwachung fungiert.</p></td>
<td><p>Domänenbenutzer, der auch Mitglied der lokalen Administratorgruppe ist.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> im Supporthandbuch</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Unterstützung von Server Software und-Infrastruktur in lync Server 2013</a> im Supporthandbuch</p></td>
</tr>
<tr class="odd">
<td><p><strong>Erstellen der geeigneten internen Topologie zur Unterstützung der Überwachung</strong></p></td>
<td><p>Verwenden Sie den lync Server 2013-Topologie-Generator, um der Topologie Überwachungsdatenbanken hinzuzufügen, und veröffentlichen Sie dann die aktualisierte Topologie.</p></td>
<td><p>Definieren einer Topologie, ein Benutzer, der Mitglied der lokalen Benutzergruppe ist.</p>
<p>Veröffentlichen der Topologie, ein Benutzer, der Mitglied der Domänenadministratorgruppe und der RTCUniversalServerAdmins-Gruppe ist.</p></td>
<td><p><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in lync Server 2013</a> im Bereitstellungshandbuch</p></td>
</tr>
<tr class="even">
<td><p><strong>Aktivieren der entsprechenden Überwachungseinstellungen</strong></p></td>
<td><p>Aktivieren Sie die Anrufdetailaufzeichnung (CDR) und/oder die QoE-Überwachung (Quality of Experience) auf den globalen und/oder den Website Bereichen.</p></td>
<td><p>Ein Benutzer, der Mitglied der RTCUniversalServerAdmins-Gruppe ist oder dem eine RBAC-Rolle mit Zugriff auf das Cmdlet CsCdrConfiguration und auf das Cmdlet CsQoEConfiguration zugewiesen wurde.</p></td>
<td><p><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Konfigurieren der Einstellungen für die Anrufdetailaufzeichnung und die Qualität der Benutzerfreundlichkeit in lync Server 2013</a> im Betriebshandbuch</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

