---
title: 'Lync Server 2013: Konfigurieren von Unified Messaging auf Microsoft Exchange Server für die Zusammenarbeit mit Lync Server 2013'
description: 'Lync Server 2013: Konfigurieren von Unified Messaging auf Microsoft Exchange Server für die Zusammenarbeit mit lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53c303f0ae659536aafcbdfcd829ed236e35a0ba
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432429"
---
# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Konfigurieren von Unified Messaging auf Microsoft Exchange Server für die Zusammenarbeit mit Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-11_

<div>


> [!IMPORTANT]  
> Wenn Sie Exchange Unified Messaging (um) zum Bereitstellen von Anrufbeantwortung, Outlook Voice Access oder automatischen Telefonzentralen für Enterprise-VoIP-Benutzer verwenden möchten, lesen Sie <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planen der Integration von Exchange Unified Messaging in lync Server 2013</A> in der Planungsdokumentation, und folgen Sie dann den Anweisungen in diesem Abschnitt.



</div>

Um Exchange Unified Messaging (um) für die Arbeit mit Enterprise-VoIP zu konfigurieren, müssen Sie die folgenden Aufgaben ausführen:

  - Konfigurieren von Zertifikaten auf dem Server mit Exchange Unified Messaging (um)-Diensten
    
    <div>
    

    > [!NOTE]  
    > Fügen Sie allen um-SIP-URI-Wählplänen alle Client Zugriffs-und Postfachserver hinzu. Wenn dies nicht der Fall ist, funktioniert das Routing für ausgehende Anrufe nicht wie erwartet.

    
    </div>

  - Erstellen Sie bei Bedarf einen oder mehrere um-SIP-URI-Wählpläne zusammen mit den Telefonnummern für den Abonnenten Zugriff, und erstellen Sie dann entsprechende lync Server-Wählpläne.

  - Verwenden Sie das **exchucutil.ps1** -Skript, um Folgendes zu tun:
    
      - Erstellen von um-IP-Gateways
    
      - Erstellen von um-Sammelanschlüssen
    
      - Erteilen der lync Server 2013-Berechtigung zum Lesen von um-Active Directory-Domänendienste-Objekten

  - Erstellen Sie ein Objekt der automatischen UM-Telefonzentrale.

  - Erstellen Sie ein Teilnehmerzugriffs Objekt.

  - Erstellen Sie einen SIP-URI für jeden Benutzer, und verknüpfen Sie Benutzer mit einem um-SIP-URI-Wählplan.

<div>

## <a name="requirements-and-recommendations"></a>Anforderungen und Empfehlungen

Bevor Sie beginnen, wird in der in diesem Abschnitt aufgeführten Dokumentation davon ausgegangen, dass Sie die folgenden Exchange 2013-Rollen bereitgestellt haben: Client Zugriff und Postfach. In Microsoft Exchange Server 2013 wird Exchange um als Dienst auf diesen Servern ausgeführt.

Ausführliche Informationen zum Bereitstellen von Exchange 2013 finden Sie in der Exchange 2013 TechNet-Bibliothek unter [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)

Beachten Sie außerdem Folgendes:

  - Wenn Exchange um in mehreren Gesamtstrukturen installiert ist, müssen die Exchange Server-Integrationsschritte für jede um-Gesamtstruktur ausgeführt werden. Darüber hinaus muss jede um-Gesamtstruktur so konfiguriert werden, dass Sie der Gesamtstruktur vertraut, in der lync Server 2013 bereitgestellt wird, und die Gesamtstruktur, in der lync Server 2013 bereitgestellt wird, muss so konfiguriert sein, dass Sie jeder um-Gesamtstruktur vertraut.

  - Die Integrationsschritte erfolgen sowohl für die Exchange-Serverrollen, auf denen Unified Messaging-Dienste ausgeführt werden, als auch auf dem Server, auf dem lync Server 2013 ausgeführt wird. Sie sollten die Exchange Server Unified Messaging-Integrationsschritte ausführen, bevor Sie die lync Server 2013-Integrationsschritte ausführen.
    
    <div>
    

    > [!NOTE]  
    > Informationen dazu, welche Integrationsschritte für welche Server und welche Administratorrollen ausgeführt werden, finden Sie unter <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Bereitstellungsprozess für die Integration von lokalen Unified Messaging und lync Server 2013</A>.

    
    </div>

Die folgenden Tools müssen auf jedem Server mit Exchange um verfügbar sein:

  - Exchange-Verwaltungsshell

  - Das Skript **exchucutil.ps1**, in dem die folgenden Aufgaben ausgeführt werden:
    
      - Erstellt ein um-IP-Gateway für jeden lync Server 2013.
    
      - Erstellt einen Sammelanschluss für jedes Gateway. Die Pilotkennung der einzelnen Sammelanschlüsse gibt den um-SIP-URI-Wählplan an, der vom Front-End-Pool oder Standard Edition-Server verwendet wird, der dem Gateway zugeordnet ist.
    
      - Erteilt lync Server 2013 die Berechtigung zum Lesen von Exchange um-Objekten in Active Directory-Domänendiensten.

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren von Zertifikaten auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Konfigurieren von Unified Messaging in Microsoft Exchange für lync Server 2013](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

