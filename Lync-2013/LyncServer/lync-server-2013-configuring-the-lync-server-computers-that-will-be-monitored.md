---
title: 'Lync Server 2013: Konfigurieren der lync Server-Computer, die überwacht werden sollen'
description: 'Lync Server 2013: Konfigurieren der lync Server-Computer, die überwacht werden sollen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742bd8a67eb42472e598c45619514e9407cb29cf
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49432555"
---
# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a>Konfigurieren der lync Server-Computer, die in lync Server 2013 überwacht werden

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Da lync Server 2013 den zentralen Ermittlungsprozess, der in Microsoft lync Server 2010 verwendet wird, nicht verwendet, muss jeder lync Server 2013-Computer, den Sie überwachen möchten, seine Existenz dem Verwaltungs Server selbst melden können. Damit dies möglich ist, müssen Sie die Operations Manager-Agentendateien auf jedem der zu überwachenden Computer installieren. Nachdem die Agentendateien installiert wurden, müssen Sie den Computer so konfigurieren, dass er als System Center-Proxy fungiert. Beachten Sie, dass diese Verfahren ausgeführt werden sollten, nachdem Sie lync Server auf diesen Computern installiert und konfiguriert haben.

</div>

<span> </span>

</div>

</div>

</div>

