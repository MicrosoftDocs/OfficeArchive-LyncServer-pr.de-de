---
title: 'Lync Server 2013: zwischen trunk-Routing'
description: 'Lync Server 2013: zwischen trunk-Routing.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e023956f28183423c04e94948acdec0df2c1284
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49426865"
---
# <a name="inter-trunk-routing-in-lync-server-2013"></a>Zwischen trunk-Routing in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-08_

Lync Server 2013 bietet grundlegende Sitzungsverwaltung durch die Unterstützung von intertrunk-Routing. Mit dieser neuen Funktion kann lync Server Funktionen zur Anrufsteuerung für Downstream-Telefoniesysteme bereitstellen. Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können. In ähnlicher Weise kann lync Server zwei oder mehr IP-PBX-Systeme verbinden, damit Anrufe zwischen PBX-Telefonen von den verschiedenen IP-PBX-Systemen getätigt und empfangen werden können.

Die folgende Abbildung zeigt, wie lync Server 2013 die Interkonnektivität zwischen einem PSTN-Gateway und einer IP-Telefonanlage bereitstellt.

![Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)")

Die nächste Abbildung zeigt die lync Server 2013-Verbindung zwischen zwei IP-PBX-Systemen.

![Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)")

</div>

<span> </span>

</div>

</div>

</div>

