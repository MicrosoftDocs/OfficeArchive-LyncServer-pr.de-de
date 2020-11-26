---
title: 'Lync Server 2013: Einrichten von Benutzerrichtlinien für die Archivierung in lync Server'
description: 'Lync Server 2013: Einrichten von Benutzerrichtlinien für die Archivierung in lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e33abf6cf16c9c1367162aa8beee91874f4c725
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49441627"
---
# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>Einrichten von Benutzerrichtlinien für die Archivierung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

Das Aktivieren oder Deaktivieren der Archivierung für bestimmte Benutzer, die in lync Server 2013 verwaltet werden, erfordert das Erstellen und Konfigurieren einer oder mehrerer Benutzerrichtlinien und das anschließende Anwenden der entsprechenden Richtlinie auf bestimmte Benutzer oder Benutzergruppen. Benutzerrichtlinien setzen Website-und globale Richtlinien außer Kraft, allerdings nur für Benutzer, die in lync Server 2013 verwaltet werden.

Benutzer sind immer in lync Server beheimatet. Wenn die Microsoft Exchange-Integration aktiviert ist, müssen Benutzer, deren Postfächer in Microsoft Exchange Server 2013 enthalten sind, ihre Archivierungsrichtlinien nicht in lync Server verwalten. Diese Benutzer mit Archivierung werden von Exchange In-Place halten verwaltet.

Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für Global-, Website-und Benutzerrichtlinien, finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.

<div>


> [!NOTE]  
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange In-Place Speicherrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange 2013 befinden. Die Archivierung für diese Benutzer setzt voraus, dass ihre Postfächer In-Place halten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server-Integration</A> in der Bereitstellungsdokumentation.<BR>Sie sollten alle geeigneten Optionen in den Archivierungs Konfigurationen angeben, bevor Sie die Archivierung aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Konfigurieren von Archivierungsoptionen in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Anwenden einer lync Server-Archivierungsrichtlinie auf einen Benutzer in lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

