---
title: 'Lync Server 2013: Übersicht über den Sicherungs-und Wiederherstellungsprozess'
description: 'Lync Server 2013: Übersicht über den Sicherungs-und Wiederherstellungsprozess.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77b833a05021d3a848e9de1ee8768f7daa194c6a
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437994"
---
# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Übersicht über den Sicherungs-und Wiederherstellungsprozess für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-26_

Dieser Abschnitt enthält eine Übersicht über die Funktionsweise des Sicherungs-und Wiederherstellungsprozesses für lync Server 2013. Sie verwenden das gleiche Verfahren für alle Standard Edition-Server und Enterprise Edition-Server unabhängig von deren Standort.

Im Allgemeinen funktioniert der Sicherungsvorgang wie folgt:

  - Sie erstellen einen Sicherungsspeicherort als freigegebenen Ordner auf einem eigenständigen Computer, der nicht zu einem Pool gehört. Auf den Speicherort der Sicherung wird in **$Backup** verwiesen.

  - In regelmäßigen Abständen sichern Sie alle lync Server-Datenbanken und alle Dateispeicher, die unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013 beschrieben werden: Daten](lync-server-2013-backup-and-restoration-requirements-data.md) , indem Sie die unter [Sichern von lync Server 2013](lync-server-2013-backing-up-lync-server.md) beschriebenen Verfahren ausführen, in dem der zentrale Verwaltungsspeicher alle Server Einstellungen und-Konfigurationen umfasst.

  - Jedes Mal, wenn Sie eine nachfolgende Sicherung ausführen, erstellen Sie einen neuen freigegebenen Ordner und ändern den Pfad, in dem Verweise **$Backup** .

Im Allgemeinen funktioniert der Wiederherstellungsprozess wie folgt:

  - Wenn ein Fehler oder Ausfall auftritt, stellen Sie die Daten an dem Speicherort wieder her, auf den **$Backup** auf neue oder bereinigte Computer verweisen.
    
    <div>
    

    > [!IMPORTANT]  
    > Durch diesen Wiederherstellungsprozess werden keine Daten auf einem vorhandenen Serverzustand wiederhergestellt. Dieser Vorgang erfordert also, dass der Server sauber oder neu ist.

    
    </div>

  - Damit Ihre Benutzer-und Konferenz Informationen bis zum Zeitpunkt des Fehlers wiederherstellbar sind, können Sie eine Disaster Recovery-Topologie mit gekoppelten Front-End-Pools implementieren, wie in [Planen für Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)beschrieben.

  - Alle DNS-Konfigurationen (Domain Name System), DHCP-Konfiguration (Dynamic Host Configuration Protocol), Domänennamen, vollqualifizierte Computer Domänennamen (FQDNs), Dateispeicher Pfade usw. müssen zum Zeitpunkt der Wiederherstellung identisch sein, die Sie zum Zeitpunkt der Wiederherstellung hatten.

Wenn ein Server mit lync Server ausfällt, umfasst die Wiederherstellung die folgenden Schritte:

  - Installieren Sie das Betriebssystem auf einem neuen oder sauberen Computer mit demselben FQDN wie der fehlerhafte Computer.

  - Installieren Sie Zertifikate erneut.

  - Wenn der Server eine Datenbank gehostet hat, installieren Sie Microsoft SQL Server 2012 oder Microsoft SQL Server 2008 R2.

  - Wenn der Server eine Datenbank gehostet hat, führen Sie im Allgemeinen den Topologie-Generator aus, um die Datenbank zu erstellen und zu installieren sowie Zugriffssteuerungslisten (ACLs) einzurichten.

  - Wenn der Server eine Serverrolle gehostet hat, führen Sie im allgemeinen Schritt 1 bis Schritt 4 des lync Server-Bereitstellungs-Assistenten aus, um die lokalen Konfigurationsdateien zu installieren, die Serverrollenkomponenten zu installieren, Zertifikate zuzuweisen und die Dienste zu starten.
    
    <div>
    

    > [!NOTE]  
    > Wenn der Server eine Datenbank mit der Serverrolle gehostet hat, wird mit Schritt 2 des lync Server-Bereitstellungs-Assistenten die Datenbank neu erstellt.

    
    </div>

  - Wenn der Server eine Datenbank gehostet hat, stellen Sie die gesicherten Daten wieder her.

</div>

<span> </span>

</div>

</div>

</div>

