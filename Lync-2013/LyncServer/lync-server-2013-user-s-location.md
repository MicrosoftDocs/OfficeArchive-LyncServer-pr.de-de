---
title: 'Lync Server 2013: Standort des Benutzers'
description: 'Lync Server 2013: Standort des Benutzers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a92ec780809cdb3e1ee582ce6c348c884bbb5890
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49439170"
---
# <a name="users-location-in-lync-server-2013"></a>Standort des Benutzers in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-09_

Location-Based-Routing nutzt dieselben netzwerkregionen,-Standorte und-Subnetze, wie Sie in lync Server von E9-1-1, CAC und medienumgehung definiert sind, um Anruf Weiterleitungs Einschränkungen anzuwenden, um die PSTN-Maut Umgehung zu verhindern. Der Standort eines Benutzers wird durch das IP-Subnetz der lync-Endpunkte des Benutzers bestimmt, von dem die Verbindung hergestellt wird. Jedes IP-Subnetz ist einem Netzwerkstandort zugeordnet, von denen mehrere zu vom Administrator definierten Netzwerkbereichen zusammengefasst sind. Das standortbasierte Routing wird auf Grundlage des Netzwerkstandorts des Benutzers durchgesetzt.

Location-Based Routingregeln werden pro Netzwerk Website angewendet, was bedeutet, dass ein bestimmter Regelsatz auf alle Endpunkte angewendet wird, die für Location-Based Routing aktiviert sind, die sich innerhalb desselben Netzwerkstandorts befinden. Administratoren können das standortbasierte Routing auf Netzwerkstandorte anwenden, die dies erfordern.

Richtlinien für das VoIP-Routing können auf Grundlage von Netzwerkstandorten definiert werden, um ein bestimmtes Gateway in das öffentliche Telefonnetz zu definieren, das dann von allen Benutzern, die sich am gleichen Netzwerkstandort befinden, für Verbindungen mit Rufnummern im öffentlichen Telefonnetz verwendet werden muss. Solche VoIP-Routing Richtlinien haben Vorrang vor dem Routing, das durch die VoIP-Richtlinie des Benutzers definiert wird, wenn sich der Benutzer in einer Netzwerk Website befindet, die für Location-Based Routing aktiviert ist, und er verhindert das Routing von Anrufen über andere PSTN-Gateways, die für Location-Based Routing aktiviert sind. Wenn ein lync-Benutzer einen PSTN-Anruf anlegt, bestimmt die VoIP-Richtlinie des Benutzers, ob der Benutzer zum tätigen des Anrufs autorisiert werden kann. Wenn die VoIP-Richtlinie des Benutzers es dem Benutzer ermöglicht, den Anruf zu tätigen, bestimmt Location-Based Routing, von welchem PSTN-Gateway der Anruf ausgehen soll. Location-Based Routing macht diese Ermittlung auf Grundlage des Standorts des Benutzers.

Der Standort eines Benutzers kann auf folgende Weise kategorisiert werden:

  - Der Benutzer befindet sich in einer bekannten Netzwerk Website, die für Location-Based Routing aktiviert ist, und seine DID-Nummer (Direktwahl) wird auf einem PSTN-Gateway beendet, das sich auf demselben Netzwerkstandort befindet (also Office). Das Routing ausgehender Anrufe erfolgt anhand der VoIP-Routingrichtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet. Aus dem öffentlichen Telefonnetz für den Benutzer eingehende Anrufe werden an Endpunkte geroutet, die sich am gleichen Netzwerkstandort wie das Gateway in das öffentliche Telefonnetz befinden.

  - Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der sich von dem Netzwerkstandort unterscheidet, an dem sich das Gateway in das öffentliche Telefonnetz befindet (d. h., der Benutzer ist zu einem anderen Unternehmensstandort gereist). Das Routing ausgehender Anrufe erfolgt anhand der VoIP-Routingrichtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet. Für den Benutzer aus dem öffentlichen Telefonnetz eingehende Anrufe werden nicht an Endpunkte geroutet, die sich an anderen Standorten befinden als das Gateway in das öffentliche Telefonnetz, um das Umgehen von Gebühren im öffentlichen Telefonnetz zu vermeiden.

  - Wenn sich ein Benutzer in einer Netzwerk Website befindet, die der lync Server-Bereitstellung unbekannt ist, basiert das Routing von ausgehenden Anrufen auf der VoIP-Richtlinie, die dem Benutzer für PSTN-Gateways zugewiesen ist, die nicht an Location-Based Routing Einschränkungen gebunden sind. Eingehende Anrufe aus dem öffentlichen Telefonnetz werden nicht an Endpunkte geroutet, die sich an unbekannten Netzwerkstandorten befinden, um das Umgehen von Gebühren im öffentlichen Telefonnetz zu vermeiden.

<div>

## <a name="see-also"></a>Siehe auch


[Anleitungen für das standortbasierte Routing in Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

