---
title: 'Lync Server 2013: Konfigurieren von Reaktionsgruppen'
description: 'Lync Server 2013: Konfigurieren der Reaktionsgruppe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92674bb971ec5216051d75d788dc58b9c7ca641c
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432688"
---
# <a name="configuring-response-group-in-lync-server-2013"></a>Konfigurieren von Reaktionsgruppen in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-30_

Reaktionsgruppe ist ein Enterprise-VoIP-Feature, mit dem eingehende Anrufe an Personengruppen, so genannte *Agenten*, weitergeleitet und in die Warteschlange gestellt werden, beispielsweise ein Helpdesk oder ein Kundendienst Desk.

Die Komponenten, die von der Reaktionsgruppe benötigt werden, werden beim Bereitstellen von Enterprise-VoIP automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert. Um die Reaktionsgruppe für Benutzer verfügbar zu machen, müssen Sie Agentengruppen, dann Warteschlangen und dann Workflows konfigurieren. Darüber hinaus kann ein Antwortgruppen Administrator die Konfiguration eines vorhandenen Workflows an einen Reaktionsgruppen-Manager delegieren, der dann den Workflow und die zugehörigen Agentengruppen und-Warteschlangen ändern und neu konfigurieren kann.

Dieser Abschnitt führt Sie durch die Konfiguration der lync Server 2013-Reaktionsgruppe. Es wird davon ausgegangen, dass Sie die Planungsabschnitte in Bezug auf die Reaktionsgruppe bereits gelesen haben und einen Enterprise Edition-Server oder einen Standard Edition-Server mit Enterprise-VoIP bereitgestellt haben.

<div>


> [!TIP]  
> Details zum Erstellen einer Reaktionsgruppe mithilfe der lync Server-Verwaltungsshell, einschließlich eines Beispielskripts, finden Sie unter "Erstellen Ihrer ersten Reaktionsgruppe mithilfe der lync Server-Verwaltungsshell" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A> .



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Berechtigungen und Voraussetzungen für die Konfiguration von Reaktionsgruppen in Lync Server 2013](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Bereitstellungsprozess für die Reaktionsgruppe in lync Server 2013](lync-server-2013-deployment-process-for-response-group.md)

  - [Übersicht über Szenarios zur Erstellung von Workflows in Lync Server 2013](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [Erstellen von Agent-Gruppen für Reaktionsgruppen Lync Server 2013](lync-server-2013-create-response-group-agent-groups.md)

  - [Erstellen von Warteschleifen für Reaktionsgruppen in Lync Server 2013](lync-server-2013-create-response-group-queues.md)

  - [Optional Definieren der Geschäftszeiten der Reaktionsgruppe in lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)

  - [Optional Definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [Erstellen von Workflows für Reaktionsgruppen in Lync Server 2013](lync-server-2013-create-response-group-workflows.md)

  - [Optional Überprüfen der Bereitstellung von Reaktionsgruppen in lync Server 2013](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen der Anruf Verwaltungsfeatures in lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

