---
title: 'Lync Server 2013: Ändern des einem Front-End-Pool zugeordneten Edgepools'
description: 'Lync Server 2013: Ändern des Edge-Pools, der einem Front-End-Pool zugeordnet ist.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab22ba35420341e291d51a1ff012459840e63a56
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49435047"
---
# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a>Ändern des einem Front-End-Pool zugeordneten Edgepools in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Wenn ein Edge-Pool ausfällt, der Front-End-Pool am gleichen Standort aber noch ausgeführt wird, müssen Sie den Front-End-Pool so einrichten, dass ein Edge-Pool an einer anderen Website verwendet wird, bis der fehlerhafte Edge-Pool wiederhergestellt wird.

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a>Ändern des einem Front-End-Pool zugeordneten Edge-Pools

1.  Navigieren Sie im Topologie-Generator zu dem Namen des Front-End-Pools, den Sie ändern müssen.

2.  Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

3.  Verwenden Sie im Abschnitt **Zuordnungen** unter **Edge-Pool zuordnen (für Medienkomponenten)** das Dropdownfeld, um den Edge-Pool auszuwählen, dem Sie diesen Front-End-Pool zuordnen möchten.

4.  Klicken Sie auf **OK**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Notfallwiederherstellung für Edgeserver in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

