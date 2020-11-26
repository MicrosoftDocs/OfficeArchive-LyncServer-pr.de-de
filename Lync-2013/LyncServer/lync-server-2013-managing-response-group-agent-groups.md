---
title: 'Lync Server 2013: Verwalten von Reaktionsgruppen-Agentgruppen'
description: 'Lync Server 2013: Verwalten von Reaktionsgruppen-Agentgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23a4f430981689f9794c05aa1472ff61cd32cd5f
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49437266"
---
# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>Verwalten von Reaktionsgruppen-Agentgruppen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Eine Agentengruppe besteht aus einer Gruppe von Personen, die für die Beantwortung von Anrufen an eine Reaktionsgruppe vorgesehen sind. Wenn Sie eine Agentengruppe erstellen, wählen Sie die Agents aus, die der Gruppe zugewiesen sind, und geben zusätzliche Gruppeneinstellungen an, beispielsweise die Routingmethode, und ob sich ein Agent an-und abmelden kann.

<div>


> [!NOTE]  
> Benutzer müssen für Enterprise-VoIP aktiviert sein, bevor Sie Sie den Agentengruppen hinzufügen können. Details zum Aktivieren eines Benutzers für Enterprise-VoIP finden Sie unter <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</A>.



</div>

<div>


> [!NOTE]  
> Nur lokale Benutzer können Agents sein. Wenn ein Agent von lokal in Online verschoben wird, werden keine Antwortgruppen Aufrufe an diesen Agenten weitergeleitet.



</div>

Ein Agent, der sich bei der Gruppe an-und abmelden muss, die sich von der Anmeldung bei lync Server unterscheidet, wird als *formeller Agent* bezeichnet. Formelle Agents müssen bei der Gruppe angemeldet sein, bevor Sie Anrufe empfangen können, die an die Gruppe weitergeleitet werden. Dies kann für Agents nützlich sein, die Anrufe der Gruppe nur zeitweise annehmen. Formelle Agents melden sich bei ihren Gruppen an und aus, indem Sie in lync 2013 auf ein Menüelement klicken, um den Internet Browser von Windows Internet Explorer zu öffnen und eine Webseite-Konsole anzuzeigen.

Ein Agent, der sich nicht bei der Gruppe anmeldet, wird als *informeller Agent* bezeichnet. Informelle Agents werden bei der Anmeldung bei lync Server automatisch bei der Gruppe angemeldet, und Sie können sich nicht von der Gruppe abmelden.

<div>


> [!IMPORTANT]  
> Wenn Sie Benutzer als Reaktionsgruppenagents zuweisen, weisen Sie diese darauf hin, dass sie bei aktiviertem Datenschutzmodus nach „RGS-Anwesenheitsmonitor“-Kontakten suchen und sie ihrer Kontaktliste hinzufügen müssen. Agents, deren Datenschutzmodus aktiviert ist, die jedoch „RGS-Anwesenheitsmonitor“ nicht in ihre Kontaktliste aufgenommen haben, können keine Anrufe bei der Reaktionsgruppe annehmen. Agents, deren Datenschutzmodus nicht aktiviert ist, sind davon nicht betroffen.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erstellen oder Ändern einer Agentengruppe in lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Löschen einer Agentengruppe in lync Server 2013](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

