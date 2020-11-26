---
title: 'Lync Server 2013: Erstellen von Agent-Gruppen für Reaktionsgruppen'
description: 'Lync Server 2013: Erstellen von Reaktionsgruppen-Agentgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9420ee5f6fbd4b995c8542b848ef30f53e46fc4
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431617"
---
# <a name="create-response-group-agent-groups-lync-server-2013"></a>Erstellen von Agent-Gruppen für Reaktionsgruppen Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-12_

Beim Erstellen einer Agentgruppe wählen Sie die Agents aus, die der Gruppe zugewiesen werden. Außerdem geben Sie zusätzliche Gruppeneinstellungen (beispielsweise die Routingmethode) an und legen fest, ob sich ein Agent bei der Gruppe an- und abmelden muss.

Ein Agent, der sich bei der Gruppe an-und abmelden muss, die sich von der Anmeldung bei lync Server unterscheidet, wird als *formeller Agent* bezeichnet. Formelle Agents müssen sich bei der Gruppe anmelden, um an die Gruppe weitergeleitete Anrufe empfangen zu können. Dies kann für Agents nützlich sein, die Anrufe der Gruppe nur zeitweise annehmen. Formelle Agents melden sich bei ihren Gruppen an und aus, indem Sie in lync 2013 auf ein Menüelement klicken, um den Internet Browser von Windows Internet Explorer zu öffnen und eine Webseite-Konsole anzuzeigen.

Ein Agent, der sich nicht bei der Gruppe anmeldet, wird als *informeller Agent* bezeichnet. Informelle Agents werden bei der Anmeldung bei lync Server automatisch bei der Gruppe angemeldet, und Sie können sich nicht von der Gruppe abmelden.

<div>


> [!NOTE]  
> Nur lokale Benutzer können Agents sein. Wenn ein Agent von lokal in Online verschoben wird, werden keine Antwortgruppen Aufrufe an diesen Agenten weitergeleitet.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

[Erstellen oder Ändern einer Agentengruppe in lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

