---
title: Konfigurieren von lync Server für die Zusammenarbeit mit System Center Operations Manager
description: Konfigurieren von lync Server für die Zusammenarbeit mit System Center Operations Manager
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58126c9e56d48548ba5ce6d74059809c55fecf5
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432898"
---
# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>Konfigurieren von lync Server 2013 für die Zusammenarbeit mit System Center Operations Manager

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Um Ihre Microsoft lync Server 2013-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren, müssen Sie drei Schritte ausführen:

  - Identifizieren und konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver. Die Konfiguration des Verwaltungsservers umfasst die Installation von System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 sowie das Einrichten einer Back-End-Datenbank mithilfe von SQL Server. Die aktuelle Version von SQL Server, die Sie verwenden müssen, hängt von der Version von System Center Operations Manager ab, die Sie verwenden. Ausführliche Informationen finden Sie unter [Konfigurieren des primären Verwaltungsservers in lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).

  - Identifizieren und konfigurieren Sie die lync Server-Computer, die Sie überwachen möchten. Wenn Sie einen lync Server-Computer mithilfe von System Center Operations Manager überwachen möchten, müssen Sie die System Center Operations Manager-Agentdateien installieren und die einzelnen Server so konfigurieren, dass Sie als Proxy fungieren.

  - Identifizieren und konfigurieren Sie die Computer, die als lync Server Watcher- *Knoten* fungieren sollen. Watcher-Knoten sind Computer, die in regelmäßigen Abständen lync Server-synthetische Transaktionen ausführen, also Windows PowerShell-Cmdlets, die überprüfen, ob wichtige lync Server-Komponenten wie die Möglichkeit zur Anmeldung am System oder die Möglichkeit zum Austausch von Sofortnachrichten wie erwartet funktionieren.

Die Themen in diesem Abschnitt enthalten Anweisungen zur Durchführung der einzelnen Aufgaben.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren des primären Verwaltungsservers in lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md)

  - [Installieren der lync Server 2013-Verwaltungspakete](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Konfigurieren der lync Server-Computer, die in lync Server 2013 überwacht werden](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Installieren und Konfigurieren von Watcher-Knoten in lync Server 2013](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

